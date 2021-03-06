---
title: 'dragenter'
attributions:
  - 'Microsoft Developer Network: [[Windows Internet Explorer API reference](http://msdn.microsoft.com/en-us/library/ie/hh828809%28v=vs.85%29.aspx) Article]'
code_samples:
  - 'http://samples.msdn.microsoft.com/workshop/samples/author/dhtml/refs/DragDropEventsEX.htm'
notes:
  - 'Needs summary, specs, and compat'
readiness: 'In Progress'
tags:
  - Events
  - DOM
  - Needs_Summary
uri: dom/DragEvent/dragenter

---
## Overview Table

<table class="wikitable">
<tr>
<th>
Synchronous

</th>
<td>
No

</td>
</tr>
<tr>
<th>
Bubbles

</th>
<td>
No

</td>
</tr>
<tr>
<th>
Target

</th>
<td>
dom/Element

</td>
</tr>
<tr>
<th>
Cancelable

</th>
<td>
No

</td>
</tr>
<tr>
<th>
Default action

</th>
<td>
 ?

</td>
</tr>
</table>
## Examples

This example shows when and where each event fires during a drag-and-drop operation by listing each event and the name of the object firing it in a list box.

``` html
<HEAD>
<SCRIPT>
// Code for dynamically adding options to a select.
function ShowResults()
{               // Information about the events
                 // and what object fired them.
  arg = event.type + "  fired by  " + event.srcElement.id;
  var oNewOption = new Option();
  oNewOption.text = arg;
  oResults.add(oNewOption,0);
}
</SCRIPT>
</HEAD>
<BODY>
<P>Source events are wired up to this text box.</P>
<INPUT ID=txtDragOrigin VALUE="Text to Drag"
    ondragstart="ShowResults()"
    ondrag="ShowResults()"
    ondragend="ShowResults()"
>
<P>Target events are bound to this text box.</P>
<INPUT ID=txtDragDestination VALUE="Drag Destination"
    ondragenter="ShowResults()"
    ondragover="ShowResults()"
    ondragleave="ShowResults()"
    ondrop="ShowResults()"
>
<SELECT ID=oResults SIZE=30>
  <OPTION>List of Events Fired
</SELECT>
</BODY>
```

[View live example](http://samples.msdn.microsoft.com/workshop/samples/author/dhtml/refs/DragDropEventsEX.htm)

## Notes

### Remarks

You can handle the **ondragenter** event on the source or on the target object. Of the target events, it is the first to fire during a drag operation. Target events use the [**getData**](/dom/DataTransfer/getData) method to stipulate which data and data formats to retrieve. The list of drag-and-drop target events includes:

-   [**beforepaste**](/dom/Event/beforepaste)
-   [**paste**](/dom/Element/paste)
-   [**dragover**](/dom/DragEvent/dragover)
-   [**dragleave**](/dom/DragEvent/dragleave)
-   [**ondrop**](/dom/DragEvent/drop)

When scripting custom functionality, use the [**returnValue**](/dom/BeforeUnloadEvent/returnValue) property to disable the default action. Calls the associated event handler. To invoke this event, do one of the following:

-   Drag the selection over a valid drop target within the client.
-   Drag the selection to a valid drop target within another window.

### Syntax

### Standards information

There are no standards that apply here.

### Event handler parameters

*pEvtObj* [in]
:   Type: ****IHTMLEventObj****
