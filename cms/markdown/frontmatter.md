---
description: Using structured data in Markdown files
---

# Frontmatter

The Elements CMS uses [YAML Frontmatter](frontmatter.md) to define metadata and editable fields for your Markdown content. This is a block of structured data placed at the top of a Markdown file, enclosed by triple dashes.&#x20;

Here's an example file containing frontmatter, and a paragraph of content.

{% code title="sample.md" %}
```markdown
---
title: Elements CMS Example
date: 2025-08-07
author: Jonny Appleseed
tags: [introduction, getting-started]
---

## Example INtroduction
Elements CMS lets you manage content using *simple Markdown* files with frontmatter.
You can write normal Markdown below the frontmatter, and **Elements** will handle the rest.
```
{% endcode %}

You can [learn more about defining Frontmatter here](frontmatter.md)

### Date Format

The YAML frontmatter **date** uses the following format, **year**-**month**-**day** in the Elements CMS.&#x20;

Time is also respected for date filtering, so you can now use "2025-08-21 17:00". The time is currently in UTC, customising the timezone is not currently supported.

### **No Quotes Needed If**

Whether or not you **need to use quotes** depends on what's inside the value. You can safely skip quotes for simple strings:

```markdown
title: My Blog Post
date: 2025-08-06
author: Julia
```

***

### **Use Quotes If**

1. The value contains **special characters** like `:`, `@`, `#`, or `{}`:

```
title: “My Favorite Tools: Tailwind, Alpine, and Elements”
```

2. The value \*\*starts with a number\*\* that might be misread (like a version number):

```
version: “1.0”
```

3. The value looks like a \*\*boolean\*\*, \`null\`, or includes \*\*colons/time values\*\*:

```
status: “false”

time: “14:30”
```

4. The value has \*\*line breaks\*\* (rare, but possible in multiline strings).

### &#x20;Safe Rule of Thumb

If you’re unsure, wrap it in quotes. You won’t break anything by quoting strings:

```yaml
title: “I Just Used Tailwind UI in Elements – And It’s a Game Changer!”
```

### Setting Default Frontmatter

If there is no default value the CMS will output nothing. You can set a default for any missing frontmatter properties like so `{{item.missingProp|default("Default Text")}}` .&#x20;

### Image Front Matter

You can define images in your front matter using nested keys. This allows you to store multiple pieces of information about an image, rather than just a single file path.\
\
The following keys are supported inside an image object:

* src – the path or URL to the image
* title – the image title (optional, often used for tooltips or accessibility)
* width – the image width in pixels (optional)
* height – the image height in pixels (optional)
* alt – a short text description of the image, used for accessibility

The src value can point to a local file within your project or to a remote image hosted online.

You can name the image object anything you like, it doesn’t have to be called image. For example, `banner:`, `thumbnail:`, or `photo:` will all work the same way.

```markdown
---
title: Welcome to the Elements CMS
date: 2025-08-07
image:
  src: welcome.jpg
  alt: Abstract illustration of a CMS interface
---
```

And here’s the same example using a custom key:

```markdown
---
title: Welcome to the Elements CMS
date: 2025-08-07
banner:
  src: blog/interface.jpg
  title: CMS interface
  alt: Abstract illustration of a CMS interface
---
```

When you reference this data in your template, you can access each nested property directly, for example, in a custom component you could do the following:

```html
@raw()
    <img src="{{item.image.src}}" alt="{{item.image.alt}}">
@endraw
```

### Defining an Array of Images

The following example defines an array of remote images in the frontmatter for use in a photo gallery:

```markdown
gallery:
- src: "https://images.unsplash.com/photo-1626692987335-15dfc7a6f4b2?q=80&w=4448&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
  title: "Chichen Itza: Ancient Precision - View 1"
  alt: "Chichen Itza: Ancient Precision image 1"
- src: https://images.unsplash.com/photo-1544214889-03dfb1348b48?q=80&w=5184&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
  title: "Chichen Itza: Ancient Precision - View 2"
  alt: "Chichen Itza: Ancient Precision image 2"
- src: "https://plus.unsplash.com/premium_photo-1755105194454-21564954e25e?w=900&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxmZWF0dXJlZC1waG90b3MtZmVlZHw1fHx8ZW58MHx8fHx8$0"
  title: "Chichen Itza: Ancient Precision - View 3"
  alt: "Chichen Itza: Ancient Precision image 3"
```

The following example displays as array of local images for use in a Gallery or Image Slider.

```markdown
gallery:
  - src: "images/project1.jpg"
    alt: "Exterior view of the finished building"
  - src: "images/project2.jpg"
    alt: "Interior design showcasing the main lobby"
  - src: "images/project3.jpg"
    alt: "Construction phase with scaffolding"
```

To display the above array of images use the following code in a custom component:

```html
@raw()
<ul class="flex gap-2">
{% for image in item.gallery %}
    <li><img src="{{ image.src }}" class="w-20 h-auto aspect-[1]" />
{% else %}
    <li>No image.
{% endfor %}
</ul>
@endraw
```
