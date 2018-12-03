---
title: csv
header&lowbar;icon: /assets/images/icons/icn-documentation.svg
header&lowbar;title: csv
breadcrumbs:
  Files types list: /files
---
#csv

####Feature support list
- Segmentation support: `Yes`
- Reference in CE (file comments): We pull the Key content
- DNM behavior: Keep original value
- Content&lowbar;type API Endpoint: csv

**Classic RFC version of CSV**

Resources

- [CSV RFC](http://www.ietf.org/rfc/rfc4180.txt)

 

####Keys Management


|  file name |  View Key |  Adding Key |  Delete Key |  Edit Key |  
| --| --| --| --| --| 
|  CSV |   ✅ |  ❌|  ❌|  ❌| 

####Integration Support 

|  file name |  CLI |  API |  GitHub |  BitBucket |  
| --| --| --| --| --| 
|  CSV |   ✅ |  ✅|  ✅|  ✅| 


####Variables Rules

| regex approximation of variable matcher |  Variable example |  Status | 
|--|-- |-- | 
| %% | 	%%| 	❌	| 
| %&lowbar;(.*)&lowbar;%	| %&lowbar;variable&lowbar;%	|  ❌	| 
| &bsol;&bsol;n	| &bsol;n	| ✅	| 
| &lt;(/&lbrace;0,1&#125;)([a-z]*:)*[a-z]+ (.*)&gt; |  &lt;span&gt; | 	✅	| 
| &lt;(/&lbrace;0,1&#125;)([a-z]*:)*[a-z]+ (.*)&gt; |  	&lt;span&gt;	| ✅	| 
| &amp;amp; | 	&amp;amp;	|  ✅	| 
| &amp;nbsp;| 	 &amp;nbsp;	| 	✅| 
| &amp;gt;	| &amp;gt;	| 	✅| 
| &amp;lt;	| &amp;lt;	| 	✅| 
| &amp;copy;	| &amp;copy;	| 	✅| 
| &amp;ndsh;| 	&amp;ndsh;	| 	✅| 
| &amp;laquo;| 	&amp;laquo;	| 	✅| 
| &amp;raquo;	| &amp;raquo;	| 	✅| 
| &dollar;([a-z])&bsol;((.*)&bsol;)	| &dollar;i(variable)	|	✅| 
| &dollar;([a-z])| 	&dollar;i	| 	✅| 
| %#@(.*)@	| %#@variable@	| 	✅| 
| %([0-9])&dollar;#@(.*)@	| %1&dollar;#@variable@	| 	✅| 
| %&bsol;&lbrace;&bsol;&lbrace;(.*)&bsol;&#125;&bsol;&#125;| 	%&lbrace;&lbrace;variable&#125;&#125;	| 	✅| 
|  #&bsol;&lbrace;&bsol;&lbrace;(.*)&bsol;&#125;&bsol;&#125;| 	#&lbrace;&lbrace;variable&#125;&#125;	|	✅| 
|  %&bsol;&lbrace;(.*)&bsol;&#125;	| %&lbrace;variable&#125;	| 	✅| 
|  &dollar;&bsol;&lbrace;(.*)&bsol;&#125;	| &dollar;&lbrace;variable&#125;	| 	✅| 
|  &bsol;&lbrace;&bsol;&lbrace;(.*)&bsol;&#125;&bsol;&#125;| 	&lbrace;&lbrace;variable&#125;&#125;	| 	✅| 
|  &bsol;&lbrace;(.*)&bsol;&#125;	| &lbrace;variable&#125;	| 	✅| 
| &quot;%&bsol;&lbrace;(.*)&bsol;&#125;&	| v&quot;%&lbrace;variable&#125;&quot;	| 	✅| 
| %&bsol;((.*)&bsol;)	| %(variable)	| 	✅| 
| %([a-z]+)%	| %variable%	| 	✅| 
| %([a-z])| 	%a	| 	✅| 
| &bsol;(%([a-z])&bsol;)	| (%a)	| 	✅| 
| &bsol;[&bsol;[(.*)&bsol;]&bsol;]	|  [[variable]]	| 	✅| 
| &bsol;[(.*)&bsol;]&bsol;([:url:]&bsol;)	|  [google&rbrack;(google.com)	| ❌	| 
| &bsol;[(.*)&bsol;]&bsol;[(.*)&bsol;]	|  [google&rbrack;[google-ref&rbrack; | 	❌	| 
| &bsol;[(.*)&bsol;]	| [google-ref]	| 	✅| 
| &lt;!&bsol;[CDATA&bsol;[| 	&lt;![CDATA[	| 	✅| 
| &bsol;]&bsol;]&gt;	|  ]]&gt;	| 	✅| 
| &lt;bpt(.*)&lt;/bpt&gt;	| &lt;bpt&gt; text &lt;/bpt&gt;	| 	✅| 
| &lt;ept(.*)&lt;/ept&gt;	| &lt;ept&gt; text &lt;/ept&gt;	| 	✅| 
|  &lt;(/?)([a-z]*:)*[a-z]+ (.*)&gt;| 	&lt;span&gt;		| ✅| 
|  %[0-9]&dollar;(0&verbar;1)?([sSdDuUxoOfeEgGcCpaAFlL@]) | 	%1&dollar;0s <br/>%1&dollar;s	|  ❌	| 
| %([sSdDuUxoOfeEgGcCpaAFlL@])	| %s| 	❌| 
| %[0-9]&dollar;(s&verbar;d)	|  %0&dollar;s	| 	✅| 
| &dollar;&lowbar;([a-z])| 	&dollar;&lowbar;a	| 	✅| 
| %@!	|  %@!	| 	✅| 
| %@	|  %@	| 	✅| 
|  /&bsol;&bsol;u([a-z]&lbrace;4&#125;)/| 	/&bsol;uaadf/	| 	✅| 
|  &bsol;&bsol;u([a-z]&lbrace;4&#125;)| 	&bsol;uaadf		| ✅| 
| &ast;&ast;&ast;(.&ast;)&ast;&ast;&ast;	| &ast;&ast;&ast;variable&ast;&ast;&ast;| 	❌	| 
| &lowbar;&lowbar;&lowbar;(.&ast;)&lowbar;&lowbar;&lowbar;	| &lowbar;&lowbar;&lowbar;variable&lowbar;&lowbar;&lowbar;	| ❌	| 
| &ast;&ast;(.&ast;)&ast;&ast;| 	&ast;&ast;variable&ast;&ast;	| ❌	| 
| &lowbar;&lowbar;(.&ast;)&lowbar;&lowbar;| 	&lowbar;&lowbar;variable&lowbar;&lowbar;	| ❌	| 
| &#126;(.&ast;)&#126;	| &#126;variable&#126;	| ❌	| 
| &ast;&verbar;(.&ast;)&verbar;&ast; | 	&ast;&verbar;variable&verbar;&ast;	| 	✅| 
| &ast;(.&ast;)&ast;	|  &ast;variable&ast;	| ❌	| 
| &lowbar;(.&ast;)&lowbar; | 	&lowbar;variable&lowbar;	| ❌| 
