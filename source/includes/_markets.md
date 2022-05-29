# اطلاعات بازارهای راستین



```plane
/api/v1/market/symbols/

```


> درصورت فراخوانی صحیح پاسخ به این صورت خواهد بود:

```plane

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

با قرار دادن نام بازار مورد نظر در آدرس زیر می توانید اطلاعات مربوط به تغییرات قیمت و حجم معاملات مربوط  به آن بازار را دریافت کنید.

 /api/v1/market/symbols/symbol

در صورت فراخوانی صحیح پاسخ به این صورت خواهد بود:

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

 برای دریافت اطلاعات مربوط به همه ی بازارهای راستین از این API استفاده کنید.

متد:
Get
نوع: عمومی

محدودیت فراخوانی:


در این api امکان فیلتر کردن بازار بر اساس name و asset symbol    و base_asset فراهم شده است. برای این منظور کافی است تا پارامترهای ذکر شده به عنوان کوئری پارام در url ارسال شود.

نمونه:
http://127.0.0.1:8000/api/v1/market/symbols/?base_asset=USDT&asset=BTC



## لیست سفارش‌ها:اردر بوک

برای دریافت لیست سفارش‌های هر بازار از این API استفاده کنید.

## لیست معاملات



```plane
 /api/v1/market/trades/?symbol=SYMBOL

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


```

برای دریافت لیست معاملات هر بازار  از این API استفاده کنید.

آدرس:


متد:
Get
نوع:

عمومی

پارامترها:
محدودیت فراخوانی:
