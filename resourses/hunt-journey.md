# How to Become a Hunter (The Journey)

## Starter

1. **آشنایی عمیق با مفاهیم امنیت وب**
    مثل XSS، CSRF، SQLi، IDOR، SSRF، RCE، و ...
2. **یادگیری ابزارها**
    Burp Suite، OWASP ZAP، Nmap، Nikto، و ابزارهای Recon مثل Amass، Subfinder و...
3. **مطالعه منابع و ریداپ‌ها (Writeups)**
    سایت‌هایی مثل:
   - HackerOne Hacktivity
   - Bugcrowd VRT
   - PortSwigger Web Security Academy
   - PentesterLab
4. **تمرین در پلتفرم‌های آموزشی یا CTF**
   - TryHackMe
   - Hack The Box
   - Web Security Academy
   - Root Me

## Things to Stay in Route

#### ۱. **تسلط روی تکنیک‌های Recon پیشرفته**

- یادگیری استفاده از ابزارهای Recon مثل:
  - `Subfinder`, `Amass`, `Assetfinder`
  - `httpx`, `waybackurls`, `gau`, `nuclei`
- ساخت یک اسکریپت اتوماتیک برای جمع‌آوری دامنه‌ها و ساب‌دامنه‌ها
- تمرین در پیدا کردن صفحات مخفی، پارامترهای حساس و فایل‌های حساس

#### ۲. **تمرین روی حملات پیچیده‌تر**

- **SSRF**, **IDOR**, **Open Redirect**, **CSP Bypass**
- خواندن writeupهای با کیفیت برای این دسته حملات
- تمرین روی باگ‌های گزارش‌شده در HackerOne یا Bugcrowd

#### ۳. **یادگیری استفاده حرفه‌ای از Burp Suite**

- نوشتن اکستنشن ساده با جاوا یا پایتون (BApp Store)
- استفاده حرفه‌ای از Intruder، Repeater و Collaborator

#### ۴. **تست روی برنامه‌های واقعی (VDP & Bug Bounty)**

- شروع با برنامه‌های دارای VDP (بدون پاداش مالی) مثل:
  - https://securitytxt.org/
  - https://intigriti.com/public-programs
- ورود تدریجی به برنامه‌های پولی مثل:
  - HackerOne, Bugcrowd, Synack (بعداً با دعوت)

#### ۵. **ساخت پروفایل و حضور در جامعه**

- ساخت اکانت در HackerOne و Bugcrowd حتی اگر قصد ریپورت نداری
- خواندن و تحلیل writeupهای Hacktivity
- شرکت در مسابقات CTF با تمرکز بر وب

## Learn More

## 🔐 1. **Authentication (Auth Bypass, Misconfigurations)**

### 🎯 ایده‌ها و سناریوها:

- **Rate Limit Bypass:** ورود با روش brute-force در فرم لاگین با دور زدن محدودیت‌ها
- **2FA Bypass:** تست برای جاهایی که OTP بررسی نمی‌شه یا قابلیت re-use داره
- **Password Reset Poisoning:** تغییر ایمیل یا توکن ریکاوری
- **JWT Manipulation:** استفاده از الگوریتم none یا کلید ضعیف (HS256 به RS256 و بالعکس)
- **OAuth Misuse:** abuse کردن flowهایی مثل implicit یا client credentials
- **Auth Logic Flaws:** لاگین به اکانت دیگر با تغییر role_id یا user_id

### 📘 منابع:

- https://hackerone.com/hacktivity?labels=authentication
- https://portswigger.net/web-security/authentication

------

## 🧪 2. **Cross-Site Scripting (XSS) پیشرفته**

### 🎯 ایده‌ها و سناریوها:

- **DOM-based XSS:** در فریم‌ورک‌هایی مثل React, Angular, Vue
- **Stored XSS در چت، ریویوها، یا notification‌ها**
- **Bypass کردن WAF با Unicode, Nested Tags یا Obfuscation**
- **Event-based XSS:** مثل `onerror=`, `onpointerdown`, `onanimationstart`
- **XSS to Account Takeover:** ترکیب با CSRF یا Cookie Theft
- **XSS via SVG, base64, iframe injection**

### 📘 منابع:

- https://xss-game.appspot.com/
- https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/XSS%20Injection
- https://xsshunter.com/

------

## 🌐 3. **Cross-Site Request Forgery (CSRF)**

### 🎯 ایده‌ها و سناریوها:

- **CSRF در توکن‌هایی که به‌درستی validate نمی‌شن**
- **CSRF روی endpoints که فکر می‌کنن امن هستن (مثلاً /logout)**
- **Multipart/Form-Data CSRF روی آپلود فایل**
- **CSRF on JSON endpoints (with CORS misconfig)**
- **Stored CSRF → حمله به admin و اجرای تنظیماتی مثل تغییر ایمیل**

### 📘 منابع:

- https://portswigger.net/web-security/csrf
- https://book.hacktricks.xyz/pentesting-web/csrf

------

## 🛰 4. **Server-Side Request Forgery (SSRF)**

### 🎯 ایده‌ها و سناریوها:

- **خواندن فایل‌های داخلی سرور (`file:///etc/passwd`)**
- **پینگ به متادیتای کلود (AWS: `169.254.169.254`)**
- **SSRF → RCE (در نرم‌افزارهایی که پاسخ رو اجرا می‌کنن)**
- **Blind SSRF با استفاده از DNS loggers (مثل Burp Collaborator)**
- **SSRF inside PDF Generators, Webhooks, Image Fetchers**
- **Bypass URL filters (با `@`, `//`, `%00`, `..`, `localhost:80#@evil.com`)**

### 📘 منابع:

- https://blog.orange.tw/2019/06/attacking-ssrf-in-cloud.html
- https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/Server%20Side%20Request%20Forgery



## Some Sources

1. ​        "https://hackerone.com/reports/209008",
2. ​        "https://www.linkedin.com/posts/infosec-writeups_jwt-authentication-bypass-leads-to-admin-activity-7256450364214763520-HPAc",
3. ​        "https://mchklt.medium.com/authentication-bypass-leads-to-pii-01d34fc7f547",
4. ​        "https://infosecwriteups.com/mastering-xss-a-comprehensive-guide-for-bug-bounty-hunters-fc4e2b4ad1f1",
5. ​        "https://www.intigriti.com/researchers/blog/hacking-tools/hunting-for-blind-cross-site-scripting-xss-vulnerabilities-a-complete-guide",
6. ​        "https://medium.com/@shadyfarouk1986/advanced-xss-filter-bypass-methods-using-payload-splitting-c8e32497461a",
7. ​        "https://medium.com/@trixiahorner/csrf-walkthrough-5876cdf437ea",
8. ​        "https://hackerone.com/reports/127703",
9. ​        "https://www.youtube.com/watch?v=o2rj0utFZvg",
10. ​        "https://medium.com/@josekuttykunnelthazhebinu/how-i-uncovered-an-ssrf-vulnerability-in-a-private-hackerone-program-4c3146b414ff",
11. ​        "https://www.intigriti.com/researchers/blog/hacking-tools/ssrf-a-complete-guide-to-exploiting-advanced-ssrf-vulnerabilities",
12. ​        "https://hackerone.com/reports/326040",
13. ​        "https://github.com/devanshbatham/Awesome-Bugbounty-Writeups",
14. ​        "https://hackerone.com/hacktivity"
15. "https://www.acunetix.com/blog/articles/cross-site-scripting-via-svg-files/",
16. "https://hackerone.com/reports/127703"
17. "https://blog.assetnote.io/2021/03/10/ssrf-everywhere/",
18. "https://portswigger.net/web-security/ssrf/blind"
19. "https://portswigger.net/web-security"

## Learn

## 🗓 هفته ۱ – **Authentication & Authorization Flaws**

**🎯 هدف:** یادگیری Bypass ورود، JWT manipulation، و مشکلات لاجیک
 **📘 یاد بگیر:**

- OAuth flow abuse
- Password reset poisoning
- JWT None + HS256/RS256 bypass
- Role escalation / vertical privilege escalation

**🔧 تمرین کن:**

- https://portswigger.net/web-security/authentication
- https://tryhackme.com/room/authentication

**📖 رایت‌آپ پیشنهادی:**

- https://www.linkedin.com/posts/infosec-writeups_jwt-authentication-bypass-leads-to-admin-activity-7256450364214763520-HPAc

------

## 🗓 هفته ۲ – **Cross-Site Scripting (XSS) پیشرفته**

**🎯 هدف:** پیدا کردن و بای‌پس XSS در فریم‌ورک‌ها و DOM
 **📘 یاد بگیر:**

- DOM XSS, blind XSS, self-XSS
- بای‌پس فیلتر با Unicode، base64 و payload splitting
- Stored XSS در چت/نوتیفیکیشن

**🔧 تمرین کن:**

- https://xss-game.appspot.com/
- https://portswigger.net/web-security/cross-site-scripting
- [HackTheBox - XSS CTFs]

**📖 رایت‌آپ پیشنهادی:**

- https://www.intigriti.com/researchers/blog/hacking-tools/hunting-for-blind-cross-site-scripting-xss-vulnerabilities-a-complete-guide

------

## 🗓 هفته ۳ – **Cross-Site Request Forgery (CSRF)**

**🎯 هدف:** یافتن CSRF در APIها، فرم‌ها، و ترکیب آن با XSS
 **📘 یاد بگیر:**

- SameSite cookies و CORS در CSRF
- JSON CSRF / multipart CSRF
- Stored CSRF در سیستم‌های مدیریت ادمین

**🔧 تمرین کن:**

- https://portswigger.net/web-security/csrf
- https://tryhackme.com/room/csrf

**📖 رایت‌آپ پیشنهادی:**

- https://medium.com/@trixiahorner/csrf-walkthrough-5876cdf437ea

------

## 🗓 هفته ۴ – **Server-Side Request Forgery (SSRF)**

**🎯 هدف:** حمله به سرویس‌های داخلی، دسترسی به متادیتای کلود
 **📘 یاد بگیر:**

- SSRF Blind با DNS logging
- استفاده از redirect chain / open redirect
- SSRF در PDF/Img generators, webhook

**🔧 تمرین کن:**

- https://portswigger.net/web-security/ssrf
- https://tryhackme.com/room/ssrf

**📖 رایت‌آپ پیشنهادی:**

- https://medium.com/@josekuttykunnelthazhebinu/how-i-uncovered-an-ssrf-vulnerability-in-a-private-hackerone-program-4c3146b414ff



## ✅ **هفته اول: برنامه تمرینی Auth Bypass**

### 📘 بخش ۱ – یادگیری مفاهیم پیشرفته

روی این مباحث تمرکز کن:

| موضوع                               | توضیح                                                        |
| ----------------------------------- | ------------------------------------------------------------ |
| **JWT Manipulation**                | تغییر الگوریتم به `none` یا استفاده از کلید اشتباه در HS256 / RS256 |
| **Brute-force & Rate Limit Bypass** | پیدا کردن فرم ورود بدون محدودیت تلاش یا کد تایید             |
| **Logic Flaws in Login**            | مثال: اگر فقط ایمیل بررسی شود و رمز عبور نادیده گرفته شود    |
| **Password Reset Exploits**         | تغییر ایمیل در ریکاوری، پیش‌بینی توکن، یا تزریق ایمیل         |
| **OAuth Misuse**                    | اشتباه در callback، گرفتن access token برای کاربر دیگر، SSRF در `redirect_uri` |



