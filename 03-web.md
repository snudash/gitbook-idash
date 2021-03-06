# 웹 서비스 시작하기

## 웹 기술

웹은 WWW (World Wide Web)을 짧게 부르는 말로 1989년 Tim Berners-Lee의 제안에 의해 시작되었으며 현재 인터넷 자체를 의미할 정도의 위상을 가지고 있습니다. 웹을 가능하게 하는 웹 기술을 구성하는 요소는 여러가지가 있으나 HTML, CSS, JavaScript가 현재 핵심적인 위치를 차지하고 있습니다. 웹 기술을 발전과 함께 소위 홈페이지를 넘어서 응용 소프트웨어로까지 발전하고 있습니다. 예를 들어, Microsoft Office 365는 웹 브라우저 상에서 기존의 Microsoft Office 응용 프로그램의 기능을 제공하고 있습니다. 모바일 시대가 오고 구독 서비스라는 비지니스와 맞물리며 이러한 웹 어플리케이션은 더욱 각광받고 있습니다.

* [웹](https://ko.wikipedia.org/wiki/월드_와이드_웹)
* [웹 어플리케이션](https://ko.wikipedia.org/wiki/웹_애플리케이션)
* [웹 기술](https://developer.mozilla.org/ko/docs/Web)
* [HTML \(HyperText Markup Language\)](https://ko.wikipedia.org/wiki/HTML)
* [CSS \(Cascading Style Sheet\)](https://ko.wikipedia.org/wiki/종속형_시트)
* [JavaScript](https://ko.wikipedia.org/wiki/자바스크립트)
* [SVG \(Scalable Vector Graphics\)](https://ko.wikipedia.org/wiki/스케일러블_벡터_그래픽스)

어떤 컴퓨터에 웹 페이지를 만들어 놓으면 다른 컴퓨터에서 그 웹 페이지를 볼 수 있습니다. 인터넷 상에서 서로 연결되어 있기 때문이죠. 이때 그냥 한 컴퓨터의 디스크에 파일을 저장해 놓는다고 해서 다른 컴퓨터에서 웹 페이지를 볼 수 있는 것이 아닙니다. 웹 페이지를 제공하는 컴퓨터를 서버라고 하고 그 페이지를 보기 위해 접속해 오는 컴퓨터를 클라이언트라고 합니다. 여기서 서버는 단순히 물리적인 하드웨어 컴퓨터를 지칭하는 것이 아닙니다. 서버 컴퓨터에 웹 페이지를 서비스하는 프로그램이 돌아가고 있어야 합니다. 클라이언트 컴퓨터에서 웹 페이지를 보여달라는 요청이 오면 그에 맞추어 파일을 보내주는 일을 하는 소프웨어가 있어야 하는 것이죠. 서버라는 말은 바로 이 프로그램을 지칭하는 데에도 사용됩니다. 여러분의 컴퓨터에 웹 페이지를 만들고 다른 사람들이 보도록 하려면 웹 서버 프로그램이 구동되고 있어야 합니다.

* [클라이언트-서버 모델](https://ko.wikipedia.org/wiki/클라이언트_서버_모델)
* [서버](https://ko.wikipedia.org/wiki/서버)
* [클라이언트](https://ko.wikipedia.org/wiki/클라이언트_%28컴퓨팅%29)

클라이언트가 어떤 요청을 보내면 그것을 받아서 서버에서 프로그램이 실행이 되고 그 결과만 클라이언트에게 보내주는 프로그램을 만드는 것을 서버 사이드 프로그래밍이라고 합니다. PHP 언어가 오래된 대표적인 예의 하나입니다. 이외에도 서버에서 실행될 수 있는 많은 언어가 서버 사이드 프로그래밍에 사용될 수 있습니다. 클라이언트에게 아예 프로그램 자체를 보내서 클라이언트의 웹 브라우저에서 실행되도록 하는 것을 클라이언트 사이드 프로그래밍이라고 합니다. 웹 브라우저에서 실행되는 언어는 바로 JavaScript입니다. 요즘에는 JavaScript를 웹 브라우저에서 해방시켜 어디서나 실행가능하게 하고 결국은 서버 사이드 프로그래밍을 가능하게 하는 Node가 인기 있는 기술 중의 하나가 되었습니다.

* [Node.js](https://nodejs.org/ko/)

## Apache2: 웹 서버

구글 클라우드에 Ubuntu 가상머신을 생성하고 웹 서버로 사용하려면 웹 서버스를 가능하게 해 주는 소프트웨어를 설치해야 합니다. 가장 널리 사용되는 것 중의 하나가 [Apache HTTP Server](https://httpd.apache.org/)입니다. 패키지 관리자를 이용하여 다음처럼 설치하세요.

```bash
sudo apt update                      # Download package information
sudo apt upgrade                     # Install upgradable packages
sudo apt install apache2             # Install Apache2 web server
```

웹 서버가 서비스를 할 웹 페이지는 DocumentRoot 디렉토리에 저장해야 합니다. 우분투에서 DocumentRoot는 따로 설정하지 않은 한 기본적으로 `/var/www/html`로 되어 있습니다.

```bash
cd /var/www/html                     # Go to Web Root Directory
sudo mv index.html apache2.html      # Rename Apache2 Default Page
```

기본 apache2 페이지는 삭제하거나 옮기고 `/var/www/html` 디렉토리 아래 자신의 웹 문서를 넣으면 됩니다. 웹 브라우저에서 자신의 가상머신의 IP 주소를 치면 `/var/www/html/index.html` 파일 열릴 것입니다.

## PHP: 서버 사이드 프로그래밍

우리 수업에서는 서버 사이드 프로그래밍을 하지 않을 것입니다. 여기에서 잠깐 간단한 예만 보고 가겠습니다. 서버 프로그래밍에서 널리 사용되는 언어 중의 하나인 PHP 언어를 살펴보겠습니다. 더 자세히 알고 싶으시면 다음 페이지를 보세요.

* [PHP 기본 수업](https://opentutorials.org/course/62) (at <opentutorials.org>)

우선 다음처럼 PHP 프로그래밍 언어와 아파치 웹 서버에서 PHP를 사용할 수 있게 해 주는 모듈을 설치하세요. 그리고 아파치 웹 서버를 재시동하세요.

```bash
sudo apt install php libapache2-mod-php
sudo systemctl restart apache2
```

그리고 다음과 같이 간단하 내용이 들어있는 `phpinfo.php` 파일을 `/var/www/html`에 작성하고 웹브라우저에서 열어 보세요.

```php
<?php
  phpinfo()
?>
```

여기서 PHP에 관한 정보가 길게 나오면 모든 설치와 설정이 제대로 이루어진 것입니다.

### 서버 사이드 프로그래밍 예제

이제 PHP 언어를 이용하여 간단한 서버 사이드 프로그래밍을 해 봅시다. 웹페이지에서 숫자 2개를 입력 받아 더하여 출력하는 프로그램입니다. 다음 두 파일을 웹 서버에 올리고 html 파일을 열어보세요.

다음은 `calc.html` 파일입니다. 텍스트 에디터에서 이 내용 그대로 작성하면 됩니다.

```markup
<html>
  <body>
    <form action="calc.php" method="post">
      <input type="text" name="x"> +
      <input type="text" name="y">
      <input type="submit">
    </form>
  </body>
</html>
```

다음은 `calc.php`파일이다. 역시 텍스트 에디터에서 똑같이 작성하면 됩니다.

```php
<html>
<body>
<?php
  $x = $_POST["x"];
  $y = $_POST["y"];
  $sum = $x + $y;
  echo $x . " + " . $y . " = " . $sum;
?>
</body>
```

혹시 웹 서버에 올린다는 말이 무엇인지 모르시나요? 자신의 가상머신에 sftp로 접속을 해서 파일을 업로드한 후에 `/var/www/html` 디렉토리에 넣으면 됩니다. 파일을 이동하거나 복사할 때 `sudo`가 필요할 수 있습니다. 업로드할 때에는 sftp로 접속해서 자신의 홈 디렉토리에 올리고 ssh로 접속해서 `/var/www/html` 디렉토리로 이동하면 됩니다.

## 개별 사용자 홈페이지

이 내용은 여러분이 꼭 따라해야 하는 것은 아닙니다. 해봐서 나쁠 것은 없습니다. 그렇게 어려운 것도 아닙니다. 하지만 잘 안 된다면 시간을 너무 빼앗기지는 마세요.

### userdir

웹 서버에 계정을 가진 사용자마다 개별적으로 자신의 홈페이지를 만들 수도 있습니다. 각 사용자 홈페이지의 주소는`www.hostname.com/~username`과 같은 형식이 됩니다. 이 기능을 활성화하려면 다음과 같은 명령을 내리세요.

```bash
sudo a2enmod userdir
```

각 사용자들은 자신의 홈 디렉토리 아래 `public_html` 디렉토리를 만들고 웹 문서를 넣으면 됩니다.\`\`\`

### PHP

만약 userdir에서 php를 가능하게 하려면 `/etc/apache2/mods-enabled/php7.2.conf` 파일을 열어서 다음처럼 주석 처리를 해야 합니다.

```text
# Running PHP scripts in user directories is disabled by default
# 
# To re-enable PHP in user directories comment the following lines
# (from <IfModule ...> to </IfModule>.) Do NOT set it to On as it
# prevents .htaccess files from disabling it.
#<IfModule mod_userdir.c>
#    <Directory /home/*/public_html>
#        php_admin_flag engine Off
#    </Directory>
#</IfModule>
```

## 기타

기타 필요한 것들을 다음과 같은 명령으로 설치할 수 있습니다.

```bash
sudo apt install nodejs
sudo apt install python3
sudo apt install emacs25-nox
```

## HTML

웹 페이지는 HTML \(HyperText Markup Language\)라는 언어로 작성합니다. 이 언어로 작성한 텍스트 파일을 확장자를 `.html`로 하여 웹 서버에 올리면 됩니다. HTML 언어는 1993년에 처음 공개되었고 버전 업을 거듭하여 현재는 2014년에 나온 HTML5가 표준으로 사용되고 있습니다. 이런 웹 관련 기술들은 대개 W3C \(World Wide Web Consortium\)에서 개발하고 관리합니다. 예를 들어 다음 페이지에서 W3C 권고안을 볼 수 있습니다.

* [https://www.w3.org/TR/html51/](https://www.w3.org/TR/html51/)

하지만 이런 기술적인 문서들을 읽는 것은 까다로운 일이이고 HTML을 배우는 학습 자료로 사용하기는 곤란합니다. W3C와 관련은 없지만 W3Schools가 웹 기술들 즉, HTML, CSS, JavaScript, PHP 등에 관련된 정보를 학습하거나 참고용으로 찾아보기 좋은 형태로 잘 정리하여 제공하고 있습니다.

* [https://www.w3schools.com/](https://www.w3schools.com/)

우선 가장 처음 배워야 할 것은 HTML인데 다음 페이지에 HTML의 태그들이 기능별로 정리되어 있으니 한번 둘러 보세요.

* [https://www.w3schools.com/tags/ref\_byfunc.asp](https://www.w3schools.com/tags/ref_byfunc.asp)

