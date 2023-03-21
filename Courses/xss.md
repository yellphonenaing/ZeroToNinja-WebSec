## 7. Cross Site Scripting (XSS)

![](https://miro.medium.com/v2/resize:fit:600/0*OgDrgZakNWFRIiIu.png)

**What is XSS attack?**

Cross-Site Scripting (XSS) attacks are a type of injection, in which malicious scripts are injected into otherwise benign and trusted websites. XSS attacks occur when an attacker uses a web application to send malicious code, generally in the form of a browser side script, to a different end user. Flaws that allow these attacks to succeed are quite widespread and occur anywhere a web application uses input from a user within the output it generates without validating or encoding it.

An attacker can use XSS to send a malicious script to an unsuspecting user. The end user’s browser has no way to know that the script should not be trusted, and will execute the script. Because it thinks the script came from a trusted source, the malicious script can access any cookies, session tokens, or other sensitive information retained by the browser and used with that site. These scripts can even rewrite the content of the HTML page. (Taken From OWASP)

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
