---
# An instance of the Tag Cloud widget.
# Docs: https://wowchemy.com/docs/page-builder/
widget: tag_cloud

# This file represents a page section.
headless: true

# Order that this section appears on the page.
weight: 120

title: Hobbies
subtitle: ''

content:
  # Filter on criteria
  filters:
    folders:
      - hobby
    tag: ''
    category: ''
    publication_type: ''
    author: ''
    exclude_featured: false
    exclude_future: false
    exclude_past: false
  # Choose how many pages you would like to display (0 = all pages)
  count: 0
  # Choose how many pages you would like to offset by
  offset: 0
  # Page order: descending (desc) or ascending (asc) date.
  order: desc
design:
  # Choose a view for the listings:
  view: list
  columns: '3'
---