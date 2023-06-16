<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

توصیه می شود ابتدا nodejs, [direnv](https://direnv.net) , [bun](https://github.com/oven-sh/bun) و سپس `direnv allow` پس از ورود به دایرکتوری نصب کنید ( [.envrc](https://github.com/xxai-art/doc/blob/main/.envrc) پس از وارد شدن به دایرکتوری به طور خودکار اجرا می شود).

معنی این است: ترجمه چینی به ژاپنی، کره ای، انگلیسی، ترجمه انگلیسی به تمام زبان های دیگر. اگر فقط می خواهید از زبان چینی و انگلیسی پشتیبانی کنید، می توانید فقط `zh: en` بنویسید.

معنی این است: ترجمه چینی به ژاپنی، کره ای، انگلیسی، ترجمه انگلیسی به تمام زبان های دیگر. اگر فقط می خواهید از زبان چینی و انگلیسی پشتیبانی کنید، می توانید فقط `zh: en` بنویسید.

* [کد جلویی](https://github.com/xxai-art/web)
* [بسته های زبان برای کل سایت](https://github.com/xxai-art/web/tree/main/i18n)
* [بسته های زبان برای ماژول های ورود](https://github.com/wacpkg/user/tree/main/ui.i18n)
* [وب سایت اسناد چند زبانه](https://github.com/xxai-doc)

زبان برنامه نویسی front-end [@w5/coffee_plus](http://npmjs.com/@w5/coffee_plus) است که برخی از ویژگی ها را بر اساس نحو اسکریپت قهوه اضافه می کند، به [./coffee_plus.md](./coffee_plus.md) مراجعه کنید.

## بین المللی سازی وب سایت ها و اسناد

بر روی 3 پروژه زیر بسازید

* [@w5/mdt](https://www.npmjs.com/package/@w5/mdt)

  پسوند `.mdt` است، شما می توانید از نحوی مشابه `<+ ./coffee_plus/import.js>` برای ارجاع به فایل های خارجی استفاده کنید و با پسوند `.md` علامت گذاری ایجاد کنید.

* [@w5/trmd](https://www.npmjs.com/package/@w5/trmd)

  ترجمه Markdown کدها و پیوندها را ترجمه نمی کند و جملات ترجمه شده را در حافظه پنهان نگه می دارد. اگر ترجمه اصلاح شود اما متن اصلی اصلاح نشده باشد، اجرای مجدد آن تغییر ترجمه را بازنویسی نمی کند.

* [@w5/i18n](https://www.npmjs.com/package/@w5/i18n)

  فایل های زبانی برای ترجمه وب سایت های تولید شده `yaml` .

### دستورالعمل های اتوماسیون ترجمه اسناد

به مخزن کد [xxai-art/doc](https://github.com/xxai-art/doc) مراجعه کنید

توصیه می شود ابتدا nodejs, [direnv](https://direnv.net) , [bun](https://github.com/oven-sh/bun) و سپس `direnv allow` پس از ورود به دایرکتوری نصب کنید ( [.envrc](https://github.com/xxai-art/doc/blob/main/.envrc) پس از وارد شدن به دایرکتوری به طور خودکار اجرا می شود).

برای جلوگیری از ترجمه کد بزرگ به صدها زبان، یک پایه کد جداگانه برای هر زبان ایجاد کردم و سازمانی برای ذخیره پایه کد ایجاد کردم.

با تنظیم متغیر محیطی `GITHUB_ACCESS_TOKEN` و سپس اجرای [create.github.coffee](https://github.com/xxai-art/doc/blob/main/create.github.coffee) به طور خودکار مخزن کد ایجاد می شود.

البته می توانید آن را در یک پایه کد نیز قرار دهید.

مرجع اسکریپت ترجمه [run.sh](https://github.com/xxai-art/doc/blob/main/run.sh)

کد اسکریپت به صورت زیر تفسیر می شود:

[bux](https://bun.sh/docs/cli/bunx) جایگزینی برای npx است که سریعتر است. البته، اگر bun را نصب نکرده اید، می توانید به جای آن `npx` استفاده کنید.

`bunx mdt zh` `.mdt` در دایرکتوری zh به صورت `.md` رندر می کند، 2 فایل مرتبط زیر را ببینید

* [coffee_plus.mdt](https://github.com/xxai-doc/zh/blob/main/coffee_plus.mdt)
* [coffee_plus.md](https://github.com/xxai-doc/zh/blob/main/coffee_plus.md)

`bunx i18n` کد اصلی برای ترجمه است (اگر فقط `nodejs` نصب کرده اید، اما `bun` و `direnv` نصب نشده اند، می توانید `npx i18n` نیز برای ترجمه اجرا کنید).

[i18n.yml را](https://github.com/xxai-art/doc/blob/main/i18n.yml) تجزیه می کند، پیکربندی `i18n.yml` در این سند به شرح زیر است:

```
en:
zh: ja ko en
```

معنی این است: ترجمه چینی به ژاپنی، کره ای، انگلیسی، ترجمه انگلیسی به تمام زبان های دیگر. اگر فقط می خواهید از زبان چینی و انگلیسی پشتیبانی کنید، می توانید فقط `zh: en` بنویسید.

آخرین مورد [gen.README.coffee](https://github.com/xxai-art/doc/blob/main/gen.README.coffee) است که محتوای بین عنوان اصلی و اولین زیرنویس `README.md` هر زبان را استخراج می کند تا ورودی `README.md` ایجاد کند. کد بسیار ساده است، می توانید خودتان آن را ببینید.

Google API برای ترجمه رایگان استفاده می شود. اگر نمی توانید به Google دسترسی داشته باشید، لطفاً یک پروکسی را پیکربندی و تنظیم کنید، مانند:

```
export https_proxy=http://127.0.0.1:7890 http_proxy=http://127.0.0.1:7890 all_proxy=socks5://127.0.0.1:7890
```

اسکریپت ترجمه یک حافظه پنهان ترجمه شده در فهرست `.i18n` ایجاد می کند، لطفاً آن را با `git status` بررسی کنید و آن را به مخزن کد اضافه کنید تا از ترجمه های مکرر جلوگیری کنید.

لطفاً هر بار که ترجمه را برای به‌روزرسانی حافظه پنهان تغییر می‌دهید، `bunx i18n` را اجرا کنید.

اگر متن اصلی و ترجمه به طور همزمان اصلاح شوند، حافظه پنهان اشتباه می شود، بنابراین اگر می خواهید تغییر دهید، فقط می توانید یکی را تغییر دهید و سپس `bunx i18n` برای به روز رسانی کش اجرا کنید.
