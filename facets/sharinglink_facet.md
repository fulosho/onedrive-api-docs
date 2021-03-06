# SharingLink resource type

The **SharingLink** resource groups link-related data items into a single structure.

If a [**Permission**](../resources/permission.md) resource has a non-null **sharingLink** facet, the permission represents a sharing link (as opposed to permissions granted to a person or group).

## JSON representation

Here is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [ "application", "scope" ],
  "@odata.type": "oneDrive.sharingLink"
}-->

```json
{
  "application": { "@odata.type": "oneDrive.identity" },
  "type": "view | edit | embed",
  "scope": "anonymous | organization",
  "webHtml": "string",
  "webUrl": "url"
}
```

## Properties

| Property name   | Type                                 | Description                                                                                                                                                                                             |
|:----------------|:-------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **application** | [Identity](../resources/identity.md) | Information about the application that created the sharing link.                                                                                                                                        |
| **type**        | string                               | The type of the link created.                                                                                                                                                                           |
| **scope**       | string                               | The scope of the link represented by this permission. Value `anonymous` indicates the link is usable by anyone, `organization` indicates the link is only usable for users signed into the same tenant. |
| **webHtml**     | string                               | For embeddable links, this property contains the HTML code for an `<iframe>` element that will embed the item in a webpage.                                                                             |
| **webUrl**      | string                               | A URL that opens the item in the browser on the OneDrive website.                                                                                                                                       |

## Type enumeration

This table defines the possible values for the **type** property:

| Value   | Role    | Description                                                                     |
|:--------|:--------|:--------------------------------------------------------------------------------|
| `view`  | `read`  | A view-only sharing link, allowing read-only access.                            |
| `edit`  | `write` | An edit sharing link, allowing read-write access.                               |
| `embed` | `read`  | A view-only sharing link that can be used to embed content into a host webpage. Embed links are not available for OneDrive for Business or SharePoint. |

## Scope enumeration

| Value          | Description                                                                                                                 |
|:---------------|:----------------------------------------------------------------------------------------------------------------------------|
| `anonymous`    | The sharing link is available for anyone to use.                                                                            |
| `organization` | The sharing link is available for anyone within the same organization (tenant) to use. Not available for OneDrive Personal. |


<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "The sharing link facet provides information about how a file is shared.",
  "keywords": "sharing,sharing link, sharing url, webUrl",
  "section": "documentation",
  "tocPath": "Facets/SharingLink"
} -->
