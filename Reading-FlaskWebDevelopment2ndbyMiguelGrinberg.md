---
title: Flask 網頁開發 第二版
description: Flask Web Development, 2nd Edition by Miguel Grinberg
image: 
tags: reading, python, flask
robots: noindex, nofollow
lang: zh-tw
---

**Flask 網頁開發 第二版**
Flask Web Development, 2nd Edition

用Python開發Web應用程式

　　“本書第二版保留了Miguel部落格文章的傳統及第一版的內容，兩者的結合讓我充分學會Flask，包括資料庫整合與開發。”—Jason Myers《Essential SQLAlchemy 第二版》(O’Reilly)作者
<!--more-->


![Flask 網頁開發 第二版](https://www.books.com.tw/img/001/079/34/0010793455.jpg =50%x50%)
* [圖書資料](http://www.books.com.tw/products/0010793455)
* 書名：Flask 網頁開發 第二版
* 原文名稱：Flask Web Development, 2nd Edition
* 語言：繁體中文
* ISBN：9789864768684
* 頁數：312
* 出版社：歐萊禮
* 作者：Miguel Grinberg
* 譯者：賴屹民
* 出版日期：2018/07/24
* 類別：電腦資訊
 
Task list: :smile:

- [x] 初稿
- [ ] 再讀
- [ ] 筆記
- [ ] 完成

# 目錄
第一部分 詳細介紹 Flask
第一章 安裝
第二章 基本 app 結構
第三章 模板
第四章 web 表單
第五章 資料庫
第六章 Email
第七章 大型的 app 結構

第二部分 範例：社群部落格 app
第八章 使用者身分驗證
第九章 使用者角色
第十章 使用者個人資訊
第十一章 部落格文章
第十二章 追隨者
第十三章 使用者評論
第十四章 應用程式開發介面

第三部分 最後一哩路
第十五章 測試
第十六章 效能
第十七章 部署
第十八章 其他的資源




## 第二章 基本 app 結構

1. Flask app 初始化
2. 路由、動態路由
3. Web server, Debug mode, command line



### [Flask 初始化](http://flask.palletsprojects.com/en/1.1.x/api/?highlight=flask#flask.Flask)

```python
class flask.Flask(
        import_name, 
        static_url_path=None, 
        static_folder='static', 
        static_host=None, 
        host_matching=False, 
        subdomain_matching=False,
        template_folder='templates', 
        instance_path=None,
        instance_relative_config=False, 
        root_path=None)
```
例子：`app = Flask(import_name)`
`import_name` 可以是 
1. `__name__` ，本檔的位置
2. 或是指定模組的位置

主要是指定 `Flask` 實體的位置，根目錄，用以定位其他資源的位置，`static`,`template`


### 路由
1. decorator `flask.Flask.route()`
2. function: `flask.Flask.add_url_rule()`
3. Werkzeug routing system : `flask.Flask.url_map`


```python
add_url_rule(rule, endpoint=None, view_func=None, provide_automatic_options=None, **options)
```

[URL Route Registrations.](https://flask.palletsprojects.com/en/1.1.x/api/#url-route-registrations "URL 註冊機制")

### Request, response

Flask context 全域變數
1. `current_app`:app context 是運行中的 app 實例
2. `g`:app context 處理 request 時，可當暫存區
3. `request`:request context, request 物件
4. `session`:request context, 用在各 request 間，記住使用者的資料


### Flask command line

[Flask 命令列模式](https://flask.palletsprojects.com/en/1.1.x/cli/?highlight=flask%20command)
[Working with the shell](https://flask.palletsprojects.com/en/1.1.x/shell/?highlight=flask%20command)

request hook : 可指定 request前，後作的動作
Response: request 的回應

## 第三章 模板

主要是要把business logic、和presentation logic 內容分開。

```python
from flask import Flask,render_template

@app.route('/')
def index():
    return render_template('index.html')
    
@app.route('/user/<name>')
def user(name):
    return render_template('user.html',name=name)
```

### Jinja2 語法

* functions : safe,capitalize,lower,upper,title,trim,striptags
* 控制結構：if,else,endif;for,endfor;block,endblock
* import template:extends 'base.html'

### Flask-Bootstrap
[Bootstrap][bootstrap]


## 第四章 Web 表單

WTF
https://flask-wtf.readthedocs.io/

* [flask_navbar](https://github.com/zcyuefan/flask-navbar) : 新版的flask-nav
* [flask base](https://github.com/hack4impact/flask-base)

HTMl Entity
* https://www.w3schools.com/html/html_entities.asp
* https://dev.w3.org/html5/html-author/charref


Flash
設定 Flash style(success,info,warning,danger)
* https://stackoverflow.com/questions/57660542/flask-closing-flash-message
* https://greyli.com/flask-set-let-flash-message-supports-a-bootstrap-message-style/

Bootstrap navbar
* https://www.w3schools.com/bootstrap/bootstrap_navbar.asp
* [利用 Bootstrap Grid System 排版的學習筆記](https://cythilya.github.io/2015/04/07/bootstrap-grid-system/)
* https://getbootstrap.com/docs/3.4/css/
* [Bootstrap 的圖示](https://www.w3schools.com/bootstrap/bootstrap_ref_comp_glyphs.asp)

## 第五章 資料庫

選資料庫
* Relation Data Model: PostgreSQL,...
* Document Data Model: MongoDB,...
* Graph Data Model: [Neo4j](#Ref),...


Database

* MySQL: RDBMS
* PostgresSQL : RDBMS
* SQLite : RDBMS, filedb
* Redis : key-value database, support by VMware
* MongoDB : document-oriented database 
* CouchDB : document-oriented NoSQL database,by Apache
* DynamoDB : document-oriented NoSQL database,by Amazon, AWS
* Neo4j : Graph database,written by Java

Flask-SQLAlchemy


DataBase Migrate
* SQLAlchemy.Alembic
    * https://alembic.sqlalchemy.org/en/latest/
* Flask-Migrate
    * https://flask-migrate.readthedocs.io/en/latest/

## 第六章 Email

寄信失敗
low security login
SMTP setting
https://support.google.com/a/answer/2956491?hl=zh-Hant&authuser=1
https://support.google.com/mail/answer/7126229?hl=zh-Hant
https://www.youtube.com/watch?v=qqOgDPSD3jc&feature=youtu.be
https://github.com/twtrubiks/Flask-Mail-example



## 第七章 大型的 App 結構

## 第八章 使用者身份驗證

Salted Password
https://crackstation.net/hashing-security.htm



# Ref
1. [作者 Miguel Grinberg 網站](blog.miguelgrinberg.com)
2. [本書 github repo](https://github.com/miguelgrinberg/flasky)
3. [Flask official site](https://flask.palletsprojects.com/)
4. [Flask Mega Tutorial](https://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-i-hello-world)
5. [前言-Flask Web 开发(第2版)](https://www.wrdll.com/article/flask-web-development-2nd-edition-preface "前言-Flask Web 开发(第2版)")
6. [初探Neo4j - Graph Database](http://sj82516-blog.logdown.com/posts/5823130)

[google]: https://www.google.com "Search Engine"
[bootstrap]: http://getbootstrap.com "Twitter OSS template"
[Flask-SQLAlchemy]: https://flask-sqlalchemy.palletsprojects.com/en/2.x/ ""