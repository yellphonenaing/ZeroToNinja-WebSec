## Google Dorks (GHDB)
> ကျွန်တော်တို့ Google မှာ ကိုယ်လိုချင်တာတွေကို Searching လုပ်တဲ့အခါ ပိုမိုအဆင်ပြေစေရန်အလို့ငှာ Google Dorks တွေကို လေ့လာထားသင့်ပါတယ်။ Google Dorks တွေကို Pen-Tesing လုပ်တဲ့သူတွေပဲအသုံးများပေမယ့်။ ပုံမှန် User တွေအနေနဲ့လည်း သိထားသင့်ပါတယ်။ Google Dorks တွေကိုအသုံးပြူတတ်ခြင်းဖြင့် ကျွန်တော်တို့လိုချင်တဲ့ Target ကိုပိုမိုလွယ်ကူစွာ  ရရှိနိုင်ပါတယ်။ Google Dorks တွေကိုအသုံးပြုရာတွင် Operators ​တွေဟာအလွန်အရေးပါလှပါတယ်။ Operators တွေကိုအောက်တွင်လေ့လာကြည့်ပါ။

**intext**
> မိမိလိုခြင်တဲ့ စကားလုံးပါနေသော၊ ဆင်တူနေသော စကားလုံးပါသော Link တွေကို Search လုပ်ရာတွင် အသုံးပြုပါတယ်။

Example
```
intext:Hacked By BHG
```
> ဒါဆို Hacked By BHG ဆိုတဲ့  စကားလုံးပါသော Link များကိုထုတ်ပြပေးမှာပါ။

**intitle**
> မိမိလိုချင်သော ခေါင်းစဉ်တပ်ထားသော Link,Web Pages များကို Search လုပ်ရာတွင်အသုံးပြုပါတယ်။

Example
```
intitle:Myanmar
```
> ဒါဆို Title မှာ Myanmar ဆိုတဲ့ စကားလုံးပါနေသော Links,Web Pages များကို ထုတ်ပြပေးမှာပါ။

**site**
> Site (Or) Multi Sites တွေကို Domain Name အလိုက်ရှာချင်တဲ့အခါမှာ အသုံးပြုပါတယ်။

Example
```
site:gov.mm
```
> ဒါဆို မြန်မာနိုင်ငံရဲ့ အစိုးရ Site တွေကျလာမှာပါ။

Example
```
 site:facebook.com
```
> ဒါဆို facebook.com နဲ့ဆိုင်တဲ့ Links တွေကျလာမှာပါ။(Subdomain ရှာရာတွင်လည်းအသုံးဝင်ပါတယ်)

**cache**
> Site တစ်ခုရဲ့ cache ကိုကြည့်ချင်တဲ့အခါမှာအသုံးပြပါတယ်။

Example
```
cache:cyberbullet.xyz
```
> ဒါဆို cyberbullet.xyz ရဲ့ cache ကျလာမှာပါ။

**filetype**
> မိမိရှာလိုသော mp4,mp3,m3u8,pdf,txt,log,php,jsp,asp,env Files များကိုရှာဖွေရာတွင်အသုံးပြုနိုင်ပါတယ်။

Example
```
filetype:pdf site:gov.mm
```
> ဒါဆို မြန်မာနိုင်ငံအစိုးရ Web တွေမှာတင်ထားတဲ့ PDF Files တွေကျလာမှာပါ။

Example
```
filetype:sql intext:password
```
> ဒါဆို password ဆိုတဲ့ စကားလုံးပါနေသော sql Files တွေကျလာမှာပါ။

**inanchor**
> ကိုယ်ဖက်ချင်တဲ့ စကားလုံးပါတဲ့ Articles တွေကို Search လုပ်ရာတွင်အသုံးပြုပါတယ်။

Example
```
inanchor:Cyber Security
```
> ဒါဆို Cyber Security နဲ့ဆိုင်တဲ့ Articles တွေကျလာမှာပါ။

**| (Single Pipe)**
> တစ်ချိန်တည်းမှာ စကားလုံး ၂ခုထဲက တစ်ခု မဟုတ်တစ်ခုကို  ရှာချင်တဲ့အခါ အသုံးပြူပါတယ်။

Example
```
site:facebook.com intext:Myanmar | Burma
```
> ဒါဆို Facebook Web မှာ Myanmar Or Burma ဆိုတဲ့ စကားလုံးပါတဲ့ Link တွေကိုပြပေးမှာပါ။

**-**
> ဒိဟ ဖြစ်စောသော၊ အဓိပ္ပာယ်၂မျိုး (သို့) နှစ်မျိုးထက်ပိုသော အဓိပ္ပာယ်ရှိသော စကားလုံးများကို Search လုပ်ရာတွင် ဒိဟ မဖြစ်စေရန်အသုံးပြနိုင်ပါတယ်။ ဥပမာ ။	။ orange လို့ပြောလိုက်တာနဲ့ လိမ္မော်သီးလည့်ဖြစ်နိုင်သလို၊ လိမ္မော်ရောင် လည်းဖြစ်နိုင်ပါဝယ်။ ဒါကြောင့် Color ကိုရှာချင်ရင်  orange -fruit ဟုရှာနိုင်ပါတယ်။ လိမ္မော်သီး ကိုရှာချင်ရင် orange -color ဟူ၍ရှာနိုင်ပါတယ်။

## လက်တွေ့အသုံးခြင်း

**For Exploits**
```
Dork =>	intext:Powered By appsoftthai.com
Exploit => https://github.com/T-Tools/appsoft
```

```
Dork => intext:copyright © 2022 nemosofts all rights reserved
Exploit => https://github.com/T-Tools/nemo-exploit
```

```
Dork => intext:"Website designed and developed by Five design"
Exploit => https://github.com/T-Tools/fd-exploit
```

```
Dork => filetype:env intext:DB_PASSWORD
Acion => Search Leaked Database Creds From .env Files
```

**For OSINt**

```
Dork => intext:@gmail.com site:facebook.com inurl:sk=about
Action => Search Gmail Accounts From Facebook Profiles
```

```
Dork => intext:@gmail.com site:facebook.com inurl:about
Action => Search Gmail Accounts From Facebook Pages
```

```
Dork => intext:09 site:facebook.com intext:Magway
Action => Search Phone Numbers From Facebook Pages (Magway Region)
```


**Sensitive Data Exposure**

```
Dork => filetype:sql intext:user_pass
Action => Search SQL Backup File Containing Passwords
```

```
Dork => filetype:log intext:password
Action => Search Log Files Containing Passwords
```


**Reconnaissance**

```
Dork => site:.facebook.com -site:www.facebook.com
Action => Search Subdomains Of facebook.com
```

>အထက်ပါ Examples များအတိုင်း မိမိ ဉာဏ်ရှိသလို အသုံးပြုနိုင်ပါတယ်။
