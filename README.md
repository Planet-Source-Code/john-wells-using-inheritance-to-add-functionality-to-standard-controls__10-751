<div align="center">

## Using Inheritance to add functionality to standard controls


</div>

### Description

This article will help you learn to use Inheritance to extend other classes and add functionality to the standard controls shipped with .NET
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[John Wells](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/john-wells.md)
**Level**          |Beginner
**User Rating**    |4.8 (19 globes from 4 users)
**Compatibility**  |VB\.NET
**Category**       |[Controls/ Forms/ Dialogs/ Menus](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/controls-forms-dialogs-menus__10-3.md)
**World**          |[\.Net \(C\#, VB\.net\)](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/net-c-vb-net.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/john-wells-using-inheritance-to-add-functionality-to-standard-controls__10-751/archive/master.zip)





### Source Code

```
<html xmlns:o="urn:schemas-microsoft-com:office:office"
xmlns:w="urn:schemas-microsoft-com:office:word"
xmlns="http://www.w3.org/TR/REC-html40">
<head>
<meta http-equiv=Content-Type content="text/html; charset=windows-1252">
<meta name=ProgId content=Word.Document>
<meta name=Generator content="Microsoft Word 9">
<meta name=Originator content="Microsoft Word 9">
<link rel=File-List href="./Inheritance_files/filelist.xml">
<title>Inheritance: It’s more than money</title>
<!--[if gte mso 9]><xml>
 <o:DocumentProperties>
 <o:Author>John Wells</o:Author>
 <o:LastAuthor>John Wells</o:LastAuthor>
 <o:Revision>1</o:Revision>
 <o:TotalTime>18</o:TotalTime>
 <o:Created>2002-11-27T14:19:00Z</o:Created>
 <o:LastSaved>2002-11-27T14:37:00Z</o:LastSaved>
 <o:Pages>2</o:Pages>
 <o:Words>410</o:Words>
 <o:Characters>2342</o:Characters>
 <o:Lines>19</o:Lines>
 <o:Paragraphs>4</o:Paragraphs>
 <o:CharactersWithSpaces>2876</o:CharactersWithSpaces>
 <o:Version>9.6926</o:Version>
 </o:DocumentProperties>
</xml><![endif]--><!--[if gte mso 9]><xml>
 <w:WordDocument>
 <w:AttachedTemplate
  HRef="C:\Documents and Settings\Johnny\Application Data\Microsoft\Templates\Normal.dot"></w:AttachedTemplate>
 </w:WordDocument>
</xml><![endif]-->
<style>
<!--
 /* Font Definitions */
@font-face
	{font-family:"Lucida Console";
	panose-1:2 11 6 9 4 5 4 2 2 4;
	mso-font-charset:0;
	mso-generic-font-family:modern;
	mso-font-pitch:fixed;
	mso-font-signature:-2147482993 6144 0 0 31 0;}
 /* Style Definitions */
p.MsoNormal, li.MsoNormal, div.MsoNormal
	{mso-style-parent:"";
	margin:0in;
	margin-bottom:.0001pt;
	mso-pagination:widow-orphan;
	font-size:12.0pt;
	font-family:"Times New Roman";
	mso-fareast-font-family:"Times New Roman";}
@page Section1
	{size:8.5in 11.0in;
	margin:1.0in 1.25in 1.0in 1.25in;
	mso-header-margin:.5in;
	mso-footer-margin:.5in;
	mso-paper-source:0;}
div.Section1
	{page:Section1;}
 /* List Definitions */
@list l0
	{mso-list-id:134220155;
	mso-list-type:hybrid;
	mso-list-template-ids:-161831798 226128278 67698713 67698715 67698703 67698713 67698715 67698703 67698713 67698715;}
@list l0:level1
	{mso-level-text:%1-;
	mso-level-tab-stop:.5in;
	mso-level-number-position:left;
	text-indent:-.25in;}
ol
	{margin-bottom:0in;}
ul
	{margin-bottom:0in;}
-->
</style>
</head>
<body lang=EN-US style='tab-interval:.5in'>
<div class=Section1>
<p class=MsoNormal>Inheritance: It’s more than money!</p>
<p class=MsoNormal><![if !supportEmptyParas]>&nbsp;<![endif]><o:p></o:p></p>
<p class=MsoNormal>So you’ve heard about inheritance in .NET and how big and
important a topic that is, I’m sure.<span style="mso-spacerun: yes"> 
</span>You have, right?<span style="mso-spacerun: yes">  </span>Well, if you
have not, it’s huge, and it’s here to solve all your problems.<span
style="mso-spacerun: yes">  </span>Okay, not all, but quite a few….</p>
<p class=MsoNormal><![if !supportEmptyParas]>&nbsp;<![endif]><o:p></o:p></p>
<p class=MsoNormal>I recently came against something I needed to fix, and here’s
how I did it.</p>
<p class=MsoNormal><![if !supportEmptyParas]>&nbsp;<![endif]><o:p></o:p></p>
<p class=MsoNormal>Problem: I was weaned into programmer hood judiciously using
the Tag properties of everything I came into contact with.<span
style="mso-spacerun: yes">  </span>I’d store unique identifiers, names,
numbers, any and everything. <span style="mso-spacerun: yes"> </span>Well,
Microsoft has decided to leave the Tag property out of it’s MenuItem control,
which kinda slowed me down for a second.<span style="mso-spacerun: yes"> 
</span>You see, I have added dynamic menus to the Inbox application you may
have seen on PSC, but I need to determine (by looking at a GUID) which menu
item was clicked so I could do some stuff to the correct object.<span
style="mso-spacerun: yes">  </span>No tag? There’s nowhere to store a GUID
value in a MenuItem control!</p>
<p class=MsoNormal><![if !supportEmptyParas]>&nbsp;<![endif]><o:p></o:p></p>
<p class=MsoNormal>Solution: Not the best, not the only, but a certifiably
sound one that was perfect for my problem.<span style="mso-spacerun: yes"> 
</span>You could also make an array of items, keep track of references, or any
number of ways, but the quick and firm solution here for me was to create a new
MenuItem control, but add a Tag property to it.</p>
<p class=MsoNormal><![if !supportEmptyParas]>&nbsp;<![endif]><o:p></o:p></p>
<p class=MsoNormal>Here’s what you do:</p>
<p class=MsoNormal><![if !supportEmptyParas]>&nbsp;<![endif]><o:p></o:p></p>
<p class=MsoNormal style='margin-left:.25in'>Make a new file, and add this code
to it</p>
<p class=MsoNormal><![if !supportEmptyParas]>&nbsp;<![endif]><o:p></o:p></p>
<p class=MsoNormal style='mso-layout-grid-align:none;text-autospace:none'><span
style='font-size:9.0pt;font-family:"Lucida Console";color:blue'>Namespace</span><span
style='font-size:9.0pt;font-family:"Lucida Console"'> jwells<o:p></o:p></span></p>
<p class=MsoNormal style='mso-layout-grid-align:none;text-autospace:none'><span
style='font-size:9.0pt;font-family:"Lucida Console"'><span style="mso-spacerun:
yes">    </span><span style='color:blue'>Public</span> <span style='color:blue'>Class</span>
MenuItemEx<o:p></o:p></span></p>
<p class=MsoNormal style='mso-layout-grid-align:none;text-autospace:none'><span
style='font-size:9.0pt;font-family:"Lucida Console"'><span style="mso-spacerun:
yes">        </span><span style='color:blue'>Inherits</span>
Windows.Forms.MenuItem<o:p></o:p></span></p>
<p class=MsoNormal style='mso-layout-grid-align:none;text-autospace:none'><span
style='font-size:9.0pt;font-family:"Lucida Console"'><![if !supportEmptyParas]>&nbsp;<![endif]><o:p></o:p></span></p>
<p class=MsoNormal style='mso-layout-grid-align:none;text-autospace:none'><span
style='font-size:9.0pt;font-family:"Lucida Console"'><span style="mso-spacerun:
yes">        </span><span style='color:blue'>Private</span> m_strTag <span
style='color:blue'>As</span> <span style='color:blue'>String<o:p></o:p></span></span></p>
<p class=MsoNormal style='mso-layout-grid-align:none;text-autospace:none'><span
style='font-size:9.0pt;font-family:"Lucida Console";color:blue'><![if !supportEmptyParas]>&nbsp;<![endif]><o:p></o:p></span></p>
<p class=MsoNormal style='mso-layout-grid-align:none;text-autospace:none'><span
style='font-size:9.0pt;font-family:"Lucida Console"'><span style="mso-spacerun:
yes">        </span><span style='color:blue'>Public</span> <span
style='color:blue'>Property</span> Tag() <span style='color:blue'>As</span> <span
style='color:blue'>String<o:p></o:p></span></span></p>
<p class=MsoNormal style='mso-layout-grid-align:none;text-autospace:none'><span
style='font-size:9.0pt;font-family:"Lucida Console"'><span style="mso-spacerun:
yes">            </span><span style='color:blue'>Get<o:p></o:p></span></span></p>
<p class=MsoNormal style='mso-layout-grid-align:none;text-autospace:none'><span
style='font-size:9.0pt;font-family:"Lucida Console"'><span style="mso-spacerun:
yes">                </span><span style='color:blue'>Return</span> m_strTag<o:p></o:p></span></p>
<p class=MsoNormal style='mso-layout-grid-align:none;text-autospace:none'><span
style='font-size:9.0pt;font-family:"Lucida Console"'><span style="mso-spacerun:
yes">            </span><span style='color:blue'>End</span> <span
style='color:blue'>Get<o:p></o:p></span></span></p>
<p class=MsoNormal style='mso-layout-grid-align:none;text-autospace:none'><span
style='font-size:9.0pt;font-family:"Lucida Console"'><span style="mso-spacerun:
yes">            </span><span style='color:blue'>Set</span>(<span
style='color:blue'>ByVal</span> Value <span style='color:blue'>As</span> <span
style='color:blue'>String</span>)<o:p></o:p></span></p>
<p class=MsoNormal style='mso-layout-grid-align:none;text-autospace:none'><span
style='font-size:9.0pt;font-family:"Lucida Console"'><span style="mso-spacerun:
yes">                </span>m_strTag = Value<o:p></o:p></span></p>
<p class=MsoNormal style='mso-layout-grid-align:none;text-autospace:none'><span
style='font-size:9.0pt;font-family:"Lucida Console"'><span style="mso-spacerun:
yes">            </span><span style='color:blue'>End</span> <span
style='color:blue'>Set<o:p></o:p></span></span></p>
<p class=MsoNormal style='mso-layout-grid-align:none;text-autospace:none'><span
style='font-size:9.0pt;font-family:"Lucida Console"'><span style="mso-spacerun:
yes">        </span><span style='color:blue'>End</span> <span style='color:
blue'>Property<o:p></o:p></span></span></p>
<p class=MsoNormal style='mso-layout-grid-align:none;text-autospace:none'><span
style='font-size:9.0pt;font-family:"Lucida Console"'><span style="mso-spacerun:
yes">    </span><span style='color:blue'>End</span> <span style='color:blue'>Class<o:p></o:p></span></span></p>
<p class=MsoNormal style='mso-layout-grid-align:none;text-autospace:none'><span
style='font-size:9.0pt;font-family:"Lucida Console";color:blue'>End</span><span
style='font-size:9.0pt;font-family:"Lucida Console"'> <span style='color:blue'>Namespace<o:p></o:p></span></span></p>
<p class=MsoNormal><![if !supportEmptyParas]>&nbsp;<![endif]><o:p></o:p></p>
<p class=MsoNormal>Simple enough!</p>
<p class=MsoNormal><![if !supportEmptyParas]>&nbsp;<![endif]><o:p></o:p></p>
<p class=MsoNormal>Why did we do that? Well, now when we add a ‘MenuItemEx’
control, it looks like this:</p>
<p class=MsoNormal><![if !supportEmptyParas]>&nbsp;<![endif]><o:p></o:p></p>
<p class=MsoNormal style='mso-layout-grid-align:none;text-autospace:none'><span
style='font-size:9.0pt;font-family:"Lucida Console"'><span style="mso-spacerun:
yes">            </span><span style='color:green'>'Add the item<o:p></o:p></span></span></p>
<p class=MsoNormal style='mso-layout-grid-align:none;text-autospace:none'><span
style='font-size:9.0pt;font-family:"Lucida Console"'><span style="mso-spacerun:
yes">            </span><span style='color:blue'>Dim</span> ctxItem <span
style='color:blue'>As</span> <span style='color:blue'>New</span> jwells.MenuItemEx()<o:p></o:p></span></p>
<p class=MsoNormal style='mso-layout-grid-align:none;text-autospace:none'><span
style='font-size:9.0pt;font-family:"Lucida Console"'><span style="mso-spacerun:
yes">            </span>ctxItem.Text = “Menu item text”<o:p></o:p></span></p>
<p class=MsoNormal style='mso-layout-grid-align:none;text-autospace:none'><span
style='font-size:9.0pt;font-family:"Lucida Console"'><span style="mso-spacerun:
yes">            </span>ctxItem.Tag = “Unique string value”<o:p></o:p></span></p>
<p class=MsoNormal style='mso-layout-grid-align:none;text-autospace:none'><span
style='font-size:9.0pt;font-family:"Lucida Console"'><span style="mso-spacerun:
yes">            </span><span style='color:blue'>AddHandler</span>
ctxItem.Click, <span style='color:blue'>New</span> System.EventHandler(<span
style='color:blue'>AddressOf</span> OnDynamicMenuClick)<o:p></o:p></span></p>
<p class=MsoNormal style='mso-layout-grid-align:none;text-autospace:none'><span
style='font-size:9.0pt;font-family:"Lucida Console"'><![if !supportEmptyParas]>&nbsp;<![endif]><o:p></o:p></span></p>
<p class=MsoNormal><span style='font-size:9.0pt;font-family:"Lucida Console"'><span
style="mso-spacerun: yes">   </span><span style="mso-spacerun:
yes">         </span>ctxMenu.MenuItems.Add(Position, ctxItem)<o:p></o:p></span></p>
<p class=MsoNormal><span style='mso-bidi-font-size:9.0pt'>Okay, but how do you
access the tag property when the ‘OnDynamicMenuClick’ event fires? Easy.<o:p></o:p></span></p>
<p class=MsoNormal><![if !supportEmptyParas]>&nbsp;<![endif]><o:p></o:p></p>
<p class=MsoNormal style='mso-layout-grid-align:none;text-autospace:none'><span
style='font-size:9.0pt;font-family:"Lucida Console"'><span style="mso-spacerun:
yes">        </span><span style='color:blue'>Public</span> <span
style='color:blue'>Sub</span> OnDynamicMenuClick(<span style='color:blue'>ByVal</span>
sender <span style='color:blue'>As</span> <span style='color:blue'>Object</span>,
<span style='color:blue'>ByVal</span> e <span style='color:blue'>As</span>
System.EventArgs)<o:p></o:p></span></p>
<p class=MsoNormal style='mso-layout-grid-align:none;text-autospace:none'><span
style='font-size:9.0pt;font-family:"Lucida Console"'><span style="mso-spacerun:
yes">            </span><span style='color:blue'>If</span> <span
style='color:blue'>TypeOf</span> sender <span style='color:blue'>Is</span> jwells.MenuItemEx
<span style='color:blue'>Then<o:p></o:p></span></span></p>
<p class=MsoNormal style='mso-layout-grid-align:none;text-autospace:none'><span
style='font-size:9.0pt;font-family:"Lucida Console"'><span style="mso-spacerun:
yes">                </span><span style='color:blue'>Dim</span> ID <span
style='color:blue'>As</span> <span style='color:blue'>String</span> = <span
style='color:blue'>CType</span>(sender, jwells.MenuItemEx).Tag<o:p></o:p></span></p>
<p class=MsoNormal style='mso-layout-grid-align:none;text-autospace:none'><span
style='font-size:9.0pt;font-family:"Lucida Console"'><![if !supportEmptyParas]>&nbsp;<![endif]><o:p></o:p></span></p>
<p class=MsoNormal style='mso-layout-grid-align:none;text-autospace:none'><span
style='font-size:9.0pt;font-family:"Lucida Console"'><span style="mso-spacerun:
yes">                </span>Debug.writeline(“ID: “ &amp; ID)<o:p></o:p></span></p>
<p class=MsoNormal style='mso-layout-grid-align:none;text-autospace:none'><span
style='font-size:9.0pt;font-family:"Lucida Console"'><span style="mso-spacerun:
yes">            </span><span style='color:blue'>End</span> <span
style='color:blue'>If<o:p></o:p></span></span></p>
<p class=MsoNormal><span style='font-size:9.0pt;font-family:"Lucida Console"'><span
style="mso-spacerun: yes">        </span><span style='color:blue'>End</span> <span
style='color:blue'>Sub<o:p></o:p></span></span></p>
<p class=MsoNormal><span style='font-size:9.0pt;font-family:"Lucida Console";
color:blue'><![if !supportEmptyParas]>&nbsp;<![endif]><o:p></o:p></span></p>
<p class=MsoNormal><span style='mso-bidi-font-size:9.0pt'>This could have been
done much differently, and it could have been more extensive, but this is just
a simple example of how inheritance can make your life easy, you don’t need to
create a new object, you just need to inherit it, and add some functionality.<o:p></o:p></span></p>
<p class=MsoNormal><span style='mso-bidi-font-size:9.0pt'><![if !supportEmptyParas]>&nbsp;<![endif]><o:p></o:p></span></p>
<p class=MsoNormal><span style='mso-bidi-font-size:9.0pt'>Pretty neat huh?<span
style="mso-spacerun: yes">  </span>I hope you found this somewhat informative,
even if it is on a very basic level.<span style="mso-spacerun: yes">  </span></span></p>
</div>
</body>
</html>
```

