In some situations, you want to create your own api. First install this package:
```bash
npm install -g json-server
```

Then create your own json file with object in it. For example here we made a file name `db.json` (Database):
```json
    "products":[
        {
            "id": 201,
            "title": "گوشی موبایل سامسونگ Galaxy S24 Ultra",
            "price": 67990000,
            "image": "https://dkstatics-public.digikala.com/products/201.jpg",
            "rating": 4.9,
            "category": "mobile",
            "description": "پرچمدار سامسونگ با پردازنده فوق‌العاده سریع و دوربین حرفه‌ای مناسب عکاسی و گیمینگ."
        },
        {
            "id": 202,
            "title": "گوشی موبایل شیائومی Redmi Note 13 Pro",
            "price": 15990000,
            "image": "https://dkstatics-public.digikala.com/products/202.jpg",
            "rating": 4.6,
            "category": "mobile",
            "description": "گوشی میان‌رده با صفحه نمایش روشن، باتری قوی و دوربین باکیفیت."
        },//...
```
*Note:* Put it in the main project folder where your current active terminal is on there.

And finally run this code:
```bash
json-server --watch db.json --port 3001
```

To stop it from running press `Ctrl + c`