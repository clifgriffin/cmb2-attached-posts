CMB2 Attached Posts Field
==================

Custom field for [CMB2](https://github.com/WebDevStudios/CMB2).

This requires jQuery UI for drag & drop and sort functionality, which is included in the /js/lib/ directory.

The post IDs are saved in an array, which can be rearranged by dragging and dropping posts in the attached posts column.

## Installation

Follow the example in `example-field-setup.php` for a demonstration. The example assumes you have both CMB2 and this extension in your mu-plugins directory.

## Customization
In the example file `example-field-setup.php`, the field is added using the prefix `_attached_cmb2_` and the name `attached_posts` which results in a meta key of `_attached_cmb2_attached_posts`. The example also demonstrates how to modify the `get_posts` query args.

## Usage
You can retrieve the meta data using the following:

```php
$attached = get_post_meta( get_the_ID(), '_attached_cmb2_attached_posts', true );
```

This will return an array of attached post IDs. You can loop through those post IDs like the following example:

```php
foreach ( $attached as $attached_post ) {
	$post = get_post( $attached_post );
}
```

Once you have the post data for the post ID, you can proceed with the desired functionality relating to each attached post.
