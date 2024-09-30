---
title: Pagination
slug: Web/CSS/Layout_cookbook/Pagination
page-type: guide
---

{{CSSRef}}

This cookbook pattern demonstrates the navigation pattern used to display pagination, where the user can move between pages of content such as search results.

![Links to sets of pages in a paged listing](pagination.png)

## Requirements

The pagination pattern typically displays items in a row. To ensure that the pagination is understandable by people using a screen reader, we mark the items up as a list inside a {{htmlelement("nav")}} element, and then use CSS to display the layout visually as a row.

Typically, the pagination component will be centered horizontally underneath the content.

## Recipe

```html live-sample___pagination
<nav aria-label="pagination">
  <ul class="pagination">
    <li>
      <a href=""
        ><span aria-hidden="true">«</span
        ><span class="visuallyhidden">previous set of pages</span></a
      >
    </li>
    <li>
      <a href=""><span class="visuallyhidden">page </span>1</a>
    </li>
    <li>
      <a aria-current="page" href=""
        ><span class="visuallyhidden">page </span>2</a
      >
    </li>
    <li>
      <a href=""><span class="visuallyhidden">page </span>3</a>
    </li>
    <li>
      <a href=""><span class="visuallyhidden">page </span>4</a>
    </li>
    <li>
      <a href=""
        ><span class="visuallyhidden">next set of pages</span
        ><span aria-hidden="true">»</span></a
      >
    </li>
  </ul>
</nav>
```

```css live-sample___pagination
nav {
  display: flex;
  justify-content: center;
}

.pagination {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;
}

.pagination li {
  margin: 0 1px;
}
```

{{EmbedLiveSample("pagination")}}

> [!CALLOUT]
>
> [Download this example](https://github.com/mdn/css-examples/blob/main/css-cookbook/pagination--download.html)

## Choices made

This pattern is laid out using [flexbox](/en-US/docs/Web/CSS/CSS_flexible_box_layout) — one flex container nested inside another. The {{htmlelement("nav")}} element is designated a flex container in order that we can center the list inside using the {{cssxref("justify-content")}} property.

The list itself also becomes a flex container to lay the items out as a row. To space the items out we can either use a {{cssxref("margin")}} on the flex items or add a {{cssxref("gap")}} on the flex container.

```css
.pagination {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;
  gap: 2px;
}
```

## Accessibility concerns

We want to ensure that a person using a screen reader understands what this navigation does, and where they will go when clicking a link. To help with this we have added [`aria-label="pagination"`](/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-label) on the `<nav>` element.

We have also added some additional content that would be read by a screen reader but is hidden visually, and set the [`aria-hidden`](/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-hidden) attribute on the paging arrows.

The "See Also" section at the end of this document has links to related accessibility topics.

## See also

- {{Cssxref("justify-content")}}, {{Cssxref("gap")}}
- [Know your ARIA: 'hidden' vs 'none'](https://www.scottohara.me/blog/2018/05/05/hidden-vs-none.html) (2018)
- [Invisible content just for screen reader users](https://webaim.org/techniques/css/invisiblecontent/#techniques) via WebAIM.org (2020)
- [Writing CSS with accessibility in mind](https://medium.com/@matuzo/writing-css-with-accessibility-in-mind-8514a0007939) (2017)
- [a11y style guide: pagination](https://a11y-style-guide.com/style-guide/section-navigation.html#kssref-navigation-pagination)
