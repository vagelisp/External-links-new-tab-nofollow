# External-links-new-tab-nofollow

Makes all external links to open in a new tab, also adds rel nofollow.

This is also available as a WordPress plugin.
You can download if from WP Plugin Directory 
https://wordpress.org/plugins/external-links-new-tab-nofollow
or install it from your WP dashboard.

Make sure your website includes jQuery

```javascript
jQuery(document).ready(function($) {
    $('a').not('[href*="mailto:"], [href*="tel:"], [href*="#"], [href*=""] ').each(function () {
        var mylink = new RegExp('/' + window.location.host + '/');
        if ( ! mylink.test(this.href) ) {
            $(this).attr('target', '_blank');
            $(this).attr('rel', 'nofollow');
        }
    });
});
```