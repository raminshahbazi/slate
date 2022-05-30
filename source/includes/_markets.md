# اطلاعات بازارهای راستین



```plane

GET https://api.raastin.com/api/v1/market/symbols/ HTTP/1.1

```



> درصورت فراخوانی صحیح پاسخ به این صورت خواهد بود:

```plane
{
    "name": "BTCUSDT",نام بازار
        "asset": "BTC",ارز معامله شده
        "base_asset": "USDT",ارز پایه
        "taker_fee": "0.002", کارمزد معامله ای که بر اساس ثبت سفارش جدید روی تابلوی معاملات انجام شود
        "maker_fee": "0",کارمزد معامله ای که بر اساس انتخاب از سفارشات روی تابلو انجام شود
        "tick_size": 2,
        "step_size": 5,
        "min_trade_quantity": "0.00001",مقدار کمینه مجاز برای معامله
        "max_trade_quantity": "9000",مقدار بیشینه ماز برای معامله
        "enable": false فعال بودن بازار
}

```

 برای دریافت اطلاعات مربوط به همه ی بازارهای راستین از این API استفاده کنید.

- آدرس : `https://api.raastin.com/api/v1/market/symbols`
- متد : `GET`
- نوع :‌ عمومی


در این api امکان فیلتر کردن بازار بر اساس name و asset symbol    و base_asset فراهم شده است. برای این منظور کافی است تا پارامترهای ذکر شده به عنوان کوئری پارام در url ارسال شود.

نمونه:

`http://api.raastin.com/api/v1/market/symbols/?base_asset=USDT&asset=BTC`


## اطلاعات یک بازار خاص

```plane

GET https://api.raastin.com/api/v1/market/symbols/symbol/ HTTP/1.1

```

 > درصورت فراخوانی صحیح پاسخ به این صورت خواهد بود:

 ```

{
    "name": "USDTIRT",
    "asset": "USDT",
    "base_asset": "IRT",
    "enable": true,
    "price": null,قیمت
    "change": null,تغییرات قیمت در ۲۴ ساعت
    "change_percent": null,تغییرات درصد قیمت در ۲۴ ساعت
    "high": null,بیشینه قیمت در ۲۴ ساعت
    "low": null,کمینه قیمت در ۲۴ ساعت
    "volume": null,حجم معاملات در ۲۴ ساعت
    "base_volume": null
}

 ```

 با قرار دادن نام بازار مورد نظر در آدرس زیر می توانید اطلاعات مربوط به تغییرات قیمت و حجم معاملات مربوط  به آن بازار را دریافت کنید.

- آدرس : `https://api.raastin.com/api/v1/market/symbols/symbol`
- متد : `GET`
- نوع :‌ عمومی



## لیست سفارش‌ها:اردر بوک



```plane

 GET https://api.raastin.com/api/v1/market/depth/symbol HTTP/1.1

```


> درصورت فراخوانی صحیح پاسخ به این صورت خواهد بود:

```plane

{
    "last_trade": {اخرین معامله
        "amount": "0.00049",حجم سفارش
        "price": "1104354177",قیمت سفارش
        "total": "541133" ارزش سفارش
    },
    "bids": [اردر های خرید
                {
            "price": "100000",
            "amount": "10.00000",
            "depth": "2",
            "total": "1000000"
        }
    ],
    "asks": [اردرهای فروش
        {
            "price": "1112952204",
            "amount": "0.01517",
            "depth": "33",
            "total": "16883484"
        },
}

```

برای دریافت لیست سفارش‌های هر بازار از این API استفاده کنید.

- آدرس : `https://api.raastin.com/api/v1/market/depth/symbol`
- متد : `GET`
- نوع :‌ عمومی

پارامتر:

نماد بازار مورد نظر را باید به جای کلمه symbol وارد کنید.



## لیست معاملات



```plane

 GET https://api.raastin.com/api/v1/market/trades/?symbol=SYMBOL HTTP/1.1

```


> درصورت فراخوانی صحیح پاسخ به این صورت خواهد بود:

```plane

{
    "count": 3978,
    "next": "https://api-staging.raastin.com/api/v1/market/trades/?limit=20&offset=20&symbol=BTCIRT",
    "previous": null,
    "results": [
        {
            "created": "2022-04-27T14:48:27.378360+04:30",
            "coin": "BTC",
            "pair": "IRT",
            "amount": "0.00064",
            "price": "1099759483",
            "pair_amount": "703846",
            "is_buyer_maker": true
        },
        {
            "created": "2022-04-27T14:47:17.375744+04:30",
            "coin": "BTC",
            "pair": "IRT",
            "amount": "0.00065",
            "price": "1113288328",
            "pair_amount": "723637",
            "is_buyer_maker": false
        },
}

```

برای دریافت لیست معاملات هر بازار  از این API استفاده کنید.

- آدرس : `https://api.raastin.com/api/v1/market/trades/?symbol=SYMBOL`
- متد : `GET`
- نوع :‌ عمومی

پارامترها:
