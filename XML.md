# Week 9
## XML
### What is XML
- eXtensible Markdown Language
- Designed to store and transport data
- Self-descriptive: containing data as well as the metadata that describes the format and meaning
> XML does not DO anything, just info wrapped in tags
- Compared to HTML: XML focuses more on carrying the data instead of displaying it
### Syntax
```
<root>
  <child>
    <subchild>.....</subchild>
  </child>
</root>
```
> XML contains one ```<root>```element which is the parent of all other elements
Example
```
<?xml version="1.0" encoding="UTF-8"?>
<note>
  <to>Tove</to>
  <from>Jani</from>
  <heading>Reminder</heading>
  <body>Don't forget me this weekend!</body>
</note>
```
> The ```<note>``` here is the ```<root>``` element

 - The ```<?xml version="1.0" encoding="UTF-8"?>``` is called the **prolog** (optional, but must be at the first line)
    - _UTF-8_ is the default character encoding for XML documents
-  Closing tag <br/>
In XML all elements must have a closing tag 
```
<p>THis is a paragraph<p/>
```
>prolog does not have since it's not a part of the document
- Tags
XML tags are **case sensitive**
Opening and closing tags must be written with the same case
- ELements must be properly nested
<br/>
**The opening and closing order**
<br/>
For Example
```
<b><i>Bold and Italic<i><b>
```
> Note the order of i and b here, since i is opened inside b, it has to be closed inside as well
- Values always have to be **quoted**
```
<note date = "12/3/2022">
    <to>Tove</to>
    <from>Jani</from>
</note>
```






