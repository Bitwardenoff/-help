---
layout: article
title: Searching the vault
categories: [features]
featured: false
popular: false
tags: [search, lunr]
---

Bitwarden indexes your vault using a [full-text search](https://en.wikipedia.org/wiki/Full-text_search){:target="_blank"} programming library called [Lunr](https://lunrjs.com/){:target="_blank"}. Lunr provides the ability to invoke high-performance search queries against your vault to quickly find what you need with great accuracy.

## Applications that use full-text search

The following Bitwarden applications provide full-text searching capabilities and are applicable to the information this article:

- Web vault
- Desktop applications
- Browser extensions

This article **does not** apply to the following Bitwarden applications, which provide only basic search capabilities:

- CLI
- Mobile apps

## Indexed Fields

The following fields from items in your vault are indexed and are searchable:

- `shortid` - First 8 characters of the item's id.
- `organizationid` - Id of the item's organization (if it belongs to one).
- `name`
- `subtitle` - Login username, card brand + last four, and identity name.
- `notes`
- `fields` - Name and value. Only "text" type field values are included.
- `attachments` - File name
- `login.username`
- `login.uris` - Only the URI's [hostname](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHyperlinkElementUtils/hostname){:target="_blank"} value.

## Wildcard Searches

The asterisk character (`*`) provides the ability to perform wildcard searches in your vault. Examples:

- `*bitwarden`
- `bitwarden*`
- `*bitwarden*`
- `*bit*war*den*`

{% callout info %}
The following fields automatically include leading and trailing wildcards while performing normal search queries:

- `name`
- `subtitle`
- `login.uris`

It is not necessary to provide wildcards if you are searching for information in these fields.
{% endcallout %}

## Advanced Searches

Starting your search query with a greater than character (`>`) enables the full power of [Lunr search queries](https://lunrjs.com/guides/searching.html){:target="_blank"}.

### Advanced Search Examples

- `>bitwarden*` - Search all fields for a term that starts with "bitwarden".
- `>notes:something` - Search the notes field for the term "something".
- `>login.username:jsmith` - Search the username field on items of type login for the term "jsmith".
- `>+organizationid:*` - Search for all items that belong to an organization.
- `>-organizationid:*` - Search for all items that *do not* belong to an organization (items that you own).
- `>+foo bar -baz` - Search for items that must contain "foo", might contain "bar" and must not contain "baz".

Learn more about writing advanced search queries using [Lunr's searching guide](https://lunrjs.com/guides/searching.html){:target="_blank"}.
