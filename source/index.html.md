---
title: API Reference
lang: fa

language_tabs: # must be one of https://git.io/vQNgJ
  - plane


toc_footers:
  - <a href='https://raastin.com/account/api-management'>ساخت api token </a>
  - <a href='https://raastin.com'>راستین</a>

includes:
  - markets
  - trade
  - user

search: false

code_clipboard: true

meta:
  - name: مستندات صرافی راستین
    content: مستندات صرافی راستین
---

# مستندات API راستین

سلام. مفتخریم که در صرافی راستین‌‌، خدمات با کیفیت را با کمترین کارمزد در اختیار شما مشتریان محترم قرار دهیم. با توجه به اهمیت استفاده از سرویس API برای انجام معاملات خودکار این سند تهیه شده است.

# احراز هویت و توکن

> جهت احراز هویت از این HTTP Header استفاده کنید:

```plane
Authorization: Token yourTOKENhereHEX0000000000
```


> بخاطر داشته باشید که `yourTOKENhereHEX0000000000` را با توکن خود جایگذاری کنید.


API ها در راستین به دو دسته تقسیم می‌شوند. دسته نخست  API های عمومی است که نیازی به احراز هویت و ارسال توکن نیست. برای دسترسی به API های خصوصی لازم است  توکن به عنوان HTTP Header درخواست به صورت زیر ارسال شود:




<aside class="notice">
برای دریافت توکن می‌توانید با مراجعه به پنل کاربری خود در راستین  از بخش حساب کاربری وارد صفحه <a href="https://raastin.com/account/api-management">مدیریت apiها</a> شده  و توکن خود را دریافت نمایید.
</aside>



<h1 id="quickstart">راهنمای شروع به کار با API</h1>

- محدودیت فراخوانی :‌ ۱۰۰ درخواست در دقیقه
