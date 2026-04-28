---
description: Display a dynamic list of CMS items, perfect for blogs, projects, and more.
---

# Collection

The **Collection** component displays a group of CMS items on your page, such as blog posts, products, team members, or case studies. It acts as a dynamic list that automatically updates whenever new content is added to your CMS folder.

You can choose which folder to pull content from, how items should be sorted, and which template page to use for displaying individual entries. Collections can also be filtered by tags, authors, status, or featured items, giving you full control over what appears.

Typical use cases include:

* Listing blog posts or news articles
* Showing team members or portfolio projects
* Displaying a paginated list of products

With options for pagination, filtering, and layout controls (like columns, rows, and spacing), the Collection component makes it easy to build flexible, data-driven layouts that stay up to date automatically.

### Collection RSS Feed

To enable an RSS Feed for your collection, open the RSS and Sitemap settings and switch on the RSS toggle. This activates a dynamic feed for the collection, allowing users and apps to subscribe to updates without any extra setup on your server.

{% hint style="info" %}
If you need to force a rebuild of the xml files, you can append `?regenerate_rss=1` to the URL of the page where the Collection is used.
{% endhint %}

You can access `{{collection.rssURL}}` inside the Collection component. This lets you drop a Text component into the Before or After zones and link any text, icon, or SVG directly to the collection’s RSS feed.

### Collection Sitemap

The URL for a sitemap can be exposed on the collection and can be output using `{{collection.sitemapURL}}`

{% hint style="info" %}
If you need to force a rebuild of the xml files, you can append `?regenerate_sitemap=1` to the URL of the page where the Collection is used.
{% endhint %}
