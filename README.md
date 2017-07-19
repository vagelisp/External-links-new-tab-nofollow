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


Simple demo file

```
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>External-links-new-tab-nofollow</title>
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
</head>
<body>
  You ll need to use a domain to test this ( localhost will do )
  <p><a href="#">Link</a></p>
  <p><a href="http://google.com">External link</a></p>
  <script>
    jQuery(document).ready(function($) {
        $('a').not('[href*="mailto:"], [href*="tel:"], [href*="#"], [href*=""] ').each(function () {
            var mylink = new RegExp('/' + window.location.host + '/');
            if ( ! mylink.test(this.href) ) {
                $(this).attr('target', '_blank');
                $(this).attr('rel', 'nofollow');
            }
        });
    });
  </script>
</body>
</html>
```