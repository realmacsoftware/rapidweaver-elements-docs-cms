---
description: The flexible, fast, and secure template engine for PHP
icon: leaf
---

# Twig

Elements CMS support the [Twig templating language](https://twig.symfony.com/).

### Date Format Example <a href="#twig-filter-examples" id="twig-filter-examples"></a>

The following example uses the [date–modify Twig Syntax](https://twig.symfony.com/doc/3.x/filters/date_modify.html) to format the date, using the [DateTimeInterface in PHP](https://www.php.net/manual/en/datetime.format.php).

```
{{item.date_published|date("j F  Y")}}
```

{% hint style="warning" %}
### International Date Formatting <a href="#twig-filter-examples" id="twig-filter-examples"></a>

The Twig International Date Extension is installed, but it requires PHP's `intl` extension to be installed and enabled on your server to function correctly. Make sure to check your PHP configuration to ensure it is available.
{% endhint %}

### Uppercase Example <a href="#twig-filter-examples" id="twig-filter-examples"></a>

If you need to ensure your title is uppercased you could append a pipe and upper text to the item.title tag, like this:

```
{{item.title}} 
```

Outputs: Hello world!

```
{{item.title|upper}}
```

Outputs: HELLO WORLD!

### Generate a Clean Text Excerpt

Shows the first 32 words of the content, with all HTML tags removed for a clean text excerpt.

```html
{{ item.body|striptags|split(' ')|slice(0, 32)|join(' ') ~ ' ...' }}
```

### Useful Resources <a href="#useful-resources" id="useful-resources"></a>

* [Twig Docs](https://twig.symfony.com/doc/3.x/)
* [Twig Filters](https://twig.symfony.com/doc/3.x/filters/index.html)
* [Twig Playground](https://twig.symfony.com/play)
* [PHP Date Functions](https://www.php.net/manual/en/function.date.php)