------

### 🔧 بخش ۲ – تمرین عملی

#### 🌐 پلتفرم تمرینی:

1. **PortSwigger Auth Labs** https://portswigger.net/web-security/authentication
   - انجام حداقل 5 چالش در بخش login/auth
   - تمرکز روی bypass و brute-force
2. **TryHackMe - Authentication Room **https://tryhackme.com/room/authentication
   - تمرین احراز هویت با تحلیل توکن‌ها و کوکی‌ها
3. **[HackTheBox - Writeup Challenge (optional)]**
    اگر حساب داری، بخش‌هایی مثل “Knife” یا “Lame” حاوی ضعف‌های لاجین هستند.

------

### 🧠 بخش ۳ – تحلیل رایت‌آپ واقعی

#### 🎯 JWT Manipulation to Admin https://www.linkedin.com/posts/infosec-writeups_jwt-authentication-bypass-leads-to-admin-activity-7256450364214763520-HPAc

**لینک:** JWT Admin Bypass

**نکات کلیدی برای یادگیری:**

- چک کردن JWT در سمت کلاینت!
- تست الگوریتم `none` یا استفاده از public key به جای private key
- ایده‌های حمله: تزریق دستی در JWT header و payload با ابزار JWT.io

------

### 🎁 ابزارهای پیشنهادی این هفته

| ابزار                   | کاربرد                                        |
| ----------------------- | --------------------------------------------- |
| **JWT.io**              | ویرایش و مشاهده توکن‌های JWT                   |
| **Burp Suite Intruder** | برای brute force یا حملات روی فرم‌های لاگین    |
| **ffuf / wfuzz**        | پیدا کردن صفحات حساس با directory brute-force |
| **Autorize (Burp Ext)** | بررسی auth bypass با user/guest در یک تب      |



------

### 📌 وظایف این هفته

-  مطالعه مفاهیم JWT و OAuth در PortSwigger
-  حل حداقل 5 تمرین Auth در PortSwigger
-  انجام TryHackMe Auth Room
-  تحلیل رایت‌آپ JWT Bypass
-  تست یکی از فرم‌های ورود واقعی در سایت‌های bug bounty (با رعایت قوانین!)

------



## 🧪 **هفته دوم – Cross-Site Scripting (XSS) پیشرفته**

### 📘 مفاهیم پیشرفته

| موضوع                         | توضیح                                                       |
| ----------------------------- | ----------------------------------------------------------- |
| **DOM XSS**                   | تزریق در JavaScript سمت کلاینت                              |
| **Blind XSS**                 | زمانی‌که payload در سیستم لاگ یا پنل admin اجرا شود          |
| **Stored XSS در HTML/JS/CSS** | مانند داخل `title`، `meta`, `svg` یا حتی `style=`           |
| **Filter Bypass Techniques**  | مثل استفاده از `<`, `javascript:` یا nested event handlerها |



------

### 🔧 تمرین عملی

1. https://xss-game.appspot.com/
2. https://portswigger.net/web-security/cross-site-scripting
3. TryHackMe → https://tryhackme.com/room/xss

------

### 🧠 تحلیل رایت‌آپ

**عنوان:** Blind XSS Hunting Guide
https://www.intigriti.com/researchers/blog/hacking-tools/hunting-for-blind-cross-site-scripting-xss-vulnerabilities-a-complete-guide

**نکات کلیدی:**

- تست کردن فرم‌های بی‌پاسخ
- استفاده از xsshunter.com یا Burp Collaborator برای کشف اجرای blind

------

### 🧰 ابزارها

| ابزار                                    | کاربرد                               |
| ---------------------------------------- | ------------------------------------ |
| **xsshunter.com**                        | ثبت و کشف blind XSS                  |
| **Burp Suite - Logger++ / Collaborator** | دیدن اجرا و تعامل با blind payload   |
| **XSStrike**                             | ابزار تست XSS پیشرفته و بای‌پس خودکار |



------

### 📌 وظایف این هفته

-  حل حداقل 5 تمرین XSS (DOM و Stored) در PortSwigger
-  انجام TryHackMe XSS Room
-  ثبت نام در xsshunter و تست Blind XSS در یک فرم
-  تحلیل رایت‌آپ Blind XSS

------

## 🎯 **هفته سوم – CSRF پیشرفته**

### 📘 مفاهیم پیشرفته

| موضوع                       | توضیح                                        |
| --------------------------- | -------------------------------------------- |
| **CSRF روی JSON/Multipart** | به ویژه در upload یا تغییرات تنظیمات         |
| **CSRF در admin panels**    | مانند تغییر role یا حذف user                 |
| **Bypass SameSite**         | با iframe + auto-submit و تنظیمات lax/strict |



------

### 🔧 تمرین عملی

1. https://portswigger.net/web-security/csrf
2. https://tryhackme.com/room/csrf

### 🧠 تحلیل رایت‌آپ

**عنوان:** CSRF → تغییر ایمیل کاربر
https://medium.com/@trixiahorner/csrf-walkthrough-5876cdf437ea

------

### 🧰 ابزارها

| ابزار                               | کاربرد                         |
| ----------------------------------- | ------------------------------ |
| **Burp Suite - CSRF PoC Generator** | تولید فرم برای حمله CSRF       |
| **Postman**                         | شبیه‌سازی درخواست POST/PUT JSON |
| **OWASP CSRFTester**                | بررسی خودکار سایت‌ها برای CSRF  |



------

### 📌 وظایف این هفته

-  انجام حداقل 3 سناریوی CSRF در PortSwigger
-  اجرای یک تست در محیط شخصی با تنظیم SameSite
-  بررسی عملکرد CSRF در سایت‌های ساده با ابزار Burp
-  تحلیل رایت‌آپ ایمیل تغییر CSRF

------

## 🌐 **هفته چهارم – Server-Side Request Forgery (SSRF)**

### 📘 مفاهیم پیشرفته

| موضوع                                             | توضیح                                                        |
| ------------------------------------------------- | ------------------------------------------------------------ |
| **Blind SSRF**                                    | بدون پاسخ مستقیم، قابل شناسایی از طریق DNS log               |
| **SSRF در Image Fetcher, PDF Renderer, Webhooks** |                                                              |
| **Cloud Metadata Abuse**                          | مانند `169.254.169.254` در AWS/GCP                           |
| **Bypass فیلتر URL**                              | مثل استفاده از `127.0.0.1@evil.com`, `file://` یا `internal.hostname` |



------

### 🔧 تمرین عملی

1. https://portswigger.net/web-security/ssrf
2. https://tryhackme.com/room/ssrf

------

### 🧠 تحلیل رایت‌آپ

**عنوان:** SSRF in Private HackerOne Program
https://medium.com/@josekuttykunnelthazhebinu/how-i-uncovered-an-ssrf-vulnerability-in-a-private-hackerone-program-4c3146b414ff

------

### 🧰 ابزارها

| ابزار                 | کاربرد                                       |
| --------------------- | -------------------------------------------- |
| **Burp Collaborator** | تست Blind SSRF                               |
| **Interactsh**        | جایگزین سبک‌تر Collaborator برای DNS/HTTP log |
| **ffuf + gau**        | کشف پارامترهای احتمالی SSRF                  |



------

### 📌 وظایف این هفته

-  حل تمرین SSRF در PortSwigger
-  استفاده از Interactsh یا Collaborator برای تست Blind SSRF
-  تحلیل حمله به `metadata service` در رایت‌آپ
-  تست SSRF در یک PDF Generator یا endpoint `url=`



## Writeups

## 🔐 Authentication Bypass

1. **Bypass با ترکیب Username Enumeration و Brute Force**
    در این گزارش، محقق با استفاده از ترکیب دو آسیب‌پذیری توانسته به حساب‌های کاربری دسترسی پیدا کند.
   https://hackerone.com/reports/209008
2. **دور زدن احراز هویت از طریق JWT Manipulation**
    در این مقاله، نحوه دور زدن احراز هویت با استفاده از JWT و دسترسی به پنل مدیریت شرح داده شده است.
   https://www.linkedin.com/posts/infosec-writeups_jwt-authentication-bypass-leads-to-admin-activity-7256450364214763520-HPAc
3. **دور زدن احراز هویت با استفاده از Header Manipulation**
    محقق با دستکاری هدرهای HTTP توانسته به اطلاعات حساس کاربران دسترسی پیدا کند.
   https://mchklt.medium.com/authentication-bypass-leads-to-pii-01d34fc7f547

------

## 🧪 Cross-Site Scripting (XSS)

1. **راهنمای جامع برای یافتن و بهره‌برداری از XSS**
    این مقاله به بررسی انواع مختلف XSS و تکنیک‌های پیشرفته برای بهره‌برداری از آن‌ها می‌پردازد.
   https://infosecwriteups.com/mastering-xss-a-comprehensive-guide-for-bug-bounty-hunters-fc4e2b4ad1f1
2. **شکار Blind XSS: راهنمای کامل**
    در این مقاله، نحوه شناسایی و بهره‌برداری از Blind XSS با استفاده از ابزارهای خاص توضیح داده شده است.
   https://www.intigriti.com/researchers/blog/hacking-tools/hunting-for-blind-cross-site-scripting-xss-vulnerabilities-a-complete-guide
3. **روش‌های پیشرفته برای دور زدن فیلترهای XSS با استفاده از Payload Splitting**
    این مقاله به بررسی تکنیک‌های پیشرفته برای دور زدن فیلترهای XSS می‌پردازد.
   https://medium.com/@shadyfarouk1986/advanced-xss-filter-bypass-methods-using-payload-splitting-c8e32497461a

------

## 🎯 Cross-Site Request Forgery (CSRF)

1. **تغییر ایمیل کاربر با استفاده از CSRF**
    در این رایت‌آپ، نحوه بهره‌برداری از CSRF برای تغییر ایمیل کاربر شرح داده شده است.
   https://medium.com/@trixiahorner/csrf-walkthrough-5876cdf437ea
2. **CSRF منجر به تصاحب کامل حساب کاربری**
    این گزارش به بررسی آسیب‌پذیری CSRF که منجر به تصاحب کامل حساب کاربری می‌شود، می‌پردازد.
   https://hackerone.com/reports/127703
3. **مطالعه موردی CSRF در باگ بانتی**
    این ویدیو به بررسی تکنیک‌های مؤثر برای شناسایی و بهره‌برداری از CSRF در سال 2024 می‌پردازد.
   https://www.youtube.com/watch?v=o2rj0utFZvg

------

## 🌐 Server-Side Request Forgery (SSRF)

1. **SSRF در برنامه خصوصی HackerOne**
    در این مقاله، محقق نحوه شناسایی و بهره‌برداری از SSRF در یک برنامه خصوصی را توضیح می‌دهد.
   https://medium.com/@josekuttykunnelthazhebinu/how-i-uncovered-an-ssrf-vulnerability-in-a-private-hackerone-program-4c3146b414ff
2. **راهنمای کامل برای بهره‌برداری از SSRF پیشرفته**
    این مقاله به بررسی تکنیک‌های پیشرفته برای بهره‌برداری از SSRF می‌پردازد.
   https://www.intigriti.com/researchers/blog/hacking-tools/ssrf-a-complete-guide-to-exploiting-advanced-ssrf-vulnerabilities
3. **SSRF در برنامه‌های Atlassian**
    در این گزارش، محقق نحوه بهره‌برداری از SSRF در برنامه‌های Atlassian را شرح می‌دهد.
   https://hackerone.com/reports/326040



