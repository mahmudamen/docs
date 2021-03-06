---
title: 'aria-labelledby'
attributions:
  - 'Microsoft Developer Network: [[Windows Internet Explorer API reference](http://msdn.microsoft.com/en-us/library/ie/hh828809%28v=vs.85%29.aspx) Article]'
compatibility:
  feature: aria-labelledby
  topic: aria
notes:
  - 'Needs summary, example, spec reference, standardization status'
readiness: 'Not Ready'
tags:
  - Markup_Attributes
  - ARIA
  - Needs_Summary
  - Needs_Examples
uri: aria/attributes/aria-labelledby

---
<table class="wikitable">
<tr>
<th>
Applies to

</th>
<td>
</td>
</tr>
</table>
## Notes

### Remarks

<table class="wikitable">
<tr>
<th>
Used in Roles

</th>
<td>
<dl>

<dt>
No role required.

</dt>
</dl>
</td>
</tr>
</table>
  One or more [**id**](/html/attributes/id) properties may be specified. A list of **id** properties is returned by Microsoft UI Automation. In addition to providing the **ariaLabelledby** property, you should also use a **label** element to indicate a label for previous versions of the browser.

**Note**  For cross-browser compatibility, always use the WAI-ARIA attribute syntax to access and modify ARIA properties, for example `object.setAttribute("aria-valuenow", newValue)`. If more than one [**id**](/html/attributes/id) is specified, only the first id is recognized by Windows Internet Explorer 8. **Note**  Recursive use of **ariaLabelledby** is not supported. An element that is using **ariaLabelledby** should not reference another element that is also using **ariaLabelledby**.

### Syntax

### Standards information

-   [Accessible Rich Internet Applications (WAI-ARIA) 1.0](http://go.microsoft.com/fwlink/p/?linkid=203793), Section 6.6

## See also

### Related pages

-   Accessible Rich Internet Applications (ARIA)[Accessible Rich Internet Applications (ARIA)](/aria)
-   `Reference`
-   aria-controls[aria-controls](/aria/attributes/aria-controls)
-   aria-flowto[aria-flowto](/aria/attributes/aria-flowto)
-   aria-describedby[aria-describedby](/aria/attributes/aria-describedby)
-   aria-owns[aria-owns](/aria/attributes/aria-owns)
-   aria-posinset[aria-posinset](/aria/attributes/aria-posinset)
-   aria-setsize[aria-setsize](/aria/attributes/aria-setsize)
