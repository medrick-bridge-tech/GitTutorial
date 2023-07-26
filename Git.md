# گیت (Git) چیست؟ 

گیت یک سیستم کنترل ورژن (VSC) متن باز است که در سال 2005 توسط لینوس تورالدز، خالق سیستم عامل لینوکس بوجود آمده است.

### سیستم کنترل ورژن VSC(Version Control System) چیست؟

سیستم کنترل ورژن (Version Control System) وظیفه مدیریت و ردیابی تغییرات در کدهای پروژه را برعهده دارد. سیستم‌های کنترل ورژن ابزارهایی هستند که به برنامه‌نویسان کمک می‌کنند تا تغییرات کدهای پروژه را در طول زمان دراختیار داشته باشند و هر زمان که نیاز داشتند، بتوانند کدهای نسخه‌های قبل را بازیابی کنند.

سیستم کنترل ورژن هر تغییری در کد را در نوع خاصی از پایگاه‌داده ثبت می‌کند. اگر اشتباهی در کدهای پروژه رخ دهد، برنامه‌نویسان می‌توانند به کدهای گذشته دسترسی داشته باشند و نسخه‌های قبلی کد را با‌هم مقایسه و باگ را رفع کنند.

### چرا از Git استفاده می کنیم ؟
* مخازن گیت را می‌توان به‌صورت خصوصی و درون‌تیمی یا به‌صورت عمومی برای همه ذخیره کرد.
* گیت از بسیاری از سیستم‌های کنترل ورژن (VCS) مشابه مانند CVS و SVN و Mercurial قوی‌تر است.
* امنیت گیت
    * گیت به کمک الگوریتم SHA1 محتوای فایل ها و روابط بین فایل ها و دایرکتوری ها را رمزنگاری می کند . این رمزگذاری باعث می‌شود تغییر نسخه‌های قبلی کد در مخزن گیت غیرممکن باشد و درصورت نیاز، گیت کدهای شما را بدون هیچ تغییری بازیابی می‌کند و دراختیارتان قرار می‌دهد. 
*  سازگاری با بسیاری از سیستم‌‌عامل‌ها مانند ویندوز و لینوکس و مک 

## آغاز کار با git

### مرحله اول : نصب Git

* linux : 
> sudo apt-get install git-all

* windows : 
*[دانلود](https://soft98.ir/software/programming/699-git-windows.html)*

### مرحله دوم : راه اندازی مخزن Git

ترمنیال خود را باز کنید و در محل پروژه خود دستور زیر را وارد کنید .
> git init

اجرای این دستور پوشه‌ای جدید به نام git. در دایرکتوری فعلی شما ایجاد می‌کند .

### مرحله سوم : ذخیره تغییرات در مخزن Git

من برای مثال، یک فایل html می سازم و کدهای زیر را درون آن می نویسم.

```
<!DOCTYPE html>
<html>
<body>
    <h1>Hello World</h1>
</body>
</html>
```
* با دستور status می توانید تغییرات ایجاد شده در پروژه را مشاهده کنید .
> git status

```
On branch master
Your branch is up to date with 'origin/master'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        index.html
```

* 
    *  خط 1 : به معنای این است که محل کار ما در branch master است. با branch در جلوتر آشنا می شوید.
    * خط 4 : گیت به ما می گوید که یک فایل جدید به مخزن اضافه شده و نیاز است که آنرا به مخزن اضافه کنید .
    * خط 5 : از این دستور برای اضافه کردن فایل به مخزن استفاده می کنیم 
    * خط 6 : نام فایل

* آماده‌سازی فایل‌ها برای ثبت تغییرات:
    * دستور git add فایل‌های فعلی را به ناحیه نسخه‌بندی (Staging) اضافه می‌کند (قبل از ثبت تغییرات با Commit). هربار که فایلی را در پروژه خود اضافه یا به‌روز می‌کنید، برای ثبت تغییرات، باید به‌روز‌رسانی‌ها را به قسمت Staging ارسال کنید. 
    > git add filename                        //just add one file
    
    * or
    > git add -A                              //add all files

    * پس از اجرای این دستور، فایل هایی که دچار تغییر شده اند stage می شوند. دستور status را وارد می کنم تا تغییرات را ببینیم :
```
On branch master
Your branch is up to date with 'origin/master'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   index.html
```
* ثبت تغییرات فایل در مخزن:
    * با دستور commit پس از stage کردن فایل ها، تغییرات آنها ثبت می شود.
    * commit کردن به معنای اضافه کردن یه توضیح در مورد تغییرات ایجاد شده در پروژه است.
    > git commit -m explaination

    * پس حال باید فایل هایی که stage شده اند را commit کنیم .
    > git commit -m "Initialized project"

```
[master bbd47f9] Initialized project
2 files changed, 28 insertions(+)

    create mode 100644 index.html
```

*وووو تبریک! شما اولین پروژه Git خود را ایجاد کردید.*

حال با استفاده از دستور log می توانید تاریخچه commit های خود را بررسی کنید .
> git log

```
commit bbd47f98afc91c8dc82fae79dc79e29097061979 (HEAD -> master)
Author: Amir Yazdan <begal.cmay@gmail.com>
Date:   Thu Jul 27 00:44:24 2023 +0330

    Initialized project

commit bef00d37b3bdceed076d113a432e85230436c279 (origin/master)
Author: Amir Yazdan <begal.cmay@gmail.com>
Date:   Thu Jul 27 00:26:21 2023 +0330

    Edit tutorial

    Add some spaces and change in texts to become right to left

commit 0fc16a62b8e2cd119cbd643518a9e7f1c4694e42
Author: Amir Yazdan <begal.cmay@gmail.com>
Date:   Thu Jul 27 00:19:37 2023 +0330

    Write tutorial

    Write step 3 and log command

commit e2fc65b42a0d49a2a7da1ec841dfac61ca10c78c
Author: Amir Yazdan <begal.cmay@gmail.com>
Date:   Wed Jul 26 20:48:25 2023 +0330

    Revert "Write tutorial"

    This reverts commit 52c76779a06049aa56c88b665893abb94b43bee6.

commit 52c76779a06049aa56c88b665893abb94b43bee6
Author: Amir Yazdan <begal.cmay@gmail.com>
Date:   Wed Jul 26 20:43:52 2023 +0330

    Write tutorial

    Write until step 2

```
*پایان*