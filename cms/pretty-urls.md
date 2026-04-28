---
icon: map-location-dot
---

# Pretty URL's

You can modify the .htaccess file on your server to ensure the CMS produces clean, pretty URL's.

**We'll have detailed instructions on how to configure your .htaccess file soon. In the meantime,** you can add the following code to your htaccess file:

```bash
RewriteEngine On

# ----------------------------------------
# 1. Redirect /post/?item=slug and /post/index.php?item=slug → /post/slug
RewriteCond %{THE_REQUEST} \s/post/(index\.php)?\?item=([^&\s]+) [NC]
RewriteRule ^post/?$ /post/%2? [R=301,L]

# ----------------------------------------
# 2. Internally rewrite /post/slug → /post/index.php?item=slug
RewriteRule ^post/([^/]+)/?$ post/index.php?item=$1 [L,QSA]
```

You will then need to add the following “base” tag to the `<head>` area of your project’s template:

```php-template
<base href="/">

<!-- OR if you're publishing to a subfolder: -->
<base href="/blog/">
```

This ensures that URL like `/post/my-first-post` is rewritten under the hood to `/post/index.php?item=my-first-post`.

Obviously “post” can be anything you want, you just need to ensure your update the htaccess code to match whatever you’ve called the folder in Elements.

***

**Update: April 4th 2026**

The following .htaccess code works for the cms listing page being in the root folder, with the single articles in a /post folder.

```bash
Options -MultiViews
RewriteEngine On

RewriteCond %{THE_REQUEST} \s/+post/(?:index\.php)?\?item=([^\s&]+) [NC]
RewriteRule ^post/(?:index\.php)?$ /post/%1? [R=301,L,NE]

RewriteCond %{REQUEST_FILENAME} -f [OR]
RewriteCond %{REQUEST_FILENAME} -d
RewriteRule ^ - [L]

RewriteRule ^post/([^/]+)/?$ /post/index.php?item=$1 [L,QSA]
```

You will then need to add the following “base” tag to the `<head>` area of your project’s template:

```php-template
<base href="/">
```
