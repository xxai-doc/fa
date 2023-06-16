<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

# xxAI.art

بخشی از کد وب سایت منبع باز است، برای کمک به بهینه سازی ترجمه خوش آمدید.

## کد جلویی

* [کد جلویی](https://github.com/xxai-art/web)
* [بسته های زبان برای کل سایت](https://github.com/xxai-art/web/tree/main/i18n)
* [بسته های زبان برای ماژول های ورود به سیستم](https://github.com/wacpkg/user/tree/main/ui.i18n)
* [وب سایت اسناد چند زبانه](https://github.com/xxai-doc)

زبان برنامه نویسی front-end [@w5/coffee_plus](http://npmjs.com/@w5/coffee_plus) است که برخی از ویژگی ها را بر اساس نحو اسکریپت قهوه اضافه می کند، به [./coffee_plus.md](./coffee_plus.md) مراجعه کنید.

## بین المللی سازی وب سایت ها و اسناد

بر روی 3 پروژه زیر بسازید

### [@w5/mdt](https://www.npmjs.com/package/@w5/mdt)

الگوی علامت گذاری، با پسوند `.mdt` ، می تواند به فایل های خارجی با نحوی مشابه `<+ ./coffee_plus/import.js>` اشاره کند.

[@w5/trmd](https://www.npmjs.com/package/@w5/trmd)

ترجمه Markdown کدها و پیوندها را ترجمه نمی کند و جملات ترجمه شده را در حافظه پنهان نگه می دارد. اگر ترجمه اصلاح شود اما متن اصلی اصلاح نشده باشد، اجرای مجدد آن تغییر ترجمه را بازنویسی نمی کند.

[@w5/i18n](https://www.npmjs.com/package/@w5/i18n)

فایل های زبانی برای ترجمه وب سایت های تولید شده `yaml` .
