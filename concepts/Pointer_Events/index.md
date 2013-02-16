{{Page_Title|Pointer Events Primer}}
{{Flags
|High-level issues=Stub
|Content=Incomplete
|Editorial notes=Created page as a placeholder; will be populating later this afternoon.
}}
{{API_Name}}
{{Summary_Section|This document is written for web developers who have basic familiarity with [http://docs.webplatform.org/wiki/html HTML] and [http://docs.webplatform.org/wiki/javascript JavaScript].  This document should help you:
# Understand the end-user and web developer problems that Pointer Events address
# Easily add Pointer Events to an existing web page
# Take advantage of additional methods and attributes available in Pointer Events
# Find additional resources to learn more about Pointer Events
}}
{{Concept_Page
|Content=__TOC__

==1. WHY POINTER EVENTS==

===1.1 UNIFIED MODEL FOR MULTIPLE INPUT TYPES===
In the last few years, there has been an explosion of computing devices that use mechanisms other than a mouse for end user input.  These input mechanisms include touch as on a smartphone or pen/stylus as on a slate.  All of today’s web browsers support mouse events (mouseover, mousedown, mousemove, etc.) but many users aren’t using a mouse.  Today’s user may be interacting with a web page using their fingers on a smartphone while riding public transit or using a pen on a slate/tablet while in a meeting.  Pointer Events provides a unified model for all three of these input types without requiring web developers to write unique code for each.  And Pointer Events is intended to be forward compatible covering future interaction paradigms.

===1.2 ABILITY TO IDENTIFY DIFFERENT INPUT TYPES===
Most modern browsers such as the latest versions of Chrome, Firefox, Internet Explorer, Opera, and Safari all map touch or pen input to mouse events.  But this makes it hard to know if a mouse event is an actual mouse event or was synthetically generated from a touch or pen input event.  Pointer Events also includes attributes to identify which mouse or pen button(s) were pressed during the event.  

===1.3 ADDITIONAL METHODS AND ATTRIBUTES===
Finally, Pointer Events provides additional attributes such as touch contact geometry size, pressure, and pen tilt so that web developers can take advantage of these additional inputs in building experiences for end users.  And if web developers want, they can write unique code for each input type.


==2. BASIC POINTER EVENTS==
Pointer Events includes a number of basic events similar to mouse events:


===2.1 DOWN AND UP (WITH EXAMPLE)===
Pointer Events includes basic pointer down and pointer up events.  
* <code>pointerdown</code> is triggered when a user clicks a mouse button or touches the screen with a finger or pen.
* <code>pointerup</code> is triggered when a user releases a mouse button or releases their finger or pen from touching the screen. 
The below example shows how pointerdown and pointerup are similar to mousedown and mouseup:

<syntaxhighlight lang="html5">
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
    <title></title>
    <script type="text/javascript">
</syntaxhighlight>
<syntaxhighlight lang="javascript">
        function MouseDownResponse(event) {
            document.getElementById("dvMouseStatus").innerHTML += "Mouse Down<br />";
        }

        function MouseUpResponse(event) {
            document.getElementById("dvMouseStatus").innerHTML += "Mouse Up<br />";
        }

        function PointerDownResponse(event) {
            document.getElementById("dvPointerStatus").innerHTML +=
                "PointerId:" + event.pointerId +
                " of pointerType:" + event.pointerType + " Down<br />";
        }

        function PointerUpResponse(event) {
            document.getElementById("dvPointerStatus").innerHTML +=
                "PointerId:" + event.pointerId +
                " of pointerType:" + event.pointerType + " Up<br />";
        }

        function init() {
            document.addEventListener("mousedown", MouseDownResponse, false);
            document.addEventListener("mouseup", MouseUpResponse, false);

            document.addEventListener("pointerdown", PointerDownResponse, false);
            document.addEventListener("pointerup", PointerUpResponse, false);

            // Support for prefixed IE10 implementation
            document.addEventListener("MSPointerDown", PointerDownResponse, false);
            document.addEventListener("MSPointerUp", PointerUpResponse, false);
        }
</syntaxhighlight>
<syntaxhighlight lang="html5">
    </script>
</head>
<body onload="init()">
    <p>Click, touch, or tap</p>
    <table>
        <tr>
            <td style="vertical-align:top; width:30%;"><div id="dvMouseStatus"></div></td>
            <td style="vertical-align:top; width:40%;"><div id="dvPointerStatus"></div></td>
        </tr>
    </table>
</body>
</html>
</syntaxhighlight>


===2.2 MOVE (WITH EXAMPLE)===
Pointer Events also includes a basic move event.  The <code>pointermove</code> event is triggered when a user moves their mouse, finger, or pen.
Many devices with touch screens have default pan and zoom behaviors such as zooming for a double tap.  Web developers can disable these default behaviors with the <code>touch-action</code> CSS value of <code>none</code> as shown in the below example.  
The below example shows how <code>pointermove</code> is similar to <code>mousemove</code>:
<syntaxhighlight lang="html5">
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
    <title></title>
    <script type="text/javascript">
</syntaxhighlight>
<syntaxhighlight lang="javascript">
        function MouseMoveResponse(event) {
            document.getElementById("dvMouseStatus").innerHTML =
                "Mouse position: " + event.clientX + ", " + event.clientY + "<br />";
        }

        function PointerMoveResponse(event) {
            document.getElementById("dvPointerStatus").innerHTML =
                "PointerId:" + event.pointerId + " of pointerType:" + event.pointerType +
                " isPrimary:" + event.isPrimary +
                " position: " + event.clientX + ", " + event.clientY + "<br />";
        }

        function init() {
            document.addEventListener("mousemove", MouseMoveResponse, false);
            document.addEventListener("pointermove", PointerMoveResponse, false);

            // Support for prefixed IE10 implementation
            document.addEventListener("MSPointerMove", PointerMoveResponse, false);
        }
</syntaxhighlight>
<syntaxhighlight lang="html5">
    </script>
</head>
<body onload="init()" style="touch-action:none; -ms-touch-action:none;">
    <p>Move your mouse, finger, or pen</p>
    <table>
        <tr>
            <td style="vertical-align:top; width:30%;"><div id="dvMouseStatus"></div></td>
            <td style="vertical-align:top; width:40%;"><div id="dvPointerStatus"></div></td>
        </tr>
    </table>
</body>
</html>
</syntaxhighlight>
In addition to the basic x and y coordinates, <code>pointermove</code> includes <code>pointerId</code>, <code>pointerType</code>, and other attributes.


===2.3 OVER AND OUT (WITH EXAMPLE)===
Pointer Events includes basic pointer over and pointer out events.  
* <code>pointerover</code> is triggered when a user moves their mouse over an HTML element or touches it with their finger or pen. 
* <code>pointerout</code> is triggered when a user moves their mouse out of an HTML element, releases a finger or pen touch, or moves their finger our out of an HTML element while still touching the screen.
The below example shows how <code>pointerover</code> and <code>pointerout</code> are similar to <code>mouseover</code> and <code>mouseout</code>.
<syntaxhighlight lang="html5">
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
    <title></title>
    <script type="text/javascript">
</syntaxhighlight>
<syntaxhighlight lang="javascript">
        function MouseOverResponse(event) {
            document.getElementById("dvMouseStatus").innerHTML += "Mouse Over<br />";
        }

        function MouseOutResponse(event) {
            document.getElementById("dvMouseStatus").innerHTML += "Mouse Out<br />";
        }

        function PointerOverResponse(event) {
            document.getElementById("dvPointerStatus").innerHTML += "Pointer Over<br />";
        }

        function PointerOutResponse(event) {
            document.getElementById("dvPointerStatus").innerHTML += "Pointer Out<br />";
        }

        function init() {
            var dvObject = document.getElementById("dvObject");

            dvObject.addEventListener("mouseover", MouseOverResponse, false);
            dvObject.addEventListener("mouseout", MouseOutResponse, false);

            dvObject.addEventListener("pointerover", PointerOverResponse, false);
            dvObject.addEventListener("pointerout", PointerOutResponse, false);

            // Support for prefixed IE10 implementation
            dvObject.addEventListener("MSPointerOver", PointerOverResponse, false);
            dvObject.addEventListener("MSPointerOut", PointerOutResponse, false);
        }
</syntaxhighlight>
<syntaxhighlight lang="html5">
    </script>
</head>
<body onload="init()">
    <p>Move your mouse, finger, or pen/stylus over the yellow box</p>
    <div id="dvObject" style="float:right; background-color:yellow; height:100px; width:200px;">
    </div>
    <table>
        <tr>
            <td style="vertical-align:top; width:30%;"><div id="dvMouseStatus"></div></td>
            <td style="vertical-align:top; width:40%;"><div id="dvPointerStatus"></div></td>
        </tr>
    </table>
</body>
</html>
</syntaxhighlight>


===2.4 ENTER AND LEAVE (WITH EXAMPLE)===
Pointer Events includes basic pointer enter and pointer leave events.  Enter and leave events are similar to over and out events described in the previous section but with some exceptions including that they do not bubble.  
* <code>pointerenter</code> is triggered when a user moves their mouse over an HTML element or touches it with their finger or pen.
* <code>pointerleave</code> is triggered when a user moves their mouse out of an HTML element, releases a finger or pen touch, or moves their finger our out of an HTML element while still touching the screen.
The below example shows how <code>pointerenter</code> and <code>pointerleave</code> are similar to <code>mouseenter</code> and <code>mouseleave</code>.
<syntaxhighlight lang="html5">
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
    <title></title>
    <script type="text/javascript">
</syntaxhighlight>
<syntaxhighlight lang="javascript">
        function MouseEnterResponse(event) {
            document.getElementById("dvMouseStatus").innerHTML += "Mouse Enter<br />";
        }

        function MouseLeaveResponse(event) {
            document.getElementById("dvMouseStatus").innerHTML += "Mouse Leave<br />";
        }

        function PointerEnterResponse(event) {
            document.getElementById("dvPointerStatus").innerHTML += "Pointer Enter<br />";
        }

        function PointerLeaveResponse(event) {
            document.getElementById("dvPointerStatus").innerHTML += "Pointer Leave<br />";
        }

        function init() {
            var dvObject = document.getElementById("dvObject");

            dvObject.addEventListener("mouseenter", MouseEnterResponse, false);
            dvObject.addEventListener("mouseleave", MouseLeaveResponse, false);

            dvObject.addEventListener("pointerenter", PointerEnterResponse, false);
            dvObject.addEventListener("pointerleave", PointerLeaveResponse, false);
        }
</syntaxhighlight>
<syntaxhighlight lang="html5">
    </script>
</head>
<body onload="init()">
    <p>Move your mouse, finger, or pen/stylus over the orange box</p>
    <div id="dvObject" style="float:right; background-color:orange; height:100px; width:200px;">
    </div>
    <table>
        <tr>
            <td style="vertical-align:top; width:30%;"><div id="dvMouseStatus"></div></td>
            <td style="vertical-align:top; width:40%;"><div id="dvPointerStatus"></div></td>
        </tr>
    </table>
</body>
</html>
</syntaxhighlight>


===2.5 CANCEL===
In the modern world of desktop PC’s with multiple monitors or smartphones and slates supporting multiple orientations, there are cases where a pointer is down and the next event should be a <code>pointercancel</code> event; rather than a <code>pointerup</code> event.  These include:
* A user changes the position of a screen in a multi-screen configuration
* A user changes the orientation of a screen (i.e. rotate from portrait to landscape)
* A user exceeds the number of simultaneous contacts a device can support
* A user locks their device or logs-off
In all of these cases, a <code>pointercancel</code> event is triggered.  This gives the developer a chance to handle any clean-up that is needed.  More information on <code>pointercancel</code> cases can be found at: http://msdn.microsoft.com/en-us/library/ie/hh846776(v=vs.85).aspx 


===2.6 COMPARISON OF MOUSE EVENTS AND POINTER EVENTS===
The below table lists Mouse Events and the related Pointer Events:
<table>
<tr><th>Mouse Event</th><th>Pointer Event</th><th>(Prefixed) IE10 Pointer Event</th></tr>
<tr><td>mousedown</td><td>pointerdown</td><td>MSPointerDown</td></tr>
<tr><td>mouseup</td><td>pointerup</td><td>MSPointerUp</td></tr>
<tr><td>mousemove</td><td>pointermove</td><td>MSPointerMove</td></tr>
<tr><td>mouseover</td><td>pointerover</td><td>MSPointerOver</td></tr>
<tr><td>mouseout</td><td>pointerout</td><td>MSPointerOut</td></tr>
<tr><td>mouseenter</td><td>pointerenter</td><td>(none)</td></tr>
<tr><td>mouseleave</td><td>pointerleave</td><td>(none)</td></tr>
<tr><td>(none)</td><td>pointercancel</td><td>MSPointerCancel</td></tr>
</table>


== 3 POINTER EVENT ATTRIBUTES==
Pointer Events have a number of additional attributes that enable you as a web developer to enhance your interactions:

===3.1 POINTERTYPE===
The <code>pointerType</code> attribute tells you if a pointer is a mouse, a touch, a pen, or some new future pointer type. Use of the <code>pointerType</code> attribute was shown in the earlier examples for <code>pointerdown</code>, <code>pointerup</code>, and <code>pointermove</code>.  As a best practice, if you are writing code that behaves uniquely for different <code>pointerType</code> values you should make sure to also handle a new future pointer type.  

===3.2 POINTERID===
The <code>pointerId</code> attribute tells you which pointer you’re interacting with.  The mouse always has a <code>pointerId</code> of 1, and touch and pen pointers have integer <code>pointerId</code> values that are not 1.  




[[File:TiltX.png|alt=Image showing positive TiltX]]
}}
{{Examples_Section
|Not_required=Yes
|Examples=
}}
{{Notes_Section}}
{{Related_Specifications_Section
|Specifications={{Related Specification
|Name=Pointer Events
|URL=http://www.w3.org/TR/pointerevents/
|Status=Working Draft
}}
}}
{{See_Also_Section}}
{{Topics|DOM, DOMEvents, Touch}}
{{External_Attribution
|Is_CC-BY-SA=No
|MDN_link=
|MSDN_link=
|HTML5Rocks_link=
}}