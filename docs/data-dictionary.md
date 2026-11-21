# فرهنگ متغیرها و قواعد داده

| نام | نوع پیشنهادی | اجباری | قاعده |
|---|---|---:|---|
| request_no | Text | بله | شناسه یکتا؛ تا زمان راه‌اندازی شماره‌ساز، دستی |
| requester_name | Text | بله | نام و نام خانوادگی |
| requester_mobile | Text | بله | 11 رقم و شروع با 09 |
| item_name | Text | بله | نام کالا |
| item_description | Text | خیر | توضیحات تکمیلی |
| quantity | Number | بله | عدد صحیح بزرگ‌تر از صفر |
| unit_price | Number | بله | تومان، صفر یا بیشتر |
| total_amount | Number | بله | quantity × unit_price؛ فقط خواندنی |
| request_status | Text | بله | submitted / pending_manager / approved / rejected / paid |
| manager_decision | Text | در مرحله مدیر | approved / rejected |
| manager_notes | Text | مشروط | هنگام رد اجباری |
| manager_decision_date | Date | در مرحله مدیر | تاریخ تصمیم |
| payment_amount | Number | بله | باید با مبلغ قابل پرداخت برابر باشد |
| payment_method | Text | بله | card_to_card / bank_transfer / cash / other |
| payment_tracking_no | Text | مشروط | حواله بانکی اجباری |
| payment_date | Date | بله | تاریخ ثبت پرداخت |
| payment_notes | Text | خیر | توضیح تکمیلی |

## قواعد کنترلی ضروری
1. مبلغ کل را در فرم فقط خواندنی کنید، اما در زمان ثبت سمت سرور دوباره محاسبه کنید.
2. برای جلوگیری از دور زدن تأیید مدیر، شرط مبلغ را فقط در رابط کاربری قرار ندهید؛ Gateway فرایند باید آن را کنترل کند.
3. در رد درخواست، توضیح مدیر را اجباری کنید.
4. در حواله بانکی، شماره پیگیری را اجباری کنید.
5. تاریخ و مبلغ پرداخت باید ثبت شوند؛ وضعیت paid فقط پس از تکمیل فرم پرداخت تنظیم شود.
6. مبلغ‌ها در تمام فرم‌ها و گزارش‌ها با واحد تومان نمایش داده شوند.
