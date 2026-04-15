---
type: project-note
status: active
created: 2026-04-15
updated: 2026-04-15
tags:
  - project
  - client
  - payload
  - cms
  - content-model
  - eagle-heights-estates
---

# Eagle Heights Estates - Payload CMS Content Model Brief

## Purpose
Make the Eagle Heights Estates website highly editable for the client by planning the site around Payload CMS from the beginning.

The goal is not just to launch a polished website, but to give the client a practical editing experience for updating key content over time without needing code changes for every adjustment.

## CMS Strategy
The site should be structured around:
- editable page content
- reusable content blocks
- dynamic lot / listing data
- centrally managed contact and site settings
- simple relationships between listings, media, and page content

## What Should Be Editable
The client should be able to update:
- hero headlines and supporting copy
- CTA text
- page sections and body copy
- gallery images
- FAQ items
- contact details
- lot availability and status
- lot metadata
- trust / reassurance content
- optional page visibility or ordering where appropriate

## Recommended Payload Structure

### Globals
Use globals for content that is reused or managed centrally.

#### Site Settings
Suggested fields:
- site name
- general SEO defaults
- footer content
- social links
- brand assets if needed

#### Contact Settings
Suggested fields:
- phone number
- email address
- inquiry messaging
- office / contact label
- optional location details

## Collections

### Pages
Use for major marketing pages like Home, About, Community / Lifestyle, FAQ, and Contact.

Suggested fields:
- title
- slug
- hero section
- layout blocks
- SEO fields
- status / publish controls

Recommended approach:
Use Payload blocks for modular page sections so the client can adjust page content without the layout becoming overly rigid.

### Lots / Listings
This is one of the most important collections.

Suggested fields:
- lot name / lot number
- slug
- status (available / pending / sold)
- price
- lot size
- short description
- full description
- featured image
- gallery
- map reference / Mapplic ID
- sort order
- optional highlights

This collection should power:
- listings page cards
- lot detail content if needed later
- the interactive Mapplic map relationships

### FAQ Items
Suggested fields:
- question
- answer
- category
- sort order
- page placement if needed

This allows the client to add or change FAQs without editing page code.

### Media / Gallery Items
If not handled through Payload media alone, consider a gallery-oriented collection for more structured visual management.

Suggested fields:
- image
- title / caption
- category
- sort order
- related lot if applicable

## Recommended Block Types
For the Pages collection, use flexible blocks such as:
- Hero block
- Rich text / intro block
- Value pillars block
- CTA block
- Gallery preview block
- FAQ preview block
- Trust / credibility block
- Listings preview block
- Contact / inquiry block
- Map block

This gives the client flexibility while preserving a coherent system.

## Mapplic Integration Considerations
Because the Properties / Listings page will use Mapplic, the content model should account for that early.

### Recommended approach
Each lot in Payload should include a field that can map to the relevant Mapplic region or item.

Suggested fields:
- `mapplicId`
- `mapLabel`
- `mapStatus`

That way:
- the lot map can reference real CMS data
- lot status changes can stay aligned between the listings UI and the map
- the client can update availability without manually changing multiple disconnected places

## Editing Experience Goals
The client editing experience should feel:
- simple
- hard to break
- flexible where needed
- structured where consistency matters

That means:
- avoid making every layout decision editable
- make content editable, not chaos editable
- use clear labels and grouped fields in Payload admin
- keep required fields obvious

## Recommended Priority For Implementation
### Phase 1
- Pages collection with reusable blocks
- Lots / Listings collection
- Contact Settings global
- FAQ Items collection
- Media handling

### Phase 2
- Stronger relationships between map data and listings
- More advanced gallery structure
- Additional SEO / preview controls
- Potential lot detail pages if needed

## Notes
- Payload should make the site adjustable without making it fragile.
- The listings / lot map relationship is one of the most important structural decisions.
- This brief should guide the implementation so the site is not designed first and retrofitted into a CMS later.

## Linked
- [[01 - Projects/Eagle Heights Estates Website]]
- [[01 - Projects/Eagle Heights Estates - Properties Listings Content Blocks]]
- [[01 - Projects/Eagle Heights Estates - Homepage Content Blocks]]
- [[01 - Projects/Eagle Heights Estates - Contact Inquire Content Blocks]]
