# WhiteDNS GitHub Mirror

این Repo لینک زیر را Mirror می‌کند:

`https://sub.whitedns.shop/sub/base64.txt`

فایل `base64.txt` داخل این پکیج یک Snapshot فعلی از ساب است.  
GitHub Actions نیز هر 15 دقیقه منبع اصلی را بررسی می‌کند و فقط در صورت تغییر، فایل را Commit می‌کند.

## نصب خیلی سریع

1. در GitHub یک Repository جدید بساز؛ پیشنهاد: `sub-mirror`
2. بهتر است Repository را **Public** بگذاری.
3. همه محتویات این ZIP را دقیقاً در ریشه Repo آپلود کن.
   دقت کن پوشه مخفی `.github/workflows/` هم باید آپلود شود.
4. وارد:
   `Settings → Actions → General`
   شو و در صورت نیاز در بخش **Workflow permissions** اجازه Read/Write را فعال کن.
5. به تب **Actions** برو.
6. Workflow با نام **Update WhiteDNS Subscription** را باز کن.
7. روی **Run workflow** بزن تا اولین اجرای دستی انجام شود.
8. بعد از سبز شدن Workflow، Mirror آماده است.

## لینک مورد استفاده در ZMOB

اگر Username شما `YOUR_USERNAME` و اسم Repo برابر `sub-mirror` باشد:

### GitHub Raw
`https://raw.githubusercontent.com/YOUR_USERNAME/sub-mirror/main/base64.txt`

### jsDelivr (دامنه جایگزین)
`https://cdn.jsdelivr.net/gh/YOUR_USERNAME/sub-mirror@main/base64.txt`

در ZMOB یکی از این دو لینک را به عنوان Subscription URL قرار بده.

## اگر Branch شما main نیست

در لینک Raw کلمه `main` را با اسم Branch اصلی خودت عوض کن.

مثال برای `master`:

`https://raw.githubusercontent.com/YOUR_USERNAME/sub-mirror/master/base64.txt`

## نکات

- Workflow هر 15 دقیقه اجرا می‌شود.
- اگر منبع اصلی موقتاً قطع یا فیلتر باشد، فایل سالم قبلی پاک نمی‌شود.
- اگر محتوای Subscription تغییر نکرده باشد، Commit جدید ساخته نمی‌شود.
- می‌توانی هر زمان از تب Actions با `Run workflow` فوراً Update دستی بگیری.
- Token یا Password خاصی لازم نیست؛ Workflow از `GITHUB_TOKEN` خود همان Repo استفاده می‌کند.
