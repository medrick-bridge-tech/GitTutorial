<div dir="rtl">

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

* توضیحات :
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
Author: Amir Yazdan <begal.cmay@gmail.com>
Date:   Thu Jul 27 00:57:09 2023 +0330

    Edit tutorial

    Terminal results now have better writing and style

commit de59f4db9e6597036fbee54a3b6eeeea69f6550f
Author: Amir Yazdan <begal.cmay@gmail.com>
Date:   Thu Jul 27 00:53:43 2023 +0330

    Edit tutorial

    HTML codes now are readable

commit ce2f44617b522ece09a4fedec66b9c684301f4e9
Author: Amir Yazdan <begal.cmay@gmail.com>
Date:   Thu Jul 27 00:48:44 2023 +0330

    Write tutorial

    Create example

commit bbd47f98afc91c8dc82fae79dc79e29097061979
Author: Amir Yazdan <begal.cmay@gmail.com>
Date:   Thu Jul 27 00:44:24 2023 +0330

    Initialized project

```

## شاخه (branch) در گیت چیست و چه کاربردی دارد؟

هر پروژه ای که با گیت ایجاد می شود، یک شاخه(branch) اصلی به نام master دارد. branch فضایی است که گیت آن را تحت بررسی دارد و تغییرات آنرا ثبت می کند. معمولا در تیم های  نرم افزاری، شاخه‌های فرعی دیگری ساخته و در آن‌ها اقدام به توسعه فیچرهای جدید نموده سپس آن‌ها را با شاخه master ادغام می کنند.

برای درک بهتر این موضوع، فرض کنیم توسعه دهنده ای به نام امیر قرار است قابلیت فرم ثبت نام را به پروژه بیفزاید و توسعه دهنده دیگری به نام علی قرار است تا رابط کاربری را تکمیل کند؛ در چنین شرایطی، می‌توان دو شاخه فرعی تحت عنواین دلخواهی همچون amir-branch-signup و ali-branch-ui ایجاد کرده و هر کدام از ایشان با سهولت هرچه تمام‌تر شروع به کدنویسی کرده و چنانچه در نهایت کدهای نوشته‌ شده مورد تأیید مدیر فنی بود،‌ با شاخه اصلی (master) ادغام خواهند شد.

به عنوان مثال، آقای x در تیم می خواهد صفحه ثبت نامی به پروژه اضافه کند. اما نمی خواهد تا قبل از اینکه تایید مدیر پروژه را بگیرد تغییرات را مستقیم روی پروژه ایجاد کند.
پس او یک branch به اسم signup به پروژه اضافه می کند.

> git branch signup

با نوشتن این دستور، شاخه ای به اسم signup ایجاد می شود. برای دیدن لیست کل اسامی شاخه های پروژه گیت می توانید دستور زیر را وارد کنید.

> git branch

```
* master
  signup
```

علامت '*' به معنی این است که شما همچنان در شاخه master هستید. در این حال هر تغییراتی که در پروژه ایجاد کنید در شاخه master اعمال می شود.
برای انتقال به شاخه signup، دستور زیر را وارد کنید.

> git checkout signup

```
Switched to branch 'signup'
```

این پیغام به این معنی است که با موفقیت به شاخه signup منتقل شدید. اگر دوباره دستور ``` git branch ``` را وارد کنید می بینید که اکنون در شاخه signup قرار دارید.

> git branch

```
* signup
```

ساخت یک شاخه جدید، مانند ساخت یک فولدر جدید می ماند. هر تغییری که در این پوشه ایجاد کنید، مانند اضافه کردن فایل های جدید یا تغییر در دیگر فایل، تنها در این شاخه بوجود می آید و با swicth کردن به شاخه دیگر، تغییرات ایجاد شده ناپدید می شوند و تنها commit هایی که در آن شاخه ثبت شده اند در فولدر نمایش داده می شوند.

آقای x شروع به ساخت فایل signup.html در شاخه signup می کند.

```
<!DOCTYPE html>
<html>
<head>
    <title>ثبت نام</title>
</head>
<body>
    <form>
        <fieldset>
            <legend>ثبت نام</legend>
            <div>
                <label>نام : </label>
                <input type="text">
            </div>
            <div>
                <label>نام خانوادگی: </label>
                <input type="text">
            </div>
            <div>
                <label>پست الکترونیک: </label>
                <input type="email">
            </div>
            <div>
                <label>تولد: </label>
                <input type="date">
            </div>
            <div>
                <label>شماره تلفن: </label>
                <input type="number">
            </div>
            <div>
                <label>رمز عبور: </label>
                <input type="password">
            </div>
            <div>
                <input type="submit" value="ثبت"/>
            </div>
        </fieldset>
    </form>
