---
title: "ARIA: definition role"
short-title: definition
slug: Web/Accessibility/ARIA/Reference/Roles/definition_role
page-type: aria-role
spec-urls: https://w3c.github.io/aria/#definition
sidebar: accessibilitysidebar
---

The `definition` ARIA role indicates the element is a definition of a term or concept.

## Description

The `definition` ARIA role can be included on an element that is a definition of a term or concept, similar to the native {{HTMLElement('dfn')}} element. To associate the definition with the `term` being defined, and to provide an accessible name, reference the term being defined with `role="term"`, using [`aria-labelledby`](/en-US/docs/Web/Accessibility/ARIA/Reference/Attributes/aria-labelledby).

```html-nolint
<p>
  <span role="term">Mansplaining</span>,
  <span role="definition">
    a portmanteau of "man" and "explain", is the patronizing act of explaining
    without being asked to do so, to someone already learned on the topic, often
    after someone has already explained it
  </span>.
</p>
```

> [!NOTE]
> Instead of a `<span>` with the [`term`](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/term_role) and `definition` roles, use the {{HTMLElement('dfn')}} element. **Always use native element if available.**

```html
<p>
  <dfn>Mansplaining</dfn>, a portmanteau of "man" and "explain", is the
  patronizing act of explaining without being asked to do so, to someone already
  learned on the topic, often after someone has already explained it.
</p>
```

## Specifications

{{Specifications}}

## See also

- [The `term` role](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/term_role)
- The {{HTMLElement('dfn')}} element
- The {{HTMLElement('dd')}} element
- The {{HTMLElement('dl')}} element
- The {{HTMLElement('dt')}} element