## More Writeups

## 🔐 Authentication Bypass

| عنوان رایت‌آپ                                             | تکنیک مورد استفاده                                 | لینک                                                         |
| -------------------------------------------------------- | -------------------------------------------------- | ------------------------------------------------------------ |
| **Bypass با ترکیب Username Enumeration و Brute Force**   | ترکیب دو آسیب‌پذیری برای تصاحب حساب کاربری          | [مشاهده رایت‌آپ](https://hackerone.com/reports/209008)        |
| **دور زدن احراز هویت از طریق JWT Manipulation**          | تغییر الگوریتم JWT برای دسترسی به پنل مدیریت       | [مشاهده رایت‌آپ](https://www.linkedin.com/posts/infosec-writeups_jwt-authentication-bypass-leads-to-admin-activity-7256450364214763520-HPAc) |
| **دور زدن احراز هویت با استفاده از Header Manipulation** | استفاده از هدرهای HTTP برای دسترسی به اطلاعات حساس | [مشاهده رایت‌آپ](https://mchklt.medium.com/authentication-bypass-leads-to-pii-01d34fc7f547) |
| **آسیب‌پذیری در پروتکل HawkAuth**                         | ضعف در اعتبارسنجی payload در پروتکل HawkAuth       | [مشاهده رایت‌آپ](https://bitsofcyber.substack.com/p/hawk-authentication-bypass-vulnerability) |
| **دور زدن احراز هویت از طریق ماشین حالت معیوب**          | بهره‌برداری از نقص در فرآیند احراز هویت چندمرحله‌ای  | [مشاهده رایت‌آپ](https://infosecwriteups.com/write-up-authentication-bypass-via-flawed-state-machine-portswigger-academy-e7448edeeb3d) |



------

## 🧪 Cross-Site Scripting (XSS)

| عنوان رایت‌آپ                                                 | تکنیک مورد استفاده                                           | لینک                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| **راهنمای جامع برای یافتن و بهره‌برداری از XSS**              | بررسی انواع مختلف XSS و تکنیک‌های پیشرفته                     | [مشاهده رایت‌آپ](https://infosecwriteups.com/mastering-xss-a-comprehensive-guide-for-bug-bounty-hunters-fc4e2b4ad1f1) |
| **شکار Blind XSS: راهنمای کامل**                             | شناسایی و بهره‌برداری از Blind XSS با استفاده از ابزارهای خاص | [مشاهده رایت‌آپ](https://www.intigriti.com/researchers/blog/hacking-tools/hunting-for-blind-cross-site-scripting-xss-vulnerabilities-a-complete-guide) |
| **روش‌های پیشرفته برای دور زدن فیلترهای XSS با استفاده از Payload Splitting** | تکنیک‌های پیشرفته برای دور زدن فیلترهای XSS                   | [مشاهده رایت‌آپ](https://medium.com/@shadyfarouk1986/advanced-xss-filter-bypass-methods-using-payload-splitting-c8e32497461a) |
| **راهنمای نهایی برای یافتن و ارتقاء آسیب‌پذیری‌های XSS**       | تکنیک‌های پیشرفته برای شناسایی و بهره‌برداری از XSS            | [مشاهده رایت‌آپ](https://www.bugcrowd.com/blog/the-ultimate-guide-to-finding-and-escalating-xss-bugs/) |



------

برای تمرین بیشتر، می‌تونی از منابع زیر استفاده کنی:

- **PortSwigger Web Security Academy**: آزمایشگاه‌های عملی برای تمرین آسیب‌پذیری‌های مختلف از جمله XSS و Authentication Bypass.
  - https://portswigger.net/web-security
- **Awesome Bug Bounty Writeups**: مجموعه‌ای از رایت‌آپ‌های دسته‌بندی‌شده بر اساس نوع آسیب‌پذیری.
  - https://github.com/devanshbatham/Awesome-Bugbounty-Writeups



## XSS in React

## 🧪 XSS در وب‌اپ‌های مدرن (با تمرکز بر React)

### ✅ ویژگی‌های امنیتی React

React به‌طور پیش‌فرض محتوای HTML را escape می‌کند، بنابراین:

```
<div>{userInput}</div> // امن
```

اما اگر از `dangerouslySetInnerHTML` استفاده شود:

```
<div dangerouslySetInnerHTML={{ __html: userInput }} /> // خطرناک
```

------

## 🎯 مسیر حمله به XSS در React

### ۱. **استفاده نادرست از `dangerouslySetInnerHTML`**

اگر داده‌ای از کاربر بدون sanitize به این تابع داده شود، مستقیماً اجرا می‌شود.

**رایت‌آپ:**
https://infosecwriteups.com/xss-in-reactjs-web-app-using-dangerouslysetinnerhtml-and-bug-bounty-tip-3c5e4dc18be6

------

### ۲. **XSS در SSR (Server-Side Rendering)**

در حالت SSR، ممکنه escape به‌درستی انجام نشه. اگر یک پیام flash یا خطا روی سرور رندر بشه و escape نشه، XSS رخ می‌ده.

**مثال:** React SSR با Express که ارور را بدون sanitize چاپ کند:

```
res.render("error", { message: req.query.msg }) // خطرناک
```

**رایت‌آپ:**
https://blog.doyensec.com/2021/01/20/xss-react-server-side.html

------

### ۳. **XSS از طریق Third-Party React Components**

کامپوننت‌های آماده مثل `react-markdown`, `react-html-parser`, یا `react-quill` اگر به‌درستی پیکربندی نشوند، می‌توانند XSS داشته باشند.

**رایت‌آپ:**
https://blog.detectify.com/2020/05/06/using-react-markdown-libraries-xss/

------

### ۴. **JSX Attribute Injection (React Prop XSS)**

اگر کاربر مقدار attribute‌ای مثل `href`, `onClick`, `style` را کنترل کند و escape نشود، می‌توان جاوااسکریپت تزریق کرد:

```
<a href={userInput}>Click</a> // اگر href = "javascript:alert(1)" باشد
```

**رایت‌آپ:**
https://portswigger.net/research/dom-based-xss-in-single-page-applications

------

### ۵. **XSS در WebSocket + React**

زمانی که داده از WebSocket گرفته می‌شود و بدون بررسی در DOM گذاشته می‌شود.

------

## 🔧 ابزارهای تمرین XSS در React

| ابزار                                       | کاربرد                                                |
| ------------------------------------------- | ----------------------------------------------------- |
| **ReactGoat**                               | یک اپلیکیشن آسیب‌پذیر ساخته‌شده با React برای تمرین XSS |
| https://github.com/OWASP/NodeGoat#reactgoat |                                                       |
| **WebGoat + SPA Labs**                      | شامل چالش‌هایی برای SPAها                              |
| **PortSwigger Labs (Advanced DOM XSS)**     | تمرین با SPA-like behavior                            |
| **HackTheBox – Injectilious**               | تمرین XSS با جاوااسکریپت مدرن                         |



## XSS Bypasses

## ✅ پیشنهاد برای تمرین‌های بای‌پس:

| تکنیک               | مثال Payload                                                 |
| ------------------- | ------------------------------------------------------------ |
| تگ‌های غیرمعمول      | `<svg/onload=alert(1)>`                                      |
| Unicode و nested    | `<scr<script>ipt>alert(1)</script>`                          |
| Attribute-based XSS | `<img src=x onerror=alert(1)>`                               |
| Base64 (غیرمستقیم)  | در `data:` URLs مثل `<iframe src="data:text/html;base64,...">` |
| DOM-only XSS        | از طریق `searchResult` و کدهایی مثل: `?q=<img src=x onerror=alert(1)>` |



## Learn Deeper about JS, React

## 📚 منابع آموزشی پیشرفته برای امنیت در React و JavaScript

### 1. **راهنمای جامع XSS در React – StackHawk**

این مقاله به بررسی نحوه وقوع حملات XSS در برنامه‌های React می‌پردازد و روش‌های پیشگیری از آن‌ها را توضیح می‌دهد.
https://www.stackhawk.com/blog/react-xss-guide-examples-and-prevention/

### 2. **ویدئو آموزشی: XSS در React و JavaScript خالص**

این ویدئو به صورت عملی نحوه بهره‌برداری از آسیب‌پذیری‌های XSS در React و JavaScript را نشان می‌دهد.
https://www.youtube.com/watch?v=fnQdZdxYxrU

### 3. **Cheat Sheet امنیتی React – Pragmatic Web Security**

این راهنما نکات کلیدی برای جلوگیری از XSS در برنامه‌های React را ارائه می‌دهد.
https://pragmaticwebsecurity.com/files/cheatsheets/reactxss.pdf

### 4. **مقاله: آسیب‌پذیری‌های XSS در React – Medium**

این مقاله به بررسی روش‌های مختلف حملات XSS در React و نحوه پیشگیری از آن‌ها می‌پردازد.
https://medium.com/@jurouhlar/quick-devnotes-xss-vulnerabilities-in-react-45d9f683a7d2

------

## 🛠 پروژه‌های عملی برای تمرین امنیت در React

### 1. **پروژه GitHub: react-xss**

این پروژه شامل مثال‌هایی از آسیب‌پذیری‌های XSS در React است که می‌توانید برای تمرین استفاده کنید.
https://github.com/robianmcd/react-xss

### 2. **آزمایشگاه‌های امنیتی PortSwigger**

این آزمایشگاه‌ها شامل تمرین‌های عملی برای شناسایی و بهره‌برداری از آسیب‌پذیری‌های مختلف از جمله XSS هستند.
https://portswigger.net/web-security



## 🗓 **هفته ۱ – مبانی امنیت در JavaScript و React**

### 🎯 اهداف:

- درک رفتار DOM و نحوه وقوع XSS
- آشنایی با تفاوت Stored، Reflected، و DOM-based XSS
- شناخت sanitize و escape در React

### 📘 یاد بگیر:

| موضوع                              | منبع                                                         |
| ---------------------------------- | ------------------------------------------------------------ |
| ساختار DOM و innerHTML             | https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model |
| انواع XSS                          | https://owasp.org/www-community/attacks/xss/                 |
| استفاده از dangerouslySetInnerHTML | https://reactjs.org/docs/dom-elements.html#dangerouslysetinnerhtml |



### 🛠 تمرین:

- اجرای react-xss project https://github.com/robianmcd/react-xss
- اجرای `dangerouslySetInnerHTML` و وارد کردن payloadهای مختلف:

------

## 🗓 **هفته ۲ – تحلیل رفتار فریم‌ورک‌ها و بای‌پس‌ها**

### 🎯 اهداف:

- تحلیل sanitizeهای ناکامل در React
- شناخت خطاهای رایج برنامه‌نویسان
- یادگیری تکنیک‌های bypass فیلتر

### 📘 یاد بگیر:

| موضوع                 | منبع                                                         |
| --------------------- | ------------------------------------------------------------ |
| Sanitization Failures | https://www.stackhawk.com/blog/react-xss-guide-examples-and-prevention/ |
| React Prop Injection  | https://portswigger.net/research/dom-based-xss-in-single-page-applications |

### 🛠 تمرین:

- تغییر پروژه ReactGoat یا پروژه قبلی و استفاده از replace برای فیلتر `script`
- تست payloadهای بای‌پس:

```
<scr<script>ipt>alert(1)</script>
<svg><desc><![CDATA[<script>alert(1)</script>]]></desc></svg>
```

------

## 🗓 **هفته ۳ – تمرین Blind XSS، WebSocket و SSR**

### 🎯 اهداف:

- تست Blind XSS در پنل‌های مدیریت
- تحلیل رندر سمت سرور (SSR) در React/Next.js
- شناخت ضعف در WebSocket handlers

### 📘 یاد بگیر:

| موضوع                 | منبع                                                         |
| --------------------- | ------------------------------------------------------------ |
| Blind XSS + WebSocket | https://www.intigriti.com/researchers/blog                   |
| XSS در SSR React      | https://blog.doyensec.com/2021/01/20/xss-react-server-side.html |



### 🛠 تمرین:

- ساخت endpoint Flask برای دریافت پیام و نمایش آن در admin
- اتصال صفحه React به WebSocket و ثبت message
- ارسال پیام حاوی payload و بررسی اجرای آن در dashboard

------

## 🗓 **هفته ۴ – ساخت پروژه کامل و تست ابزارهای امنیتی**

### 🎯 اهداف:

- اجرای ابزارهای اسکن خودکار روی پروژه React
- تست Burp Suite و ZAP روی SPA
- تحلیل نتایج اسکن

### 📘 یاد بگیر:

| موضوع                 | منبع                                                         |
| --------------------- | ------------------------------------------------------------ |
| XSS Cheat Sheet       | https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/XSS%20Injection |
| استفاده از Burp Suite | https://portswigger.net/web-security/cross-site-scripting    |



### 🛠 تمرین:

- نصب Burp Suite و اجرای proxy روی localhost
- اسکن پروژه React با Burp/ZAP
- استفاده از افزونه‌های مخصوص SPA در Burp مانند Autorize یا DOM Invader

------

## 

### learning lab

https://github.com/php-lover-boy/react-xss-lab





## Search About All things

## آسیب‌پذیری XSS (Cross-Site Scripting)

XSS از متداول‌ترین آسیب‌پذیری‌های وب است که به مهاجم اجازه می‌دهد کد مخرب سمت‌کاربر تزریق کند. در باگ بانتی، یافتن XSS‌ها (به‌ویژه نوع ذخیره‌شده و کور) بسیار رایج و ارزشمند است. منابع زیر به صورت عملی این آسیب‌پذیری و روش‌های کشف/بهره‌برداری آن را پوشش می‌دهند:

| منبع                                                         | توضیح کوتاه                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| **رایت‌آپ: کشف XSS ذخیره‌شده** – Medium (انمول)[anmolvishwakarma7466.medium.com](https://anmolvishwakarma7466.medium.com/discovering-a-stored-xss-vulnerability-on-a-bug-bounty-program-8dad1b475695#:~:text=H ello AppSec folks%2C I,straight into my recent findings)[anmolvishwakarma7466.medium.com](https://anmolvishwakarma7466.medium.com/discovering-a-stored-xss-vulnerability-on-a-bug-bounty-program-8dad1b475695#:~:text=The Blind XSS Approach) | شرح یک باگ بانتی واقعی که پژوهشگر با تزریق Payload کور (Blind XSS) در یک انجمن کاربری، موفق به اجرای اسکریپت در مرورگر مدیر شد و اکانت را تصاحب کرد (جایزه $500). این رایت‌آپ مراحل شناسایی (تست ورودی‌ها، فرضیه نیاز به مشاهده ادمین) و استفاده از ابزار XSS Hunter برای رهگیری اجرای کد را نشان می‌دهد. |
| **مقاله فنی: راهنمای جامع XSS** – وبلاگ YesWeHack            | یک راهنمای جامع ۲۰۲۵ که انواع XSS (بازتابی، ذخیره‌شده، DOM-Based و Blind) را به‌همراه روش‌های کشف، تکنیک‌های اکسپلویت و سناریوهای دنیای واقعی توضیح می‌دهد. این منبع تأکید می‌کند که XSS علیرغم رایج‌بودن، می‌تواند با تکنیک‌های درست به حملات پرخطر (مثل سرقت کوکی و تصاحب حساب) تبدیل شود. مناسب برای شکارچیان باگ جهت ارتقای مهارت XSS. |
| **لابراتوار آموزشی: XSS در PortSwigger Academy** – (سری تمرین‌ها) | مجموعه‌ای از سناریوهای تعاملی برای تمرین XSS در شرایط گوناگون. از XSS بازتابی ساده تا موارد پیچیده (مانند بایپس فیلترها و XSS در contextهای مختلف) را شامل می‌شود. هر لابراتوار همراه با راهنمایی و PoC است تا مهارت تست بلک‌باکس XSS را تقویت کند. |
| **پلتفرم تمرینی: TryHackMe – اتاق XSS**                      | یک محیط آموزشی عملی که مفاهیم XSS را قدم‌به‌قدم پوشش می‌دهد. این اتاق انواع حملات XSS (بازتابی، ذخیره‌شده، DOM) و همچنین روش‌های پچ کردن آن‌ها را آموزش می‌دهد. مناسب برای مبتدیان جهت یادگیری تعاملی در بستر باگ‌بانتی. |
| **ابزار کمکی: XSS Hunter** (سرویس تحت وب)                    | ابزاری محبوب برای شکارچیان باگ جهت شناسایی XSSهای کور. با قراردادن دامنه‌ی رهگیری XSS Hunter در payload، در صورت اجرا شدن کد روی مرورگر هدف (مثلاً پنل ادمین)، گزارشی شامل جزئیات درخواست به شما ارسال می‌شود. این ابزار در سناریوهای بلک‌باکس برای کشف XSSهایی که خروجی مستقیم ندارند بسیار کاربردی است. |
| **مخزن Payloadها: PayloadsAllTheThings – XSS Payloads**      | یک مخزن GitHub مشهور که مجموعه‌ای از payloadهای آماده و روش‌های بایپس فیلتر برای XSS را گردآوری کرده است. در هنگام گیرکردن در ساخت payload، مراجعه به بخش XSS این مخزن می‌تواند ایده‌های خلاقانه برای دورزدن فیلترها یا WAF ارائه دهد. |
| **ویدیو آموزشی: «Cross-Site Scripting Explained»** – NahamSec (YouTube) | یک ویدیوی آموزشی رایگان که مفاهیم XSS را برای شکار باگ توضیح می‌دهد. در این ویدیو مثال‌های عملی از پیدا کردن XSS در برنامه‌های واقعی ارائه شده و تکنیک‌هایی مثل استفاده از `alert(document.domain)` به جای `alert(1)` برای اعتبارسنجی باگ نمایش داده می‌شود. این ویدیو دید مناسبی از رویکرد بلک‌باکس به XSS به شما می‌دهد. |
| **دوره مبتدی XSS** – The XSS Rat (یوتیوب)                    | یک دوره رایگان ویدیویی توسط XSS Rat (شکارچی باگ معروف) که به‌صورت قدم‌به‌قدم از مبانی تا اکسپلویت‌های پیشرفته‌ی XSS را آموزش می‌دهد. این دوره برای افراد مبتدی بسیار مناسب بوده و مواردی چون یافتن نقاط تزریق، ساخت payload، دورزدن فیلترهای رایج و نکات گزارش‌نویسی را پوشش می‌دهد. |



## دورزدن احراز هویت (Authentication Bypass)

نقص در مکانیزم‌های لاگین یا اعتبارسنجی می‌تواند به مهاجم امکان ورود بدون داشتن اعتبار صحیح را بدهد. در تست جعبه‌سیاه، این موارد اغلب ناشی از منطق نادرست، کانفیگ اشتباه یا ترکیب آسیب‌پذیری‌ها هستند. منابع زیر موارد واقعی و روش یادگیری این نوع باگ‌ها را ارائه می‌کنند:

| منبع                                                         | توضیح کوتاه                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| **رایت‌آپ: بایپس احراز هویت از طریق GraphQL** – HackerOne Blog | تحلیل یک گزارش باگ‌بانتی (2024) که نشان می‌دهد چگونه API گراف‌کیوالِ بدون کنترل دسترسی، به محقق اجازه داد تا کاربر ادمین بسازد و محتوای سایت را تغییر دهد. این سناریوی بلک‌باکس تأکید می‌کند که حتی یک مسیر فرعی (مانند GraphQL) می‌تواند احراز هویت را دور بزند و منجر به تصاحب کامل حساب‌ها شود. |
| **رایت‌آپ: تصاحب اکانت با دورزدن MFA** – Medium (Sharat K.)   | مثالی واقعی از زنجیره آسیب‌پذیری که به مهاجم اجازه داد احراز هویت دومرحله‌ای (MFA) را دور بزند. محقق ابتدا با ایمیل خود یک کد MFA دریافت کرد، سپس با یک کوکی نشست صادرشده ناقص به بخش ورود MFA قربانی دسترسی یافت و همان کد را برای ورود به حساب قربانی استفاده کرد. این باگ منطقی نشان می‌دهد مدیریت نادرست کوکی نشست و MFA چگونه می‌تواند پیامدهای بحرانی داشته باشد. |
| **مقاله فنی: ۵ روش غیرمعمول دورزدن لاگین** – Synack Red Team Blog | در این پست، پژوهشگری از Synack پنج سناریوی جالب بایپس احراز هویت را شرح می‌دهد: از سوءاستفاده از توکن رفرش و پیکربندی نادرست SSO گرفته تا مشکلات JWT و تغییر نوع احراز هویت. هر مثال بر اساس باگ‌های واقعی پلتفرم بوده و نشان می‌دهد که حتی مکانیزم‌های مدرن (مثل SSO یا JWT) اگر درست پیاده‌سازی نشوند چگونه قابل دورزدن هستند. |
| **آزمایشگاه: حملات Authentication در PortSwigger**           | مجموعه تمرین‌های عملی که انواع سناریوهای بایپس احراز هویت را شبیه‌سازی می‌کند. برای مثال، یک لابراتوار درباره دورزدن احراز هویت به دلیل ماشین حالت معیوب (Flawed State Machine) است؛ یا مثالی دیگر بایپس OAuth در **implicit flow** را نشان می‌دهد. این محیط‌ها به شما امکان می‌دهند بدون خطر، در شرایط نزدیک به دنیای واقعی، منطق‌های احراز هویت را بشکنید. |
| **اتاق TryHackMe: Authentication Bypass**                    | یک اتاق آموزشی که مراحل مختلف حملات روی صفحه لاگین را آموزش می‌دهد. شامل تکنیک‌هایی مثل پیدا کردن نام‌های کاربری معتبر (از طریق پیام‌های خطا)، دورزدن صفحه لاگین با تزریق SQL ساده، یا سایر روش‌های اعتبارسنجی معیوب است. این اتاق با رویکرد مرحله‌به‌مرحله، برای مبتدیان جهت درک عملی حملات احراز هویت مناسب است. |
| **ابزار تمرین: DVWA (ماژول Brute Force & Weak Auth)**        | برنامه Damn Vulnerable Web App شامل بخش‌هایی برای تمرین بایپس احراز هویت است. به طور مثال در بخش Brute Force می‌توان مکانیزم لاگین ضعیف را شکست، یا در ماژول *Weak Session IDs* مشکلات مدیریت نشست مرتبط با احراز هویت را مشاهده کرد. DVWA یک محیط آفلاین خوب برای تمرین تست بلک‌باکس روی مکانیزم‌های ورود است. |
| **ویدیو آموزشی: حملات Auth Bypass** – John Hammond (YouTube) | در این ویدیو جان هموند یک سناریوی TryHackMe را مرور می‌کند که در آن باید با حدس زدن رمزهای عبور ضعیف و سوءاستفاده از منطق آسیب‌پذیر، به پنل ادمین وارد شد. وی گام‌به‌گام فرآیند تست جعبه‌سیاه (از جمع‌آوری سرنخ تا بهره‌برداری) را نمایش می‌دهد. تماشای این ویدیو دید عملی نسبت به یافتن و بهره‌برداری از باگ‌های احراز هویت می‌دهد. |



## دست‌کاری JWT (JSON Web Token)

توکن‌های JWT به‌طور گسترده برای احراز هویت و مدیریت نشست در وب به‌کار می‌روند. پیکربندی اشتباه یا اعتبارسنجی نادرست JWT می‌تواند به مهاجم اجازه‌ی جعل هویت یا دورزدن دسترسی بدهد. منابع زیر بر آموزش کاربردی حملات JWT تمرکز دارند:

| منبع                                                         | توضیح کوتاه                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| **رایت‌آپ: تصاحب اکانت با سوءاستفاده از JWT** – Medium (Nirdesh R.) | یک باگ‌بانتی بحرانی که پژوهشگر متوجه شد سرویس «Login with Google» توکن JWT دریافتی را به درستی اعتبارسنجی نمی‌کند. او با تغییر دادن فیلد `email` در محتوای JWT توانست داده‌های کاربر دیگری را از سرور دریافت کند و در نهایت اکانت آن کاربر را تصاحب نماید. این گزارش اهمیت بررسی امضای JWT و عدم اعتماد به داده‌های سمت کاربر را نشان می‌دهد. |
| **مقاله مرجع: حملات JWT** – PortSwigger Web Security         | این راهنما مبانی JWT را توضیح داده و انواع آسیب‌پذیری‌های مرتبط با آن را دسته‌بندی می‌کند. مواردی مثل پذیرش JWT با امضای دلخواه یا بدون امضا، کلیدهای امضای ضعیف که قابل بروت‌فورس هستند، تزریق در هدر JWT (پارامترهای `jwk`، `jku`، `kid`) و حملات *algorithm confusion* را پوشش می‌دهد. همچنین چندین لابراتوار تعاملی برای تمرین این حملات معرفی شده است. |
| **آزمایشگاه: JWT Labs در PortSwigger Academy**               | مجموعه‌ای از سناریوهای عملی پیرامون JWT: از عدم‌بررسی امضا (ارسال توکن با امضای جعلی) گرفته تا کلید امضای ضعیف (که می‌توان آن را کرک کرد) و تزریق فیلدهای هدر (مثل `kid`) برای خواندن کلید از مسیر دلخواه. این تمرین‌ها به شما دید عمیقی از نحوه سوءاستفاده از پیاده‌سازی‌های ناامن JWT در حالت بلک‌باکس می‌دهد. |
| **اتاق TryHackMe: JWT Security**                             | محیط آموزشی که اشتباهات رایج در به‌کارگیری JWT و روش بهره‌برداری از آن‌ها را آموزش می‌دهد. برای مثال نشان می‌دهد اگر سرور امضا را بررسی نکند یا از الگوریتم `none` پشتیبانی کند چگونه می‌توان توکن را دستکاری و جعل هویت کرد. همچنین حمله‌ی بروتفورس کلیدهای HS256 و مواردی چون تزریق `kid` برای دسترسی به کلیدهای عمومی را عملی تمرین می‌کند. |
| **ابزارها: JWT.io و افزونه Burp**                            | برای تجزیه‌وتحلیل JWT، ابزار آنلاین **JWT.io** امکان decode/encode کردن JWT و مشاهده‌ی claims را می‌دهد. همچنین افزونه‌هایی مثل **JWT Editor** برای Burp Suite به شما اجازه می‌دهند به راحتی توکن‌ها را در حال رهگیری و ویرایش کنید. برای کرک کردن امضای JWT با الگوریتم HS256 نیز می‌توان از ابزارهایی مثل Hashcat (با wordlist مناسب) استفاده کرد. |
| **ویدیو آموزشی: «Attacking JWTs for Beginners»** – Farah Hawa (YouTube) | یک ویدیوی آموزشی مناسب مبتدیان که توسط Farah (از محققان معروف) تهیه شده است. او ابتدا ساختار و مکانیزم JWT را توضیح می‌دهد، سپس به سراغ سناریوهای حمله می‌رود (مثل دستکاری payload در JWTهای بدون امضا، سوءاستفاده از الگوریتم none، و استفاده از کلید عمومی سرور برای امضای توکن جعلی). این ویدیو به‌طور عملی نشان می‌دهد چگونه می‌توان در تست نفوذ وب، JWTهای آسیب‌پذیر را شناسایی و اکسپلویت کرد. |
| **مقاله آموزشی: «All About JWT Vulnerabilities»** – BugBase Blog | پستی که به زبان ساده نحوه کار JWT را مرور کرده و سپس انواع ضعف‌های امنیتی آن را شرح می‌دهد. برای هر ضعف (مانند عدمِ‌بررسی claimهای Audience یا Expiry، عدم تنظیم Secure Flag برای کوکی JWT، و ...) مثال کاربردی و بهترین راهکارهای پیشگیری ارائه شده است. مطالعه‌ی این منبع بینش جامعی نسبت به حملات JWT و روش‌های جلوگیری از آن‌ها می‌دهد. |



## سیاست امنیت محتوا (CSP) و روش‌های بایپس آن

هدر Content Security Policy برای محدود کردن منابع قابل‌لود در صفحه به‌کار می‌رود و یکی از راهکارهای مهم کاهش ریسک XSS است. اما تنظیم نادرست یا وجود حفره در Policy می‌تواند باعث شود مهاجم علیرغم حضور CSP، کد مخرب خود را اجرا کند. منابع زیر به درک و نفوذ در CSP کمک می‌کنند:

| منبع                                                         | توضیح کوتاه                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| **رایت‌آپ: دورزدن CSP در XSS** – Medium (Grishma A.)          | این بلاگ توضیح می‌دهد چگونه می‌توان یک CSP به‌ظاهر سخت‌گیر را با استفاده از یک XSS بازتابی دور زد. نویسنده ابتدا مفهوم CSP و انواع XSS را شرح داده، سپس نشان می‌دهد با سوءاستفاده از اجازه‌های CSP (مثلاً باز بودن `connect-src`) می‌توان یک درخواست **fetch** خروجی فرستاد و کوکی‌های کاربر را به سرقت برد. این مثال عملی نشان می‌دهد که وجود CSP همیشه هم مصونیت کامل ایجاد نمی‌کند. |
| **مقاله: همه‌چیز درباره CSP و بایپس آن** – Medium (Shaurya S.) | راهنمایی گام‌به‌گام که ابتدا اصول CSP (چیست و چگونه کار می‌کند) را مرور می‌کند و سپس تکنیک‌های پیشرفته دورزدن آن را معرفی می‌نماید. مواردی مانند بهره‌گیری از منابع مجاز غیرمنتظره، دورزدن CSP از طریق sandboxهای JavaScript (مثلاً در AngularJS) یا تزریق Policy خود (Policy Injection) از مباحث پوشش داده‌شده هستند. این مطلب برای درک تئوری و عملی CSP بسیار مفید است. |
| **راهنمای PortSwigger: CSP و بایپس آن**                      | در بخش آکادمی PortSwigger مبحث CSP به طور کامل بیان شده است: از هدف و نحوه تعریف Policyها تا روش‌های بایپس. به عنوان نمونه، سناریوی «تزریق Policy» شرح داده شده که در آن اگر ورودی کاربر در خود هدر CSP بازتاب شود (مثلاً در directive گزارش‌دهی)، مهاجم می‌تواند Policy را تضعیف کند. همچنین حمله‌ی «فرار از sandbox AngularJS» برای دورزدن CSP مطرح شده است[portswigger.net](https://portswigger.net/web-security/cross-site-scripting/content-security-policy#:~:text=,To capture passwords). این منبع رسمی برای یادگیری ساختار CSP و ضعف‌های آن توصیه می‌شود. |
| **ابزار تحلیل: Google CSP Evaluator**                        | ابزاری آنلاین از گوگل که سیاست امنیت محتوای یک وب‌سایت را ارزیابی کرده و نقاط ضعف آن را گوشزد می‌کند. برای شکارچیان باگ، استفاده از CSP Evaluator کمک می‌کند سریعا بفهمند CSP یک برنامه قابل دورزدن است یا خیر (مثلاً وجود wildcardهای ناامن، عدم استفاده از nonce/hash و غیره). |
| **لابراتوار عملی: \*Reflected XSS with CSP Bypass\*** – PortSwigger Labs | یک تمرین عملی که در آن یک صفحه وب دارای CSP سخت‌گیرانه است اما مهاجم باید با پیدا کردن خلأ در Policy آن، XSS بازتابی خود را اجرایی کند. برای مثال، در برخی لابراتوارها بهره‌گیری از قابلیت‌های SVG یا رویدادهای onerror که در Policy فراموش شده‌اند نشان داده می‌شود. انجام این تمرین‌ها درک شما را از ترکیب XSS و CSP بالا می‌برد. |
| **ویدیو: دورزدن CSP در حملات XSS** – کنفرانس CONFidence 2022 (M. Bentkowski)[youtube.com](https://www.youtube.com/watch?v=LFD8RenNY3Y#:~:text=XSS in Google's application and,27) | یک ارائه پیشرفته که یک مورد واقعی XSS در سرویس‌های گوگل را بررسی می‌کند و شیوه‌ی دورزدن CSP در آن را توضیح می‌دهد. این ویدیو (توسط محقق امنیتی گوگل) نشان می‌دهد حتی شرکت‌های بزرگ نیز دچار اشتباهاتی در تنظیم CSP می‌شوند و چگونه یک مهاجم حرفه‌ای می‌تواند از ترکیب ضعف CSP و یک باگ XSS برای حمله بهره ببرد. تماشای این ارائه برای درک عمیق حملات مرتبط با CSP توصیه می‌شود. |



## مدیریت نشست (Session Management)

نحوه ایجاد، نگهداری و خاتمه‌ی نشست‌های کاربران نقش مهمی در امنیت وب دارد. ضعف در مدیریت سشن می‌تواند به حملاتی مثل Session Hijacking (سرقت نشست) یا Session Fixation منجر شود. در باگ‌بانتی، اغلب با باگ‌هایی مواجه می‌شویم که به مهاجم امکان می‌دهد کوکی نشست کاربر دیگر را به‌دست آورده یا جلسات را بدون ابطال معتبر نگه دارد. منابع زیر این مبحث را پوشش می‌دهند:

| منبع                                                         | توضیح کوتاه                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| **رایت‌آپ: ضعف بحرانی در مدیریت نشست** – Medium (Ahmad Z.)    | گزارشی از یک باگ‌بانتی در اوایل 2025 که نشان می‌دهد عدم مدیریت صحیح نشست‌ها چگونه به تصاحب حساب منجر شده است. در این مورد، پس از ورود کاربر، مکانیزم برنامه کوکی جلسه را به‌درستی به‌روزرسانی یا باطل نمی‌کرد و مهاجم توانست با سوءاستفاده از یک شناسه نشست ثابت، به حساب قربانی دسترسی یابد. این باگ که با جایزه $600 همراه بود تأکید می‌کند عملیات‌هایی مثل **خروج کاربر، تغییر رمز یا فعال‌سازی 2FA باید همه نشست‌های قبلی را باطل کنند**. |
| **رایت‌آپ: زنجیره حمله سرقت نشست** – InfoSec Write-ups[infosecwriteups.com](https://infosecwriteups.com/bug-bounty-writeup-2500-reward-for-session-hijack-via-chained-attack-2a4462e01d4d#:~:text=I’d been exploring a website,there was more to discover) | یک سناریوی پیشرفته که محقق با ترکیب چند باگ (XSS + SSTI) توانست کوکی نشست کاربر دیگری را سرقت کرده و سشن وی را تصاحب کند. هرچند این حمله ترکیبی است، اما نشان می‌دهد اگر کوکی‌های نشست محافظت نشده باشند (مثلاً **HttpOnly** تنظیم نشود) یک XSS کوچک می‌تواند به سرعت به تصاحب اکانت منجر شود. مطالعه‌ی این مورد اهمیت تنظیمات Secure و HttpOnly برای کوکی‌ها و اعتبارسنجی سمت سرور را برجسته می‌کند. |
| **مقاله آموزشی: Session Hijacking چیست؟** – Wallarm Blog     | این مقاله مفاهیم جلسات وب و حمله Session Hijacking را توضیح می‌دهد. انواع روش‌های سرقت نشست (مانند دزدیدن کوکی از طریق XSS، حمله‌ی مردِمیانی برای دزدیدن توکن نشست در شبکه‌های باز، یا Session Fixation که مهاجم شناسه نشست خود را به قربانی القا می‌کند) به همراه مثال‌ها بررسی شده‌اند. همچنین نکات دفاعی (مانند استفاده از HTTPS، تنظیم Secure/HttpOnly روی کوکی و مکانیزم Timeout) ارائه گردیده است. مناسب برای فهم پایه‌ای ریسک‌های مدیریت نشست. |
| **آزمایشگاه: TryHackMe – Session Management**                | یک اتاق آموزشی عملی که شما را در محیط یک اپلیکیشن وب راهنمایی می‌کند تا ضعف‌های مدیریت نشست را بیابید. در مراحل این سناریو خواهید دید که مثلاً حذف کردن کوکی در سمت مرورگر بلافاصله دسترسی را قطع نمی‌کند یا logout فقط کوکی را سمت کاربر پاک می‌کند و روی سرور فعال نمی‌شود. با انجام این تمرین، چرخه کامل ایجاد تا خاتمه نشست (Session Lifecycle) و نقاط آسیب‌پذیر آن (ایجاد، ردیابی، انقضا، خاتمه) را به‌صورت عملی درک می‌کنید. |
| **ابزار تست: Burp Suite (Sequencer)**                        | ماژول **Sequencer** در Burp به شما اجازه می‌دهد تصادفی‌بودن شناسه‌های نشست را آنالیز کنید. در یک تست بلک‌باکس، می‌توانید چندصد کوکی `SESSIONID` جمع‌آوری و به Sequencer بدهید تا مشخص شود توزیع بیت‌های آن‌ها تصادفی است یا قابل حدس. این ابزار برای کشف مشکلاتی مانند **ضعف الگوریتم تولید کوکی نشست** یا **ثابت ماندن Session ID بعد از لاگین** بسیار کارآمد است. |
| **ویدیو: «Cookie Stealing & Session Hijacking»** – Hackersploit (YouTube) | این ویدیو به طور عملی نشان می‌دهد چطور یک مهاجم می‌تواند با به‌دست آوردن کوکی نشست کاربر (از طریق ابزارهایی مثل Wireshark در شبکه‌های باز یا با کمک XSS)، خود را به جای آن کاربر جا بزند. همچنین روش‌های جلوگیری نظیر استفاده از HTTPS و مکانیزم‌های Secure flag/HttpOnly توضیح داده می‌شوند. دیدن این ویدیو درک شما را از سناریوهای دنیای واقعی سرقت نشست بالا می‌برد. |



### Links

## 🧪 آسیب‌پذیری‌های XSS (Cross-Site Scripting)

1. **Stored XSS on reports** – HackerOne
    گزارش آسیب‌پذیری XSS ذخیره‌شده در بخش گزارش‌ها.
   https://hackerone.com/reports/485748
2. **Reflected XSS on www.hackerone.com** – HackerOne
    آسیب‌پذیری XSS بازتابی در صفحات مختلف وب‌سایت HackerOne.
   https://hackerone.com/reports/840759
3. **Reflected Cross site Scripting (XSS) on Starbucks** – HackerOne
    آسیب‌پذیری XSS بازتابی در صفحه ورود Starbucks.
   https://hackerone.com/reports/438240
4. **Stored XSS with CSP bypass via labels' color** – HackerOne
    آسیب‌پذیری XSS ذخیره‌شده با دور زدن CSP از طریق رنگ برچسب‌ها.
   https://hackerone.com/reports/1665658
5. **Reflected XSS protected by CSP, with CSP bypass** – Medium
    رایت‌آپ حل یک لابراتوار با XSS بازتابی و دور زدن CSP.
   https://cyberw1ng.medium.com/14-30-lab-reflected-xss-protected-by-csp-with-csp-bypass-779c76173f7a

------

## 🔐 دور زدن احراز هویت (Authentication Bypass)

1. **Authentication Bypass** – HackerOne
    آسیب‌پذیری در فرآیند احراز هویت که منجر به تصاحب حساب می‌شود.
   https://hackerone.com/reports/209008
2. **Two factor authentication bypass** – HackerOne
    دور زدن احراز هویت دومرحله‌ای با استفاده از دسترسی به ایمیل و رمز عبور قربانی.
   https://hackerone.com/reports/2463279
3. **Authentication Bypass - Email Verification code** – HackerOne
    دور زدن فرآیند تأیید ایمیل در هنگام ثبت‌نام.
   https://hackerone.com/reports/1406471
4. **Authentication Bypass Leads To Account Takeover** – HackerOne
    آسیب‌پذیری در منطق ورود که منجر به تصاحب حساب می‌شود.
   https://hackerone.com/reports/1709881
5. **Authentication & Registration Bypass in Newspack Extended Access** – HackerOne
    عدم اعتبارسنجی امضای JWT در نقاط پایانی ثبت‌نام و ورود.
   https://hackerone.com/reports/2472798

------

## 🔑 آسیب‌پذیری‌های JWT (JSON Web Token)

1. **Broken validation of user Id for JWT Token** – HackerOne
    عدم اعتبارسنجی صحیح شناسه کاربر در توکن JWT.
   https://hackerone.com/reports/853145
2. **Account takeover via JWT expiration bypass** – HackerOne
    دور زدن انقضای JWT با تنظیم دستی زمان انقضا.
   https://hackerone.com/reports/1760403
3. **JWT audience claim is not verified** – HackerOne
    عدم بررسی claim مخاطب در JWT که منجر به دسترسی غیرمجاز می‌شود.
   https://hackerone.com/reports/1889161
4. **Authentication Bypass when using JWT with public keys** – HackerOne
    استفاده از الگوریتم‌های متقارن برای اعتبارسنجی JWT که امکان جعل توکن را فراهم می‌کند.
   https://hackerone.com/reports/1210502
5. **JWT weak secret leads to PII leakage** – Medium
    استفاده از کلید ضعیف در امضای JWT که منجر به افشای اطلاعات شخصی می‌شود.
   https://medium.com/@ugs20b126_cic.rajesh/jwt-weak-secret-leads-to-pii-leakage-9941e780fd91

------

## 🛡️ دور زدن سیاست امنیت محتوا (CSP Bypass)

1. **CSP bypass on PortSwigger Web Security** – HackerOne
    بارگذاری اسکریپت‌های دلخواه با دور زدن محدودیت‌های Angular و CSP.
   https://hackerone.com/reports/2279346
2. **CSP-bypass XSS in project settings page** – HackerOne
    آسیب‌پذیری XSS با دور زدن CSP در صفحه تنظیمات پروژه.
   https://hackerone.com/reports/1588732
3. **CSP Bypass: Click handler for links** – HackerOne
    دور زدن CSP از طریق هندلرهای کلیک در لینک‌ها.
   https://hackerone.com/reports/47472
4. **Using form hijacking to bypass CSP** – PortSwigger Research
    استفاده از ربایش فرم برای دور زدن CSP و سرقت اطلاعات ورود.
   https://portswigger.net/research/using-form-hijacking-to-bypass-csp
5. **Reflected XSS protected by CSP, with CSP bypass** – Medium
    حل لابراتوار با XSS بازتابی و دور زدن CSP از طریق تزریق در directive‌های CSP.
   https://cyberw1ng.medium.com/14-30-lab-reflected-xss-protected-by-csp-with-csp-bypass-779c76173f7a

------

## 🔐 مدیریت نشست (Session Management)

1. **Session Hijacking leads to full control** – HackerOne
    سرقت نشست منجر به کنترل کامل حساب کاربر می‌شود.
   https://hackerone.com/reports/1201396
2. **Improper session management** – HackerOne
    مدیریت نادرست نشست که منجر به آسیب‌پذیری‌های امنیتی می‌شود.
   https://hackerone.com/reports/737
3. **Session Management** – HackerOne
    عدم انقضای کوکی نشست پس از خروج کاربر.
   https://hackerone.com/reports/288
4. **Broken Authentication & Session Management** – HackerOne
    ترکیب آسیب‌پذیری‌های احراز هویت و مدیریت نشست که منجر به تصاحب حساب می‌شود.
   https://hackerone.com/reports/222082
5. **Broken Authentication and Session Management** – HackerOne
    آسیب‌پذیری در مدیریت نشست که امکان ورود بدون اعتبارسنجی را فراهم می‌کند.
   https://hackerone.com/reports/1167029

------



    	 "https://hackerone.com/reports/485748",
        "https://hackerone.com/reports/840759",
        "https://hackerone.com/reports/438240",
        "https://hackerone.com/reports/1665658",
        "https://cyberw1ng.medium.com/14-30-lab-reflected-xss-protected-by-csp-with-csp-bypass-779c76173f7a",
        "https://hackerone.com/reports/209008",
        "https://hackerone.com/reports/2463279",
        "https://hackerone.com/reports/1406471",
        "https://hackerone.com/reports/1709881",
        "https://hackerone.com/reports/2472798",
        "https://hackerone.com/reports/853145",
        "https://hackerone.com/reports/1760403",
        "https://hackerone.com/reports/1889161",
        "https://hackerone.com/reports/1210502",
        "https://medium.com/@ugs20b126_cic.rajesh/jwt-weak-secret-leads-to-pii-leakage-9941e780fd91",
        "https://hackerone.com/reports/2279346",
        "https://hackerone.com/reports/1588732",
        "https://hackerone.com/reports/47472",
        "https://portswigger.net/research/using-form-hijacking-to-bypass-csp",
        "https://cyberw1ng.medium.com/14-30-lab-reflected-xss-protected-by-csp-with-csp-bypass-779c76173f7a",
        "https://hackerone.com/reports/1201396",
        "https://hackerone.com/reports/737",
        "https://hackerone.com/reports/288",
        "https://hackerone.com/reports/222082",
        "https://hackerone.com/reports/1167029"



## XSS and Browsers

## 🧠 ۱. قوانین امنیتی مرورگرها در برابر XSS

| مفهوم                             | توضیح                                                        |
| --------------------------------- | ------------------------------------------------------------ |
| **Same-Origin Policy (SOP)**      | پایه‌ی امنیت مرورگرها؛ جلوگیری از دسترسی اسکریپت‌ها به داده‌های سایت‌های دیگر |
| **Content Security Policy (CSP)** | محدودکننده‌ی منابع قابل اجرا؛ از XSS جلوگیری می‌کند ولی قابل بایپس است (اگر اشتباه پیکربندی شود) |
| **Trusted Types**                 | API امنیتی جدید در مرورگرها برای جلوگیری از XSS DOM-based    |
| **XSS Auditor (منسوخ)**           | محافظ قدیمی Chrome برای فیلتر XSS بازتابی (در حال حاضر حذف شده) |
| **Auto HTML escaping**            | رفتار داخلی برخی فریم‌ورک‌ها برای جلوگیری از تزریق HTML ناخواسته (مثل React, Vue) |
| **Execution Contexts**            | هر داده وارد DOM ممکنه در یکی از این contextها قرار بگیره: HTML, JavaScript, Attribute, URL و CSS—و در هرکدوم قوانین متفاوتی برای اجرای کد هست |



------

## ⚛️ ۲. رفتار React در برابر XSS

React ذاتاً امنه، چون:

- همه ورودی‌ها رو escape می‌کنه
- به جای ساختن DOM با `innerHTML`، از `createElement` استفاده می‌کنه

اما ممکنه ناامن بشه اگر:

| مورد                                                         | آسیب‌پذیر؟                                                    |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| `dangerouslySetInnerHTML`                                    | ✅ بله، محل رایج XSS                                          |
| استفاده از `eval()` در event handlers                        | ✅ بله، XSS DOM-based                                         |
| بارگذاری کتابخانه‌های شخص ثالث                                | ✅ بله، اگر sanitize نکنن                                     |
| استفاده از `setState()` با ورودی مستقیم از کاربر             | ❌ نه، ولی می‌تونه منجر به render خطرناک بشه در ترکیب با innerHTML |
| استفاده از URL بدون بررسی در props (مثل `<img src={url} />`) | ✅ بله، XSS via href/src/event                                |



------

## 🔬 ۳. موارد تخصصی مرورگر:

- اگر `Content-Type` اشتباه باشه (`text/html` به جای `application/json`) مرورگر ممکنه تلاش کنه JSON رو به‌عنوان HTML اجرا کنه.
- برخی حملات XSS از طریق MIME sniffing و iframe injection امکان‌پذیرند.
- بعضی مرورگرها مانند Chrome اجازه اجرای inline JS رو در `about:blank` در صورت خاص می‌دن (مربوط به CSP و trusted origin).
- اگر CSP شامل `'unsafe-inline'` باشه یا nonce غلط پیکربندی شده باشه، حملات XSS راحت‌تر می‌شن.



## React, JS Deeper

## ⚛️ بخش اول: امنیت داخلی React — چرا به‌صورت پیش‌فرض در برابر XSS امن است؟

| ویژگی React                        | توضیح                                                        |
| ---------------------------------- | ------------------------------------------------------------ |
| `createElement` به جای `innerHTML` | React به‌جای تزریق مستقیم HTML، از Virtual DOM و API امن `document.createElement` استفاده می‌کند. |
| HTML escaping خودکار               | تمام props ورودی به عناصر JSX به‌صورت خودکار escape می‌شوند. مثلاً: `<div>{userInput}</div>` → بدون XSS |
| جلوگیری از attribute injection     | حتی استفاده از کد مثل `<div data-id={userInput}>` توسط React sanitize می‌شود، مگر اینکه عمداً bypass کنید. |



------

## ☣️ بخش دوم: نقاط آسیب‌پذیر رایج در React

| سناریو خطرناک                          | مثال                                                      | توضیح                                                        |
| -------------------------------------- | --------------------------------------------------------- | ------------------------------------------------------------ |
| استفاده از `dangerouslySetInnerHTML`   | `<div dangerouslySetInnerHTML={{ __html: userInput }} />` | هرگونه escape از بین می‌رود و داده مستقیماً وارد DOM می‌شود—منبع اصلی XSS |
| استفاده نادرست از `ref` و `innerHTML`  | `ref.current.innerHTML = userInput`                       | دور زدن سیستم امن React                                      |
| استفاده از third-party component آلوده | مثلا کتابخانه‌های رندر Markdown                            | اگر sanitize نکنند یا از نسخه امن استفاده نشود، XSS ممکن است رخ دهد |
| event handlers با eval یا Function     | `onClick={() => eval(userInput)}`                         | اجرای مستقیم داده‌ی ورودی بدون بررسی منبع                     |



------

## 🧪 بخش سوم: حملات عملی در React

### 1. Stored XSS در React

```
// خطرناک:
const Comment = ({ text }) => (
  <div dangerouslySetInnerHTML={{ __html: text }} />
);

// payload:
<script>alert(document.domain)</script>
```

### 2. Attribute Injection

```
// ناامن اگر در دست userInput باشد:
<img src={userInput} />
// payload:
"onerror=alert(1)" → <img src="onerror=alert(1)">
```

### 3. React Router XSS

در مسیریابی سمت کلاینت اگر پارامترها sanitize نشوند:

```
<Route path="/profile/:username" component={Profile} />
// اگر username از URL در innerHTML نمایش داده شود، خطرناک است.
```

------

## 🛡️ بخش چهارم: راهکارهای دفاعی مخصوص React

| راهکار                                        | ابزار یا توضیح                                               |
| --------------------------------------------- | ------------------------------------------------------------ |
| ❌ اجتناب از `dangerouslySetInnerHTML`         | مگر اینکه با sanitize شده باشد (`DOMPurify`, `sanitize-html`) |
| ✅ استفاده از کتابخانه‌های امن Markdown         | `marked` همراه با `DOMPurify` یا `react-markdown` با `rehype-sanitize` |
| ✅ استفاده از Trusted Types (اگر CSP فعال است) | برای مرورگرهایی که پشتیبانی می‌کنند، مانع از assign کردن string‌های مشکوک به DOM می‌شود |
| ✅ از audit toolها استفاده کن                  | مانند ESLint plugin برای بررسی استفاده نادرست از innerHTML یا eval |





## RoadMap JS, React

##  نقشه‌ی یادگیری عمیق XSS در React و JS (مرحله به مرحله)

### 🔹 **مرحله ۱: درک هسته‌ی رفتار مرورگر و DOM**

قبل از اینکه به React بپردازیم، باید بفهمیم:

- مرورگر چطور HTML رو به DOM تبدیل می‌کنه؟
- چطور در زمان پارس کردن `<script>`، `<img onerror>` یا `href="javascript:"` اجرا انجام می‌شه؟
- Contextها (HTML, Attribute, JavaScript, URL, CSS) دقیقاً چه تفاوتی دارند؟

📌 تمرین:

- ساختن یک فایل HTML ساده با انواع context:

```
<!-- HTML context -->
<div>{input}</div>

<!-- Attribute context -->
<input value="{input}">

<!-- JS context -->
<script>var data = '{input}';</script>

<!-- URL context -->
<a href="{input}">link</a>
```

و بررسی اینکه چه payloadهایی در هر کدام اجرا می‌شوند یا نه.

------

### 🔹 **مرحله ۲: واکنش مرورگر به تغییرات DOM**

بفهمیم چه زمانی داده در DOM فقط نمایش داده می‌شه و چه زمانی *تبدیل به کد اجرایی* می‌شه:

- فرق بین `element.innerText`، `element.innerHTML`، و `element.setAttribute`
- چرا `innerHTML = "<img src=x onerror=alert(1)>"` خطرناکه ولی `textContent = "<img ...>"` نه؟

📌 تمرین:
 تست کردن هرکدام در DevTools با payloadهای ساده و مشاهده نتیجه.

------

### 🔹 **مرحله ۳: آشنایی با رفتار React**

الان وقتشه که روی React تمرکز کنیم:

| مکانیزم                         | رفتار پیش‌فرض |
| ------------------------------- | ------------ |
| JSX text                        | Escape می‌شه  |
| JSX attribute                   | Escape می‌شه  |
| JSX + `dangerouslySetInnerHTML` | ❗ حذف محافظت |



📌 تمرین:

- اجرای کدهای ساده JSX در React و بررسی کد HTML نهایی در DevTools
- مشاهده اینکه چطور React هیچ‌وقت مستقیم از `eval()` یا `innerHTML` استفاده نمی‌کنه

------

### 🔹 **مرحله ۴: بررسی شرایط ناامن در React**

این جا دقیقاً همون جاییه که React با اینکه *به ظاهر امنه*، قابل آسیب می‌شه:

| کد                                                        | آسیب‌پذیره؟ | چرا؟                                                         |
| --------------------------------------------------------- | ---------- | ------------------------------------------------------------ |
| `<div>{userInput}</div>`                                  | ❌          | React escape می‌کنه                                           |
| `<img src={userInput}>`                                   | ✅          | اگر مقدار src کنترل‌شده باشه، می‌شه `"javascript:..."` یا `"x" onerror="..."` گذاشت |
| `<div dangerouslySetInnerHTML={{ __html: userInput }} />` | ✅          | تمام escapeها دور زده می‌شن                                   |
| `<a href={userInput}>`                                    | ✅          | مخصوصاً اگر `javascript:` باشه و CSP ضعیف باشه                |



------

### 🔹 **مرحله ۵: مشاهده تفاوت در مرورگر**

📌 تمرین:

- فعال کردن CSP با و بدون `'unsafe-inline'`
- فعال‌سازی Trusted Types در CSP و بررسی تفاوت
- آزمایش این‌که آیا payloadی که در مرورگر A اجرا می‌شه، در مرورگر B اجرا نمی‌شه؟ (مثلاً Edge vs Chrome)

------

## 🔎 نتیجه نهایی: می‌فهمی که...

- XSS فقط یک `script` ساده نیست—یک *روند* برای رسیدن به اجرای ناخواسته در context خاصه
- React در ظاهر امنه اما در محیط‌های پیچیده‌تر (markdown, CMS, third-party input) راحت قابل شکستن می‌شه
- مرورگرها به context، تفسیر MIME، و رفتار رویدادها به‌شدت حساسن



## Learn Auth Deeper

## 🧠 محورهای یادگیری عمیق در **Authentication Security**

| حوزه                                    | زیرموضوعات کلیدی                                             |
| --------------------------------------- | ------------------------------------------------------------ |
| 🔑 **Password-Based Auth**               | ورود سنتی، حملات brute force، credential stuffing، session hijacking |
| 🪪 **Token-Based Auth**                  | JWT, opaque tokens, refresh tokens، حملات مثل JWT tampering یا none algorithm |
| 🔁 **SSO & OAuth**                       | حملات در flowهای OAuth2 (implicit, auth code, hybrid)، open redirect abuse |
| 📲 **Multi-Factor Authentication (MFA)** | MFA bypass، استفاده اشتباه از session بین مراحل              |
| 🔄 **Session Lifecycle**                 | مدیریت نشست، session fixation، logout flaws                  |
| 🧪 **Logic & Race Conditions**           | شرایط رقابتی، bypass منطق تغییر رمز/تأیید ایمیل، session upgrade bypass |



------

## 👣 پیشنهاد مسیر مرحله‌ای یادگیری عمیق Auth:

### ✅ **مرحله ۱: شناخت پایه‌ی Auth**

- تفاوت بین Session-based vs Token-based auth
- نحوه مدیریت sessionId و JWT در مرورگر
- SameSite, Secure, HttpOnly → روی کوکی‌ها

### ✅ **مرحله ۲: حملات شناخته‌شده**

- **Credential Stuffing** (با داده‌های نشت‌شده)
- **Authentication Bypass via flawed logic**
- **JWT Forgery with alg=none / public key misuse**
- **Session Fixation** (مهاجم session قبل از login تولید می‌کند)

### ✅ **مرحله ۳: Token Manipulation**

- تحلیل کامل ساختار JWT (`header.payload.signature`)
- حمله با تغییر `alg: none` یا `RS256 → HS256`
- تزریق در claimها مثل `aud`, `sub`, `exp`, `kid`

### ✅ **مرحله ۴: OAuth Attacks**

- حملات Open Redirect
- **Authorization Code Interception**
- **Login CSRF / Login Confusion**
- **Forced Login → Account Takeover**

### ✅ **مرحله ۵: Session Upgrade / Downgrade**

- وقتی MFA فقط یک مرحله جداست ولی session آپگرید نمی‌شه
- استفاده دوباره از token بعد از تغییر رمز یا logout



## 🧠 نقشه مسیر برای **درک عمیق و تخصصی Auth Security**

### 🔹 ۱. **شناخت درونی Session Lifecycle**

> کاربر چه زمانی وارد شده؟ چه زمانی نشستش باید باطل بشه؟ آیا نشست قبل از ورود و بعد از خروج یکیه؟

| سؤال مهم                                                | مفهوم                          |
| ------------------------------------------------------- | ------------------------------ |
| آیا session بعد از تغییر رمز همچنان معتبره؟             | 🔥 Session Upgrade Bug          |
| آیا کوکی logout می‌شه ولی سرور همچنان اونو معتبر می‌دونه؟ | ❌ Session Invalidation Failure |
| آیا session پس از فعال‌سازی 2FA آپگرید می‌شه؟             | ⚠️ MFA Session Logic Flaw       |



------

### 🔹 ۲. **JWT عمیق: Header و Signature Manipulation**

| حمله                   | نحوه انجام                                                |
| ---------------------- | --------------------------------------------------------- |
| `alg: none`            | تغییر هدر JWT و حذف امضا                                  |
| `HS256 با کلید public` | سروری که اشتباهی کلید public رو به‌جای secret استفاده کرده |
| `kid` Injection        | بارگذاری کلید خاص از مسیر دلخواه روی سرور                 |
| زمان‌بندی‌ها             | جعل `iat`, `exp`, `nbf` برای دسترسی موقتی یا دائمی        |



🔍 مثال:

```
{
  "alg": "none",
  "typ": "JWT"
}
.
{
  "user": "admin"
}
.
""  ← بدون امضا!
```

------

### 🔹 ۳. **SSO/OAuth Misuse and Attacks**

> بیشتر برنامه‌ها فقط از OAuth به‌عنوان Login استفاده می‌کنن ولی **پیاده‌سازی اشتباه** رایجه!

| مورد                                          | آسیب                                    |
| --------------------------------------------- | --------------------------------------- |
| OAuth flow بدون بررسی `state`                 | CSRF روی login                          |
| سوءاستفاده از open redirect در `redirect_uri` | اجرای XSS یا hijack session             |
| login confusion                               | پیوند دادن حساب اشتباه به حساب کاربر    |
| دستکاری `aud` یا `iss` در توکن‌های ارسالی      | اعتبارسنجی ناقص سمت سرور                |
| reuse کردن Authorization Code                 | اگر سرور ذخیره نکنه که یه بار مصرف بوده |



------

### 🔹 ۴. **Bypassing MFA با گپ‌های منطقی**

| حمله                                    | شرح                                             |
| --------------------------------------- | ----------------------------------------------- |
| جدا بودن مراحل MFA از session نهایی     | attacker می‌تونه MFA بپره و با کوکی دسترسی بگیره |
| استفاده از session قبلی قبل از MFA      | MFA فقط صفحه نمایشی باشه نه واقعاً auth logic    |
| استفاده اشتباه از trusted device cookie | حمله از طریق device spoofing                    |



------

### 🔹 ۵. **Race Condition در فرآیند تغییر رمز / ثبت‌نام / تأیید ایمیل**

| سناریو                                        | آسیب                            |
| --------------------------------------------- | ------------------------------- |
| تغییر ایمیل و ارسال همزمان درخواست فعال‌سازی   | hijack اکانت قبل از تأیید       |
| reset کردن رمز و login هم‌زمان با session قدیم | Session Fixation روی اکانت دیگر |
| ثبت‌نام مجدد با ایمیل موجود و شرایط هم‌زمان     | TOTP/2FA confusion              |



### 📊 نمونه‌های واقعی از آسیب‌پذیری‌های احراز هویت در HackerOne

| #    | عنوان آسیب‌پذیری                                              | نوع آسیب‌پذیری                  | شرح مختصر                                                    | لینک گزارش                            |
| ---- | ------------------------------------------------------------ | ------------------------------ | ------------------------------------------------------------ | ------------------------------------- |
| 1    | Bypass Password Authentication to Update the Password        | دور زدن احراز هویت             | امکان تغییر رمز عبور بدون نیاز به رمز فعلی                   | https://hackerone.com/reports/982293  |
| 2    | Authentication Bypass via Username Enumeration + Brute Force | دور زدن احراز هویت             | ترکیب افشای نام کاربری و حمله Brute Force برای تصاحب حساب    | https://hackerone.com/reports/209008  |
| 3    | Improper Authentication via Previous Backup Code Login       | احراز هویت نادرست              | امکان ورود به حساب کاربری با استفاده از کد پشتیبان قدیمی پس از تغییر رمز عبور | https://hackerone.com/reports/1485788 |
| 4    | Two-Factor Authentication Bypass                             | دور زدن احراز هویت دومرحله‌ای   | دسترسی به حساب کاربری بدون نیاز به کد 2FA                    | https://hackerone.com/reports/2463279 |
| 5    | Improper Authentication - 2FA OTP Reusable                   | احراز هویت نادرست              | امکان استفاده مجدد از کد OTP در احراز هویت دومرحله‌ای         | https://hackerone.com/reports/2529780 |
| 6    | Authentication Bypass with Usage of PreSignedURL             | دور زدن احراز هویت             | دسترسی به فایل‌ها بدون احراز هویت با استفاده از لینک‌های پیش‌امضا شده | https://hackerone.com/reports/2337427 |
| 7    | Authentication Bypass on gist.github.com through SSH Certificates | دور زدن احراز هویت             | امکان تغییر گیت‌های خصوصی دیگر کاربران از طریق گواهی‌های SSH   | https://hackerone.com/reports/1901040 |
| 8    | Broken Authentication Session Token Bug                      | اشکال در توکن جلسه             | امکان استفاده از توکن جلسه پس از خروج از حساب کاربری         | https://hackerone.com/reports/948345  |
| 9    | SAML Signup Domain Enforcement Bypass                        | دور زدن محدودیت دامنه در SAML  | امکان ثبت‌نام در سازمان‌های محدودشده با استفاده از SAML        | https://hackerone.com/reports/2101076 |
| 10   | Basic Authentication Heap Overflow                           | سرریز حافظه در احراز هویت پایه | امکان سرریز داده در حافظه با استفاده از احراز هویت پایه      | https://hackerone.com/reports/641240  |





## Top Vulns in H1

### 🔟 آسیب‌پذیری‌های برتر در HackerOne مرتبط با Authentication و XSS

1. **Cross-Site Scripting (XSS)**
   - توضیح: امکان اجرای اسکریپت‌های مخرب در مرورگر کاربر از طریق ورودی‌های کنترل‌نشده.
   - مثال: [Stored XSS در صفحه پروفایل Acronis](https://hackerone.com/reports/1084183)[HackerOne](https://hackerone.com/reports/1084183?utm_source=chatgpt.com)
2. **Improper Authentication**
   - توضیح: عدم اعتبارسنجی مناسب هویت کاربر، که می‌تواند منجر به دسترسی غیرمجاز شود.
   - مثال: [گزارش HackerOne درباره آسیب‌پذیری‌های احراز هویت](https://www.hackerone.com/blog/hackerone-top-10-most-impactful-and-rewarded-vulnerability-types)[HackerOne+4HackerOne+4HackerOne+4](https://www.hackerone.com/blog/hackerone-top-10-most-impactful-and-rewarded-vulnerability-types?utm_source=chatgpt.com)
3. **Information Disclosure**
   - توضیح: افشای اطلاعات حساس به دلیل پیکربندی نادرست یا کنترل‌های امنیتی ناکافی.
   - مثال: [گزارش HackerOne درباره افشای اطلاعات](https://www.hackerone.com/blog/hackerone-top-10-most-impactful-and-rewarded-vulnerability-types)
4. **Privilege Escalation**
   - توضیح: امکان ارتقاء سطح دسترسی کاربر به سطوح بالاتر بدون مجوز مناسب.
   - مثال: [گزارش HackerOne درباره ارتقاء سطح دسترسی](https://www.hackerone.com/blog/hackerone-top-10-most-impactful-and-rewarded-vulnerability-types)[HackerOne+4HackerOne+4HackerOne+4](https://www.hackerone.com/blog/hackerone-top-10-most-impactful-and-rewarded-vulnerability-types?utm_source=chatgpt.com)
5. **SQL Injection**
   - توضیح: تزریق دستورات SQL مخرب از طریق ورودی‌های کاربر به پایگاه داده.
   - مثال: [گزارش HackerOne درباره تزریق SQL](https://www.hackerone.com/blog/hackerone-top-10-most-impactful-and-rewarded-vulnerability-types)
6. **Code Injection**
   - توضیح: امکان تزریق و اجرای کد مخرب در برنامه به دلیل اعتبارسنجی ناکافی ورودی‌ها.
   - مثال: [گزارش HackerOne درباره تزریق کد](https://www.hackerone.com/blog/hackerone-top-10-most-impactful-and-rewarded-vulnerability-types)
7. **Server-Side Request Forgery (SSRF)**
   - توضیح: امکان ارسال درخواست‌های مخرب از سمت سرور به منابع داخلی یا خارجی.
   - مثال: [گزارش HackerOne درباره SSRF](https://www.hackerone.com/blog/hackerone-top-10-most-impactful-and-rewarded-vulnerability-types)
8. **Insecure Direct Object Reference (IDOR)**
   - توضیح: دسترسی غیرمجاز به اشیاء یا منابع از طریق ارجاع مستقیم بدون بررسی مجوز.
   - مثال: [گزارش HackerOne درباره IDOR](https://www.hackerone.com/blog/hackerone-top-10-most-impactful-and-rewarded-vulnerability-types)[HackerOne](https://www.hackerone.com/blog/hackerone-top-10-most-impactful-and-rewarded-vulnerability-types?utm_source=chatgpt.com)
9. **Improper Access Control**
   - توضیح: عدم اعمال کنترل‌های دسترسی مناسب، که می‌تواند منجر به دسترسی غیرمجاز شود.
   - مثال: [گزارش HackerOne درباره کنترل دسترسی نادرست](https://www.hackerone.com/blog/hackerone-top-10-most-impactful-and-rewarded-vulnerability-types)
10. **Cross-Site Request Forgery (CSRF)**
    - توضیح: وادار کردن کاربر به انجام عملیات ناخواسته در برنامه‌ای که در آن احراز هویت شده است.
    - مثال: گزارش HackerOne درباره CSRF