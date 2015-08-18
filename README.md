# Social Media Bundle for Symfony2

> Publishing/Unpublishing posts on social network can be a pain in the ass. Thats why I created an automated way of things. You can easily use this Social Media Bundle for Symfony2.

## Examples

### How to publish a post to Facebook

```php
/** @var FacebookPostPublish $post */
$post = new FacebookPostPublish(
    $title,
    $description,
    $url
);

/** @var FacebookService $service */
$service = new FacebookService();

// publish
$this->get('social_media')->publish(
    $post,
    $service
);
```

### How to unpublish a post from Facebook

```php
// facebook post id
$identifier = '126577990374899_1489744286461266';

/** @var FacebookPostUnpublish $post */
$post = new FacebookPostUnpublish(
    $identifier
);

/** @var FacebookService $service */
$service = new FacebookService();

// unpublish
$this->get('social_media')->unpublish(
    $post,
    $service
);
```

### How to fetch errors

```php
try {
    // unpublish
    $this->get('social_media')->unpublish(
        $post,
        $service
    );
} catch (SocialMediaException $e) {
    throw new Exception($e->getMessage());
}
```
