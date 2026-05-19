---
icon: globe
---

# Online CMS Editor

The Elements CMS Admin is a complete browser-based interface for managing your site’s content. It’s designed to be fast, simple, and focused, giving you everything you need to edit and organise content without getting in the way.

Built around Markdown, the admin lets you create, edit, and manage your content in a clean, structured environment that mirrors how your site is put together in Elements.

For smaller websites, you can get started for free. You can edit a single collection of Markdown content and upload files directly through the admin, making it ideal for blogs and small websites.

When your needs grow, paid plans unlock support for multiple collections, more advanced content structures, and the flexibility required for larger client projects.

{% hint style="success" %}
The Online CMS Editor is **free for smaller websites**. Choose a paid plan when you need more.
{% endhint %}

### Included for Free

The online CMS includes the following features for free:

* WYSIWYG Markdown Editor
* Create Markdown files
* Edit Markdown
* Upload Resources
* Single User Account
* Single Content Folder
* Single Resources Folder

#### Additionally with Paid Plans

Elements CMS currently offers Solo and Studio plans. If you need to switch between them, see [Upgrading and Downgrading Plans](upgrading-and-downgrading-plans.md).

* Multiple Users and Groups
* Multiple Content Folders
* Multiple Resources Folders
* [Webhook Support](webhooks.md)
* Frontmatter UI Manager
* Resize and Compress images on upload
* Sub Folder support for Content and Uploads
* Custom Appearance and Typography
* Custom Branding
* License Manager / Domain Transfer

#### JSON REST API

Sites with JSON API access can create `api_...` keys from the Online Editor's API page. Those keys let headless frontends, apps, and migration scripts read and write CMS content over HTTPS. See the [JSON REST API](../json-api/) docs for installation, authentication, examples, and the full route reference.

#### MCP Server

Sites with MCP access can connect Claude, Cursor, MCP Inspector, and other MCP-compatible AI assistants from **AI** > **Connections** in the Online Editor. The assistant can act as a chosen user to read, edit, upload, and manage CMS content through conversation. See the [MCP Server](../mcp/) docs for setup, connection methods, security notes, and the full tools reference.

#### Important note about content sync

If you add or edit Markdown files online (outside of Elements), you need to remember these changes will not be synced back down to Elements, they only exist on your server.

We’d like to add support for syncing server content back into Elements in the future, but for now, keep in mind that the app only pushes data out, it doesn’t pull it back in.

In summary, this means:

* They won’t show up in the CMS folder inside Elements.
* You won’t be able to edit or manage them in the app.
* Republishing your site from Elements may overwrite changes made online.
