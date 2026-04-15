---
type: project-note
status: active
created: 2026-04-15
updated: 2026-04-15
tags:
  - project
  - client
  - payload
  - schema
  - cms
  - eagle-heights-estates
---

# Eagle Heights Estates - Payload Schema Plan

## Purpose
Translate the CMS strategy into a practical Payload schema plan that can guide implementation.

This note is not final code. It is the planning layer for what collections, globals, and fields should likely exist before development starts.

## Recommended Globals

### 1. Site Settings
Use for site-wide settings and shared information.

Suggested fields:
- `siteName` (text)
- `siteDescription` (textarea)
- `defaultSeoTitle` (text)
- `defaultSeoDescription` (textarea)
- `socialLinks` (array)
  - `label` (text)
  - `url` (text)
- `footerText` (textarea)
- `logo` (upload -> media)

### 2. Contact Settings
Use for centrally managed contact details.

Suggested fields:
- `contactHeading` (text)
- `contactIntro` (textarea)
- `phone` (text)
- `email` (text)
- `officeLabel` (text)
- `addressOrLocationText` (textarea)
- `formSuccessMessage` (textarea)
- `formDisclaimer` (textarea)

## Recommended Collections

### 1. Pages
Use for core marketing pages such as Home, About, Community / Lifestyle, FAQ, and Contact.

Suggested fields:
- `title` (text, required)
- `slug` (text, unique, required)
- `status` (select: draft / published)
- `hero` (group)
  - `eyebrow` (text)
  - `headline` (text)
  - `body` (textarea)
  - `primaryCtaLabel` (text)
  - `primaryCtaLink` (text)
  - `secondaryCtaLabel` (text)
  - `secondaryCtaLink` (text)
  - `backgroundImage` (upload -> media)
- `layout` (blocks)
- `seoTitle` (text)
- `seoDescription` (textarea)

Notes:
- The `layout` field should use reusable blocks instead of hardcoding page sections.
- `status` can later be replaced or supported by Payload drafts/versioning.

### 2. Lots
This should be the main dynamic collection powering listings and map-related content.

Suggested fields:
- `lotName` (text)
- `lotNumber` (text, required)
- `slug` (text, unique)
- `status` (select: available / pending / sold)
- `price` (text or number depending on formatting needs)
- `lotSize` (text)
- `shortDescription` (textarea)
- `description` (richText or textarea)
- `featuredImage` (upload -> media)
- `gallery` (array of uploads or relationship to media)
- `highlights` (array of text)
- `sortOrder` (number)
- `isFeatured` (checkbox)

Map-related fields:
- `mapplicId` (text)
- `mapLabel` (text)
- `mapStatus` (text or derived from status)
- `mapTooltipText` (textarea)

Optional later fields:
- `latitude` / `longitude`
- `documents` (array of uploads)
- `sitePlanImage` (upload)

### 3. FAQ Items
Use if FAQs should be centrally reusable and easy for the client to manage.

Suggested fields:
- `question` (text, required)
- `answer` (textarea or richText, required)
- `category` (select: general / lots / process / contact)
- `sortOrder` (number)
- `isFeatured` (checkbox)

### 4. Media
Use Payload’s media collection for images and files.

Suggested notes:
- Include alt text
- Consider simple tagging or categorization if media volume grows

## Recommended Blocks For Pages.layout

### Hero Block
Suggested fields:
- eyebrow
- headline
- body
- primary CTA label/link
- secondary CTA label/link
- image

### Rich Text Intro Block
Suggested fields:
- headline
- body

### Value Pillars Block
Suggested fields:
- headline
- items (array)
  - title
  - body
  - icon or image optional

### CTA Block
Suggested fields:
- headline
- body
- CTA label
- CTA link

### Gallery Preview Block
Suggested fields:
- headline
- body
- images (relationship or array)
- CTA label
- CTA link

### FAQ Preview Block
Suggested fields:
- headline
- selected FAQs (relationship to FAQ Items)
- CTA label
- CTA link

### Trust / Credibility Block
Suggested fields:
- headline
- body
- optional proof items array

### Listings Preview Block
Suggested fields:
- headline
- body
- selected lots (relationship to Lots)
- CTA label
- CTA link

### Contact / Inquiry Block
Suggested fields:
- headline
- body
- useGlobalContactSettings (checkbox)
- CTA label

### Map Block
Suggested fields:
- headline
- body
- mapEmbedType or mapMode
- relatedLots (relationship to Lots)
- supporting text

## Relationships To Plan Carefully

### Pages to FAQ Items
Useful for showing curated FAQ previews on multiple pages.

### Pages to Lots
Useful for featured lots on homepage or other sections.

### Lots to Media
Needed for featured images, gallery, and map-related visuals.

### Lots to Mapplic data
Even if Mapplic data is not fully stored in Payload, each lot should still have a stable field that corresponds to the map layer / region.

## Admin Experience Notes
The Payload admin should be structured so the client can use it comfortably.

Recommendations:
- group related fields clearly
- keep labels simple and human-readable
- avoid exposing too many low-level fields unless needed
- use defaults where possible
- use array ordering and sortOrder fields intentionally

## Recommended Implementation Order
### Phase 1
- Media collection
- Site Settings global
- Contact Settings global
- Lots collection
- FAQ Items collection
- Pages collection with a minimal but flexible block set

### Phase 2
- richer relationships between pages and lots
- Mapplic integration refinement
- more advanced SEO handling
- potential lot detail pages

## Notes
- The Pages collection should stay flexible, but not endlessly freeform.
- The Lots collection is a major business object and should be designed carefully.
- Mapplic integration should not become an afterthought or a disconnected custom hack.
- This plan should make the site easier to maintain long after launch.

## Linked
- [[01 - Projects/Eagle Heights Estates Website]]
- [[01 - Projects/Eagle Heights Estates - Payload CMS Content Model Brief]]
- [[01 - Projects/Eagle Heights Estates - Properties Listings Content Blocks]]
