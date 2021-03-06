---
title: 'spellcheck'
attributions:
  - 'Microsoft Developer Network: [[Windows Internet Explorer API reference](http://msdn.microsoft.com/en-us/library/ie/hh828809%28v=vs.85%29.aspx) Article]'
notes:
  - 'summary, examples, clean-up MSDN import'
readiness: 'Not Ready'
relationships:
  applies_to:
    predicate: 'Property of '
    value: dom/HTMLElement
    href: /dom/HTMLElement
tags:
  - API_Object_Properties
  - DOM
  - Needs_Summary
  - Needs_Examples
uri: dom/HTMLElement/spellcheck

---
Property of [dom/HTMLElement](/dom/HTMLElement)[dom/HTMLElement](/dom/HTMLElement)

## Syntax

``` js
var result = element.spellcheck;
element.spellcheck = value;
```

## Notes

### Remarks

Spellcheck is only enabled by default for **textArea** elements, and elements with the [**contentEditable**](/html/attributes/contentEditable) = true attribute for Internet Explorer 10. Spellcheck is off by default for **input type=text**.

You can enable spellchecking by adding the **spellcheck=true** attribute to the root or ancestor markup of the content (including the \<html\> element), with no other special flags needed.

There is also a default state (missing attribute) which uses the element's default behavior, such as inheriting from the parent element's spellcheck state.

### Syntax

## See also

### Related pages

-   HTMLElement[HTMLElement](/dom/HTMLElement)
