# اطلاعات مالی کاربر


## درخواست برداشت



```plane

POST https://api.raastin.com/api/v1/apiwithdraw/ HTTP/1.1
Authorization: Token yourTOKENhereHEX0000000000


```


> درصورت فراخوانی صحیح پاسخ به این صورت خواهد بود:

```

{
    "amount": "10.000000000000000000"
}


```

برای درخواست برداشت رمز ارز از این api استفاده کنید. 


- آدرس : `https://api.raastin.com/api/v1/apiwithdraw`
- متد : `POST`
- نوع :‌ خصوصی



## تاریخچه واریز رمز ارز



```plane

GET https://api.raastin.com/api/v1/deposit/list/ HTTP/1.1
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

- آدرس : `https://api.raastin.com/api/v1/deposit/list/`
- متد : `GET`
- نوع :‌ خصوصی


## دریافت و ساخت کیف پول



```plane

GET https://api.raastin.com/api/v1/deposit/address/?coin= &network= HTTP/1.1
Authorization: Token yourTOKENhereHEX0000000000

```


> درصورت فراخوانی صحیح پاسخ به این صورت خواهد بود:

```

{
    "address": "0xd0d72802b786c45a9ccfcd7f52ac9d58b96e275f"
}

```

برای دریافت آدرس کیف پول  و یا ساخت کیف پول جدید از این  api استفاده کنید. در این api با مشخص کردن مقادیر coin و network در کوپری پارام در صورت وجود کیف پول آدرس آن برگردانده میشود و در صورت عدم وجود کیف پول ساخته شده و آدرس کیف ساخته شده برگردانده می‌شود.

- آدرس : `https://api.raastin.com/api/v1/apiwithdraw`
- متد : `GET`
- نوع :‌ خصوصی

مقادیر مجاز  coin و network:

coin | network
-----|-----
USDT | BTC


## دریافت مقادیر آزاد هر کیف پول



```plane

GET https://api.raastin.com/api/v1/wallet/balance/ HTTP/1.1
Authorization: Token yourTOKENhereHEX0000000000

```


> درصورت فراخوانی صحیح پاسخ به این صورت خواهد بود:

```

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

- آدرس : `https://api.raastin.com/api/v1/wallet/balance/`
- متد : `GET`
- نوع :‌ خصوصی