---
description: Basic requirements for running Elements CMS on your server
icon: desktop
---

# System Requirements

### Server Requirements

These are the preliminary beta requirements for the Elements CMS, they will be updated over time as the software matures.

* The Elements CMS **requires PHP 8.4** or newer to be installed on your server, including the following PHP extension(s):
  * **mbstring**
* The PHP installation should be 'as usual'. If it is reduced or modified in any way, the CMS may not function properly.
* Windows web servers are not officially supported.

{% hint style="danger" %}
Elements CMS [requires PHP 8.4](system-requirements.md) to be installed on your server. You'll need to **ensure your page extension is set to .php** on any pages you wish to access CMS data from.
{% endhint %}

#### Online CMS Editor Requirements

* The Online CMS Editor **requires PHP 8.4** or newer to be installed on your server.
* Also requires Javascript to be enabled in your browser.

#### Check your PHP environment

To quickly check your PHP environment, create a new file on your server called `phpinfo.php` and add the following line:

```php
<?php phpinfo(); ?>
```

Upload it to your site and visit it in your browser (for example https://yoursite.com/phpinfo.php). This will display a detailed page showing the PHP version, loaded extensions, and configuration settings.

Remember to delete the file once you’ve checked, as it exposes sensitive server information.

#### PHP Page extension

Ensure the page extension is set to .php on all pages you wish to access CMS data from. If you leave your page extension as .html, the CMS will not function.
