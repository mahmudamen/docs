{{Page_Title}}
{{Flags
|State=Not Ready
|Editorial notes=Deletion candidate; deprecated function
|Checked_Out=No
}}
{{Summary_Section|'''Deprecated'''

The deprecated '''unescape()''' function decodes a string that is usually encoded with the '''escape''' function.
}}
{{JS_Syntax
|Formats={{JS Syntax Format
|Format=unescape(str)
}}
|Values={{JS Syntax Parameter
|Name=str
|Required=Required
|Description=A String to be decoded
}}
}}
{{JS_Return_Value
|Description=
}}
{{Examples_Section
|Not_required=No
|Examples={{Single Example
|Language=JavaScript
|Description=
|Code=unescape("webplatform"); // "webplatform"
unescape("%FCmlaut"); // "ümlaut"
unescape("%u65E5%u672C%u8A9E"); // "日本語"
|LiveURL=
}}
}}
{{Remarks_Section
|Remarks=All characters encoded with the % xx hexadecimal form are replaced by their ASCII character set equivalents.

Characters encoded in '''%u''' xxxx format (Unicode characters) are replaced with the Unicode character with hexadecimal encoding xxxx.
}}
{{Notes_Section
|Usage=
|Notes=Do not use the '''unescape''' function to decode URIs. Use [[javascript/decodeURI{{!}}decodeURI]] and 
[[javascript/decodeURIComponent{{!}}decodeURIComponent]] functions instead.
|Import_Notes=This function is deprecated and not recommended for use in new projects. Use with caution.
}}
{{JS Object Listing}}

{{See_Also_Section
|Topic_clusters=Deprecated
|Manual_links=* [[javascript/decodeURI{{!}}decodeURI Function]]
* [[javascript/decodeURIComponent{{!}}decodeURIComponent Function]]
* [[javascript/escape{{!}}escape Function]]
* [[javascript/String{{!}}String Object]]
|External_links=
|Manual_sections=
}}
{{JS Topics
|JS Page Type=JS Function
|Applies to=String
}}
{{External_Attribution
|Is_CC-BY-SA=No
|Sources=MSDN
|MDN_link=
|MSDN_link=http://msdn.microsoft.com/en-us/library/ie/dz4x90hk(v=vs.94).aspx
|HTML5Rocks_link=
}}