</body>
</html>
```

پس از پایان نوشتن کد، اگر status شاخه را بررسی کنیم، می بینیم که تغییرات ایجاد شده در شاخه signup را نمایش می دهد.

> git status

```
On branch signup
Changes not staged for commit:
  
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        signup.html

no changes added to commit (use "git add" and/or "git commit -a")
```

فایل جدید را add و commit می کنیم.
> git add -A

> git commit -m "Create sign up form"

```
[signup 5adfc99] Create sign up form
 2 files changed, 154 insertions(+), 18 deletions(-)
 create mode 100644 signup.html
```

حال در شاخه signup ما صفحه ثبت نام خودمون رو بوجود آوردیم، اما با انتقال به شاخه master، فایل signup.html ناگهان ناپدید می شود. این بدلیل آن است که تغییرات ایجاد شده در شاخه signup اعمال و ذخیره شده و تنها در این شاخه اعتبار و موجودیت دارد. برای اعمال تغییرات ایجاد شده در شاخه master، باید آنرا با شاخه signup ادغام یا به عبارتی merge کنید.

## چگونه دو شاخه با یکدیگر ادغام (merge) می شوند؟

برای ادغام دو شاخه، از دستور merge استفاده می کنیم.
> git merge branch-name

در مثال خودمون ابتدا به شاخه اصلی می رویم و سپس دستور merge را به گونه زیر تایپ می کنیم : 
> git checkout master

> git merge signup

```
Updating 472efeb..e2a4cad
Fast-forward
 signup.html | 40 ++++++++++++++++++++++++++++++++++++++++
 1 file changed, 40 insertions(+)
 create mode 100644 signup.html
```

دو شاخه با موفقیت با یکدیگر ادغام شدند . حال خانم y وظیفه دارد یک عکس و یک لینک به صفحه ثبت نام به پروژه اضافه کند. پس یک شاخه به اسم addneeds اضافه می کند:

> git branch addneeds

> git checkout addneeds

کد index.html رو تغییر می دهد: 

```
<!DOCTYPE html>
<html>
<body>
    <a href="signup.html"><img src='index.png' alt="sign up"></a>
    <h1>Hello World</h1>
</body>
</html>
```
[دانلود_عکس](https://cdn-icons-png.flaticon.com/512/5455/5455873.png)

سپس commit و add می کند:

> git add -A

> git commit -m "git commit -m "Add an image and a link on  main page to go to the sign up page"

```
[addneeds 7be4316] Add an image and a link on  main page to go to the sign up page
 2 files changed, 1 insertion(+)
 create mode 100644 index.png
```

پس از گرفتن تاییدیه از مدیر پروژه، مسیر ادغام را طی می کند:

> git checkout master

> git merge addneeds

```
Updating e2a4cad..7be4316
Fast-forward
 index.html |   1 +
 index.png  | Bin 0 -> 4992 bytes
 2 files changed, 1 insertion(+)
 create mode 100644 index.png
```

با موفقیت ادغام شد ;) !!!!

# وصل کردن دیسکورد به گیت هاب با Webhook #

گاهی ممکن است تیم تصمیم بگیرد که تمامی کامیت ها و تغییراتی که اعضا در مخزن گیت هاب انجام می دهد را در سرور دیسکورد نمایش بدهد. در این قسمت یاد می گیرید چطور دیسکورد خود را به گیت هاب وصل کنید و اعلانات دلخواه را دریافت کنید.

### مراحل کار : ###
<div dir=”rtl”>

<ul>
    <li>ابتدا وارد دیسکورد شوید. یک سرور جدید برای خودتان ایجاد کنید یا وارد سرور تیم شوید. حالا بر روی Edit Channel کلیک کنید و وارد Integrations شوید. سپس بر روی Create Webhook کلیک کنید تا Webhook شما ساخته شود. در نهایت URL وب هوک را کپی کنید و وارد گیت هاب شوید.</li>
    <li>مخزن مورد نظرتان را باز کنید و وارد Settings شوید. در منوی سمت چپ، Webhooks را پیدا کنید . بر روی دکمه Add webhook کلیک کنید.</li>
    <li>در قسمت Payload URL، لینک وب هوک دیسکورد خود را وارد و در انتهای آن عبارت **/github** را اضافه کنید.</li>
    <li>Content type رو برابر **application/json** قرار دهید.</li>
    <li>در آخر بر روی دکمه Add webhook کلیک کنید. حال اگر عملیات push را انجام دهید، اعلانی مبنی بر push کردن در discord دریافت خواهید کرد که حاوی commit های اعمال شده در آن خواهد بود. </li>
</ul>
<div>
*پایان*

</div>