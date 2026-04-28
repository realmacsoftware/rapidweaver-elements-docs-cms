---
icon: screwdriver-wrench
---

# Troubleshooting

Most issues with the CMS setup arise from improper configuration, which can often be resolved by thoroughly reviewing your settings in Elements.

{% hint style="danger" %}
Elements CMS [requires PHP 8.4](system-requirements.md) to be installed on your server. You'll need to **ensure your page extension is set to .php** on any pages you wish to access CMS data from.
{% endhint %}

### It's outputting a PHP error on the page.

Ensure the page extension is set to .php on all pages you wish to access CMS data from. If you leave your page extension as .html, the CMS will not function.

### Images show in Preview, but not when Published.

Elements will lowercase all filenames to ensure they are web-safe (`file-name.jpg`), however if your markdown files have references in them to files with mixed case (`File-Name.jpg`), they won't render on some servers.

We'd recommend making all your file names web-safe, and lowercase in the Resources area in Elements. Update the references in your markdown files to match.

