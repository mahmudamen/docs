---
title: 'tagUrn'
attributions:
  - 'Microsoft Developer Network: [[Windows Internet Explorer API reference](http://msdn.microsoft.com/en-us/library/ie/hh828809%28v=vs.85%29.aspx) Article]'
code_samples:
  - 'http://samples.msdn.microsoft.com/workshop/samples/author/dhtml/refs/tagUrn.htm'
notes:
  - 'summary, clean-up MSDN import'
readiness: 'In Progress'
relationships:
  applies_to:
    predicate: 'Property of '
    value: dom/HTMLElement
    href: /dom/HTMLElement
tags:
  - API_Object_Properties
  - DOM
  - Needs_Summary
uri: dom/HTMLElement/tagUrn

---
Property of [dom/HTMLElement](/dom/HTMLElement)[dom/HTMLElement](/dom/HTMLElement)

## Syntax

``` js
var result = element.tagUrn;
element.tagUrn = value;
```

## Examples

This example uses the values returned by the **scopeName** and **tagUrn** properties to create a simple HelloWorld custom tag.

The browser's status bar displays the property values.

**Note**  For IE8Standards mode to render correctly, make sure there is no spaces in your call to the HTC file.

``` html
<HTML XMLNS:InetSDK='http://msdn.microsoft.com/workshop'>

<STYLE>
@media all {
   InetSDK\:HelloWorld { behavior:url(simple.htc) }
}
</STYLE>
<SCRIPT>
   function window.onload()
   {
      window.status = 'scopeName = ' + hello.scopeName +
                      '; tagUrn = '  + hello.tagUrn;
   }
</SCRIPT>
<BODY>
   <InetSDK:HelloWorld ID='hello'></InetSDK:HelloWorld>

</BODY>
</HTML>
```

[View live example](http://samples.msdn.microsoft.com/workshop/samples/author/dhtml/refs/tagUrn.htm)

An alternative call to the HTC can also be made as an attribute, as shown in the following code example.

``` html
<HTML XMLNS:InetSDK='http://msdn.microsoft.com/workshop'>

<SCRIPT>
   function window.onload()
   {
      window.status = 'scopeName = ' + hello.scopeName +
                      '; tagUrn = '  + hello.tagUrn;
   }
</SCRIPT>
<BODY>
   <InetSDK:HelloWorld ID='hello' style="behavior:url(simple.htc)"></InetSDK:HelloWorld>

</BODY>
</HTML>
```

[**Note**  Make sure there are no spaces in your style's declaration. View live example]

## Notes

### Remarks

To declare the namespace in the document, use the [**XMLNS**](/apis/xhr/properties/XMLNS_attribute) attribute of the **html** element. Download the HTC for the sample below: [simple.htc](http://go.microsoft.com/fwlink/p/?linkid=203827)

### Syntax
