# اطلاعات مالی کاربر


## درخواست برداشت



```plane

/api/v1/apiwithdraw/
headers = {'Authorization': 'Token 9054f7aa9305e012b3c2300408c3dfdf390fcddf'}

```


> درصورت فراخوانی صحیح پاسخ به این صورت خواهد بود:

```plane

{
    "amount": "10.000000000000000000"
}


```

برای درخواست برداشت رمز ارز از این api استفاده کنید. 



 متد:
POST
نوع:
خصوصی
محدودیت فراخوانی:



## تاریخچه واریز رمز ارز



```plane

/api/v1/deposit/list/
headers = {'Authorization': 'Token 9054f7aa9305e012b3c2300408c3dfdf390fcddf'}


```


> درصورت فراخوانی صحیح پاسخ به این صورت خواهد بود:

```plane

HTTP 200 OK
Allow: GET, HEAD, OPTIONS
Content-Type: application/json
Vary: Accept

{
    "count": 1,
    "next": null,
    "previous": null,
    "results": [
        {
            "created": "2022-04-12T17:18:53.909319+04:30",
            "amount": "49",
            "status": "done",
            "link": "",
            "out_address": "as",
            "coin": "USDT",
            "network": "BSC",
            "trx_hash": null,
            "fee_amount": "1"
        }
    ]
}


```

برای مشاهده تاریخچه واریزهای خود از این api استفاده کنید.

متد:
GET
نوع:

خصوصی


محدودیت فراخوانی:






## دریافت و ساخت کیف پول



```plane

/api/v1/deposit/address/?coin= &network=
headers = {'Authorization': 'Token 9054f7aa9305e012b3c2300408c3dfdf390fcddf'}

```


> درصورت فراخوانی صحیح پاسخ به این صورت خواهد بود:

```plane

HTTP 200 OK
Allow: GET, HEAD, OPTIONS
Content-Type: application/json
Vary: Accept

{
    "address": "0xd0d72802b786c45a9ccfcd7f52ac9d58b96e275f"
}

```

برای دریافت آدرس کیف پول  و یا ساخت کیف پول جدید از این  api استفاده کنید. در این api با مشخص کردن مقادیر coin و network در کوپری پارام در صورت وجود کیف پول آدرس آن برگردانده میشود و در صورت عدم وجود کیف پول ساخته شده و آدرس کیف ساخته شده برگردانده می‌شود.

مقادیر مجاز  coin و network:

متد:
GET
نوع:

خصوصی

محدودیت فراخوانی:



## دریافت مقادیر آزاد هر کیف پول



```plane

/api/v1/wallet/balance/
headers = {'Authorization': 'Token 9054f7aa9305e012b3c2300408c3dfdf390fcddf'}

```


> درصورت فراخوانی صحیح پاسخ به این صورت خواهد بود:

```plane

    {
        "wallet": [
            {
                "asset": "USDT",
                "free": "100000"
            },
            {
                "asset": "BTC",
                "free": "100000"
            },
            {
                "asset": "IRT",
                "free": "100000"
            }
        ]
    }


```

برای دریافت لیست کیف پول ها و مقادیر آزاد هر کدام میتوانید از این api استفاده کنید.
مقادیر مجاز  coin و network:

متد:
GET
نوع:

خصوصی
محدودیت فراخوانی:
