下载 O'reilly 电子书

非鱼知乐
IP属地: 广西
2024.05.11 23:46:16
字数 359
阅读 133
https://xingyys.tech/%E4%B8%8B%E8%BD%BDoreilly%E7%94%B5%E5%AD%90%E4%B9%A6/

1. 安装
首先下载 safaribooks 工具。

$ git clone https://github.com/lorenzodifuccia/safaribooks.git
Cloning into 'safaribooks'...

$ cd safaribooks/
$ pip3 install -r requirements.txt
OR

$ pipenv install && pipenv shell
2. 使用
帐号密码下载
独立（非关联） O'Reilly 帐号适用

python3 safaribooks.py --cred "account_mail@mail.com:password01" XXXXXXXXXXXXX
其中 XXXXXXXXXXXXX 表示电子书的 ID。例如电子书页面 https://learning.oreilly.com/videos/python-fundamentals/9780135917411/ 的 ID 就是 9780135917411。

使用本地 cookies.json 文件下载
O’Reilly 账号为公司关联账号适用

下载
先在浏览器中登录 O’Reilly 页面，转到这个首页 https://learning.oreilly.com/profile/。

打开浏览器的开发者模式。Chrome 下点击右上三点，选择More tools -> Developer tools，选择Console栏。

在 Console 下执行命令:

javascript:(function(){var output = {};document.cookie.split(/\s*;\s*/).forEach(function(pair) {pair = pair.split(/\s*=\s*/);output[pair[0]]=pair.splice(1).join('=');});console.log(JSON.stringify(output));})();
将输出的信息保存到 safaribooks 目录下的 cookies.json 文件中。

执行以下命令下载电子书：

python3 safaribooks.py  XXXXXXXXXXXXX
输出结果为:

                                                                                
 ██████╗     ██████╗ ██╗  ██╗   ██╗██████╗
██╔═══██╗    ██╔══██╗██║  ╚██╗ ██╔╝╚════██╗
██║   ██║    ██████╔╝██║   ╚████╔╝   ▄███╔╝
██║   ██║    ██╔══██╗██║    ╚██╔╝    ▀▀══╝
╚██████╔╝    ██║  ██║███████╗██║     ██╗
 ╚═════╝     ╚═╝  ╚═╝╚══════╝╚═╝     ╚═╝

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
[-] Successfully authenticated.                                                 
[*] Retrieving book info...                                                     
[-] Title: A Tour of C++, 3rd Edition                                           
[-] Authors: Bjarne Stroustrup                                                  
[-] Identifier: 9780136823575                                                   
[-] ISBN: 9780136823575                                                         
[-] Publishers: Addison-Wesley Professional                                     
[-] Rights:                                                                     
[-] Description: In A Tour of C++, Third Edition, Bjarne Stroustrup provides an overview of ISO C++, C++20, that aims to give experienced programmers a clear understanding of what constitutes modern C++. Featuring carefully crafted examples and practical help in getting started, this revised and updated edition concisely covers most major language features and the major standard-library components needed for effective use.Stroustrup presents C++ features in the context of the programming styles they support, suc...
[-] Release Date: 2022-09-30                                                    
[-] URL: https://learning.oreilly.com/library/view/a-tour-of/9780136823575/     
[*] Retrieving book chapters...                                                 
[*] Output directory:                                                           
    /home/liji/git/safaribooks/Books/A Tour of C__ 3rd Edition (9780136823575)
[-] Downloading book contents... (48 chapters)                                  
    [#####################################################################] 100%
[-] Downloading book CSSs... (1 files)                                          
    [#####################################################################] 100%
[-] Downloading book images... (596 files)                                      
    [#####################################################################] 100%
[-] Creating EPUB file...                                                       
[*] Done: /home/liji/git/safaribooks/Books/A Tour of C__ 3rd Edition (9780136823575)/9780136823575.epub

    If you like it, please * this project on GitHub to make it known:
        https://github.com/lorenzodifuccia/safaribooks
    e don't forget to renew your Safari Books Online subscription:
        https://learning.oreilly.com

[!] Bye!!
3. 格式转化
下载的电子书为 epub 格式，如果需要其他格式时，可以借用 calibre 工具来转化。

4. 著名出版商 O’Reilly 推出免费计算机类电子书
https://bookfere.com/post/453.html



# SafariBooks
Download and generate *EPUB* of your favorite books from [*Safari Books Online*](https://www.safaribooksonline.com) library.  
I'm not responsible for the use of this program, this is only for *personal* and *educational* purpose.  
Before any usage please read the *O'Reilly*'s [Terms of Service](https://learning.oreilly.com/terms/).  

<a href='https://ko-fi.com/lorenz0x00' target='_blank'><img height='35' style='border:0px;height:46px;' src='https://az743702.vo.msecnd.net/cdn/kofi3.png?v=0' border='0' alt='Buy Me a Coffee at ko-fi.com' />

> ## ⚠ *Attention needed* ⚠ 
> *If you are a developer and want to help this project, please take a look to the current [Milestone](https://github.com/lorenzodifuccia/safaribooks/milestone/1)*.  
> *Checkout also the new APIv2 branch: [apiv2](https://github.com/lorenzodifuccia/safaribooks/tree/apiv2)*  
> *The Community thanks 🙏🏻*

> ## ✨ ADV ✨
> *Take a look at my other GitHub projects: https://github.com/lorenzodifuccia* 👀 ❤️

## Overview:
  * [Requirements & Setup](#requirements--setup)
  * [Usage](#usage)
  * [Single Sign-On (SSO), Company, University Login](https://github.com/lorenzodifuccia/safaribooks/issues/150#issuecomment-555423085)
  * [Calibre EPUB conversion](https://github.com/lorenzodifuccia/safaribooks#calibre-epub-conversion)
  * [Example: Download *Test-Driven Development with Python, 2nd Edition*](#download-test-driven-development-with-python-2nd-edition)
  * [Example: Use or not the `--kindle` option](#use-or-not-the---kindle-option)

## Requirements & Setup:
First of all, it requires `python3` and `pip3` or `pipenv` to be installed.  
```shell
$ git clone https://github.com/lorenzodifuccia/safaribooks.git
Cloning into 'safaribooks'...

$ cd safaribooks/
$ pip3 install -r requirements.txt

OR

$ pipenv install && pipenv shell
```  

The program depends of only two **Python _3_** modules:
```python3
lxml>=4.1.1
requests>=2.20.0
```
  
## Usage:
It's really simple to use, just choose a book from the library and replace in the following command:
  * X-es with its ID, 
  * `email:password` with your own. 

```shell
$ python3 safaribooks.py --cred "account_mail@mail.com:password01" XXXXXXXXXXXXX
```

The ID is the digits that you find in the URL of the book description page:  
`https://www.safaribooksonline.com/library/view/book-name/XXXXXXXXXXXXX/`  
Like: `https://www.safaribooksonline.com/library/view/test-driven-development-with/9781491958698/`  
  
#### Program options:
```shell
$ python3 safaribooks.py --help
usage: safaribooks.py [--cred <EMAIL:PASS> | --login] [--no-cookies]
                      [--kindle] [--preserve-log] [--help]
                      <BOOK ID>

Download and generate an EPUB of your favorite books from Safari Books Online.

positional arguments:
  <BOOK ID>            Book digits ID that you want to download. You can find
                       it in the URL (X-es):
                       `https://learning.oreilly.com/library/view/book-
                       name/XXXXXXXXXXXXX/`

optional arguments:
  --cred <EMAIL:PASS>  Credentials used to perform the auth login on Safari
                       Books Online. Es. ` --cred
                       "account_mail@mail.com:password01" `.
  --login              Prompt for credentials used to perform the auth login
                       on Safari Books Online.
  --no-cookies         Prevent your session data to be saved into
                       `cookies.json` file.
  --kindle             Add some CSS rules that block overflow on `table` and
                       `pre` elements. Use this option if you're going to
                       export the EPUB to E-Readers like Amazon Kindle.
  --preserve-log       Leave the `info_XXXXXXXXXXXXX.log` file even if there
                       isn't any error.
  --help               Show this help message.
```
  
The first time you use the program, you'll have to specify your Safari Books Online account credentials (look [`here`](/../../issues/15) for special character).  
The next times you'll download a book, before session expires, you can omit the credential, because the program save your session cookies in a file called `cookies.json`.  
For **SSO**, please use the `sso_cookies.py` program in order to create the `cookies.json` file from the SSO cookies retrieved by your browser session (please follow [`these steps`](/../../issues/150#issuecomment-555423085)).  
  
Pay attention if you use a shared PC, because everyone that has access to your files can steal your session. 
If you don't want to cache the cookies, just use the `--no-cookies` option and provide all time your credential through the `--cred` option or the more safe `--login` one: this will prompt you for credential during the script execution.

You can configure proxies by setting on your system the environment variable `HTTPS_PROXY` or using the `USE_PROXY` directive into the script.

#### Calibre EPUB conversion
**Important**: since the script only download HTML pages and create a raw EPUB, many of the CSS and XML/HTML directives are wrong for an E-Reader. To ensure best quality of the output, I suggest you to always convert the `EPUB` obtained by the script to standard-`EPUB` with [Calibre](https://calibre-ebook.com/).
You can also use the command-line version of Calibre with `ebook-convert`, e.g.:
```bash
$ ebook-convert "XXXX/safaribooks/Books/Test-Driven Development with Python 2nd Edition (9781491958698)/9781491958698.epub" "XXXX/safaribooks/Books/Test-Driven Development with Python 2nd Edition (9781491958698)/9781491958698_CLEAR.epub"
```
After the execution, you can read the `9781491958698_CLEAR.epub` in every E-Reader and delete all other files.

The program offers also an option to ensure best compatibilities for who wants to export the `EPUB` to E-Readers like Amazon Kindle: `--kindle`, it blocks overflow on `table` and `pre` elements (see [example](#use-or-not-the---kindle-option)).  
In this case, I suggest you to convert the `EPUB` to `AZW3` with Calibre or to `MOBI`, remember in this case to select `Ignore margins` in the conversion options:  
  
![Calibre IgnoreMargins](https://github.com/lorenzodifuccia/cloudflare/raw/master/Images/safaribooks/safaribooks_calibre_IgnoreMargins.png "Select Ignore margins")  
  
## Examples:
  * ## Download [Test-Driven Development with Python, 2nd Edition](https://www.safaribooksonline.com/library/view/test-driven-development-with/9781491958698/):  
    ```shell
    $ python3 safaribooks.py --cred "my_email@gmail.com:MyPassword1!" 9781491958698

           ____     ___         _ 
          / __/__ _/ _/__ _____(_)
         _\ \/ _ `/ _/ _ `/ __/ / 
        /___/\_,_/_/ \_,_/_/ /_/  
          / _ )___  ___  / /__ ___
         / _  / _ \/ _ \/  '_/(_-<
        /____/\___/\___/_/\_\/___/

    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    [-] Logging into Safari Books Online...
    [*] Retrieving book info... 
    [-] Title: Test-Driven Development with Python, 2nd Edition                     
    [-] Authors: Harry J.W. Percival                                                
    [-] Identifier: 9781491958698                                                   
    [-] ISBN: 9781491958704                                                         
    [-] Publishers: O'Reilly Media, Inc.                                            
    [-] Rights: Copyright © O'Reilly Media, Inc.                                    
    [-] Description: By taking you through the development of a real web application 
    from beginning to end, the second edition of this hands-on guide demonstrates the 
    practical advantages of test-driven development (TDD) with Python. You’ll learn 
    how to write and run tests before building each part of your app, and then develop
    the minimum amount of code required to pass those tests. The result? Clean code
    that works.In the process, you’ll learn the basics of Django, Selenium, Git, 
    jQuery, and Mock, along with curre...
    [-] Release Date: 2017-08-18
    [-] URL: https://learning.oreilly.com/library/view/test-driven-development-with/9781491958698/
    [*] Retrieving book chapters...                                                 
    [*] Output directory:                                                           
        /XXXX/safaribooks/Books/Test-Driven Development with Python 2nd Edition (9781491958698)
    [-] Downloading book contents... (53 chapters)                                  
        [#####################################################################] 100%
    [-] Downloading book CSSs... (2 files)                                          
        [#####################################################################] 100%
    [-] Downloading book images... (142 files)                                      
        [#####################################################################] 100%
    [-] Creating EPUB file...                                                       
    [*] Done: /XXXX/safaribooks/Books/Test-Driven Development with Python 2nd Edition 
    (9781491958698)/9781491958698.epub
    
        If you like it, please * this project on GitHub to make it known:
            https://github.com/lorenzodifuccia/safaribooks
        e don't forget to renew your Safari Books Online subscription:
            https://learning.oreilly.com
    
    [!] Bye!!
    ```  
     The result will be (opening the `EPUB` file with Calibre):  

    ![Book Appearance](https://github.com/lorenzodifuccia/cloudflare/raw/master/Images/safaribooks/safaribooks_example01_TDD.png "Book opened with Calibre")  
 
  * ## Use or not the `--kindle` option:
    ```bash
    $ python3 safaribooks.py --kindle 9781491958698
    ```  
    On the right, the book created with `--kindle` option, on the left without (default):  
    
    ![NoKindle Option](https://github.com/lorenzodifuccia/cloudflare/raw/master/Images/safaribooks/safaribooks_example02_NoKindle.png "Version compare")  
    
---  
  
## Thanks!!
For any kind of problem, please don't hesitate to open an issue here on *GitHub*.  
  
*Lorenzo Di Fuccia*
