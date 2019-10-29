To be able to optOut an user from tracking by SPRING you need to insert this small script to your \<body> TAG.

```
<script>
var ASCDP = window.ASCDP || {};
ASCDP.optOut = function() {
    var u = document.createElement("iframe");
    u.width = '0';
    u.height = '0';
    u.style.cssText = 'display:none;visibility:hidden;position:absolute;left:-99999px;top:-99999px;';
    u.id = 'u';
    u.src = "https://www.asadcdn.com/adlib/extensions/c.html?adnxs_uid=0&ref=" + encodeURIComponent(location.protocol + '//' + location.hostname) + "&memberId=7823&springBID=forbidden";
    document.getElementsByTagName("body")[0].appendChild(u);
};
</script>
```
Afterwards you will be able to insert a clickable element to invoke ASCDP.optOut() to set the users id to "forbidden", e.g.:
```
<a href="#" onclick="ASCDP.optOut(); alert('Lieber Nutzer, Sie haben sich erfolgreich vom Tracking ausgeschlossen.');" style="font-family: 'Gotham XNarrow', Arial, Helvetica, Tahoma, sans-serif; font-size: 21px; line-height: 30px;">Link</a>
```