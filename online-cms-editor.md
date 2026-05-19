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
* Webhook Support
* Frontmatter UI Manager
* Resize and Compress images on upload
* Sub Folder support for Content and Uploads
* Custom Appearance and Typography
* Custom Branding
* License Manager / Domain Transfer

#### Webhooks

Webhooks let the Online Editor notify another service when content or users change. They are useful for triggering deployments, sending notifications, updating search indexes, or connecting the CMS to another workflow.

Webhooks are a Pro feature and are managed by owners inside the Online Editor:

1. Open **Webhooks** in the Online Editor.
2. Click **Add Webhook**.
3. Enter an HTTPS endpoint URL.
4. Choose the events the endpoint should receive.
5. Save the webhook, then copy the signing secret immediately. The secret is only shown when the webhook is created.

You can enable or disable a webhook without deleting it, edit its endpoint URL or selected events, and delete it when it is no longer needed.

Supported events:

| Event | Fires when |
| --- | --- |
| `file.created` | A content file is created. |
| `file.updated` | A content file is updated, renamed, or restored from version history. |
| `file.deleted` | A content file is deleted. |
| `user.created` | A user account is created. |
| `user.updated` | A user account is updated. |
| `user.deleted` | A user account is deleted. |

Each delivery is sent as a signed JSON `POST` request. The Online Editor attempts each delivery once and records the result in the webhook delivery log, including the event, endpoint URL, HTTP status, and any connection error.

For payload examples, the `X-Webhook-Signature` header, and HMAC verification details, see the [Webhooks JSON API guide](json-api/guides/webhooks.md).

#### JSON REST API

Sites with JSON API access can create `api_...` keys from the Online Editor's API page. Those keys let headless frontends, apps, and migration scripts read and write CMS content over HTTPS. See the [JSON REST API](json-api/README.md) docs for installation, authentication, examples, and the full route reference.

#### MCP Server

Sites with MCP access can connect Claude, Cursor, MCP Inspector, and other MCP-compatible AI assistants from **AI** > **Connections** in the Online Editor. The assistant can act as a chosen user to read, edit, upload, and manage CMS content through conversation. See the [MCP Server](mcp/README.md) docs for setup, connection methods, security notes, and the full tools reference.

#### Important note about content sync

If you add or edit Markdown files online (outside of Elements), you need to remember these changes will not be synced back down to Elements, they only exist on your server.

We’d like to add support for syncing server content back into Elements in the future, but for now, keep in mind that the app only pushes data out, it doesn’t pull it back in.

In summary, this means:

* They won’t show up in the CMS folder inside Elements.
* You won’t be able to edit or manage them in the app.
* Republishing your site from Elements may overwrite changes made online.
