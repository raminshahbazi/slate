# معامله در بازار


برای استفاده از api های این بخش استفاده از  توکن و تعریف ip های مجاز الزامی است. برای دریافت توکن و تعریف ip های مجاز لازم است به پنل حساب کاربری خود مراجعه کنید. توجه به این نکته ضروری است که فقط در هنگام درخواست نخست امکان مشاهده توکن وجود دارد و در درخواست های بعدی برای حفظ مسائل امنیتی توکن به صورت کامل نشان داده نمیشود. از این رو ضروری است تا توکن نمایش داده شده در درخواست اول را کپی کنید. در صورت فراموشی توکن ارسال شده لازم است تا توکن قبلی را حذف کرده و توکن جدیدی بسازید.


## ثبت سفارش جدید

```plane

POST https://api.raastin.com/api/v1/market/orders/ HTTP/1.1
Authorization: Token yourTOKENhereHEX0000000000


```

> درصورت فراخوانی صحیح پاسخ به این صورت خواهد بود:

```plane

{
    "id": 620881,
    "created": "2022-04-27T17:03:57.002570+04:30",
    "symbol": "BTCIRT",
    "amount": "100.00000",
    "filled_amount": "0.00000",
    "price": "100000",
    "filled_price": null,
    "side": "buy",
    "fill_type": "limit",
    "status": "new"
}

```

برای ثبت سفارش معامله در بازار راستین از این api استفاده کنید. توجه به این نکته ضروری است که ثبت سفارش الزاما به معنی انجام معامله نیست. با درخواست مشاهده وضعیت سفارش می توانید از وضعیت سفارش خود مطلع شوید.
برای استفاده از این api لازم است تا در قسمت header توکن خود را ارسال کنید.


- آدرس : `https://api.raastin.com/api/v1/market/orders/`
- متد : `POST`
- نوع :‌ خصوصی


  پارامترهای ورودی:

پارامتر     | نوع    | پیش‌فرض   |   توضیحات     | نمونه
----------- | ----   | ------   |   ---------   | -----
symbol | string | الزامی | بازار| -
amount | string, int | الزامی | مقدار سفارش| -
price | string, int | الزامی | قیمت سفارش| -
side | string(buy, sell) | buy | نوع سفارش| -
fill_type | string(limit, market) | limit | نحوه اجرای سفارش| -
market | string(spot, margin, loan) | spot | - | -

حالات خطا: 
<aside class="warning">
نکات و ملاحظات

- واحد قیمت در بازار های ریالی به ریال است. 
- واحد قیمت در بازارهای تتری نیز تتر میباشد.
- واحد پارامتر amount بر اساس رمز ارز مبدا است.
</aside>


## لیست سفارش ها



```plane

GET https://api.raastin.com/api/v1/market/orders/ HTTP/1.1
Authorization: Token yourTOKENhereHEX0000000000

```


> درصورت فراخوانی صحیح پاسخ به این صورت خواهد بود:

```plane

{
    "count": 1,
    "next": null,
    "previous": null,
    "results": [
        {
            "id": 620597,
            "created": "2022-04-27T16:06:29.953660+04:30",
            "symbol": "BTCIRT",
            "amount": "100.00000",
            "filled_amount": "0.00000",
            "price": "100000",
            "filled_price": null,
            "side": "buy",
            "fill_type": "limit",
            "status": "new"
        }
    ]
}


```

 برای دریافت لیست همه  سفارش ها میتوانید از این api استفاده کنید.

ارسال توکن دریافتی در header برای استفاده از این api ضروری است.

- آدرس : `https://api.raastin.com/api/v1/market/orders/`
- متد : `GET`
- نوع :‌ خصوصی


همچنین در این api امکان فیلتر کردن بر اساس وضعیت سفارش و بازار وجود دارد.

آدرس:
`https://api.raastin.com/api/v1/market/orders/?symbol=&status=`

مقادیر مجاز برای symbol همان بازارهای راستین است و مقادیر مجاز برای status , 
Canceled,new,filled 
 است.

برای دریافت اطلاعات مربوط به یک سفارش کافیست در انتهای ادرس api مربوط به لیست سفارشات id سفارش مورد نظر را قرار دهید.

`https://api.raastin.com/api/v1/market/orders/1`


## لغو سفارش



```plane
POST https://api.raastin.com/api/v1/market/orders/cancel/ HTTP/1.1
Authorization: Token yourTOKENhereHEX0000000000
id: 1054

```


> درصورت فراخوانی صحیح پاسخ به این صورت خواهد بود:

```plane

{
    "id": "620597",
    "canceled_at": "2022-04-27 12:31:49.827768+00:00"
}

```

برای لغو یک سفارش میتوانید از  api استفاده کنید.


- آدرس : `https://api.raastin.com/api/v1/market/orders/cancel/`
- متد : `POST`
- نوع :‌ خصوصی




ارسال توکن در header برای استفاده از این api ضروری است.


پارامتر     | نوع    | پیش‌فرض   |   توضیحات     | نمونه
----------- | ----   | ------   |   ---------   | -----
id | int | الزامی | شناسه سفارش| 1054
