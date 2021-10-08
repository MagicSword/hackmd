---
title: MongoDB技術手冊第三版
description: MongoDB技術手冊第三版
image: https://www.books.com.tw/img/001/087/62/0010876210.jpg
tags: reading,database,mongodb
robots: noindex, nofollow
lang: zh-tw
---

**MongoDB技術手冊第三版**


　MongoDB是如何幫助你管理從網站應用程式蒐集而來的大量資料呢？藉由本書權威性的介紹，你可以了解文件導向式資料庫具有哪些優勢，以及如何駕馭MongoDB這個安全、高效能的系統，實作出一個高可用性、同時具備水平延展性的資料模型。 
<!--more-->

![MongoDB技術手冊第三版)](https://www.books.com.tw/img/001/087/62/0010876210.jpg "MongoDB技術手冊第三版" =30%x30%)
* [圖書資料](https://www.books.com.tw/products/0010876210)
* 書名： MongoDB技術手冊第三版
* 原文書名： MongoDB: The Definitive Guide: Powerful and Scalable Data Storage
* 作者：   Shannon Bradshaw, Eoin Brazil, Kristina Chodorow
* 譯者：   吳曜撰
* 出版社：歐萊禮
* 出版日期：2020/11/23
* ISBN：9789865026660
* 規格：平裝 / 536頁 / 18.5 x 23 x 2.68 cm / 普通級 / * 單色印刷 / 三版
* 出版地：台灣
* 本書分類：電腦資訊> 資料庫/大數據> NoSQL
 
Task list: :smile:

- [x] 初稿
- [ ] 再讀
- [ ] 筆記
- [ ] 完成

# 記錄

- 20211008 : 略讀一次，伺服器管理的內容略過。


# 目錄

第一部分 MongoDB 簡介 
* 第一章 簡介 
* 第二章 開始使用 
* 第三章 建立、更新以及刪除文件 
* 第四章 查詢 
 
第二部分 設計你的應用程式 
* 第五章 索引 
* 第六章 特別的索引和集合種類 
* 第七章 簡介聚集框架 
* 第八章 交易 
* 第九章 應用程式設計 
 
第三部分 複製 
* 第十章 設定複製組 
* 第十一章 複製組的元件 
* 第十二章 從應用程式連接複製組 
* 第十三章 管理 
 
第四部分 分片 
* 第十四章 簡介分片 
* 第十五章 配置分片 
* 第十六章 選擇分片鍵 
* 第十七章 分片管理 
 
第五部分 應用程式管理 
* 第十八章 查看應用程式在做什麼 
* 第十九章 MongoDB 安全性簡介 
* 第二十章 持久性 
 
第六部分 伺服器管理 
* 第二十一章 在正式環境中設定MongoDB 
* 第二十二章 監控MongoDB 
* 第二十三章 製作備份 
* 第二十四章 部署MongoDB 
 
附錄 A 部署MongoDB 
附錄 B MongoDB 內部運作 


# 心得

## 前言

本書分六部分

1. 開始使用 MongoDB
2. 開發  Designing Your Application
3. 複製 Replication
4. 分片 Sharding
5. 應用程式管理 Application Administration
6. 伺服器管理 Server Administration

先看附錄 A 安裝 MongoDB，另外 附錄 B 很短，大約看一下 MongoDB 的內部運作方式。

MongoDB 可以在本機電腦安裝server，也可以用MongoDB cloud 的 server. 這邊用 chocolatey 安裝 MongoDB。

chocolatey 安裝完後，執行 mongo.exe 即可進入 localhost的 server。


Client

- mongosh.exe
- MongoDB Compass
- NoSQL Manager
- Robo 3T

example: 用 mongosh.exe
- mongosh "mongodb://localhost:27017
- mongosh \"mongodb+srv://cluster0.uxts8.mongodb.net/sample_airbnb\" --username miller


## 第一部分 MongoDB 簡介 
### 第一章 簡介 

NoSQL 資料庫概念始於 1998 年, 原先是指一種不同於傳統關聯式, 不提供 SQL 功能的資料庫, 但目前已被重新定義為 Not Only SQL, 意指無綱要 (Schemaless), 分散式, 非關聯式, 不提供 ACID 特性的資料庫. 所謂 ACID 是指 :
- 最小性 (Atomicity)
- 一致性 (Consistency)
- 隔離性 (Isolation)
- 持久性 (Durability)

NoSQL 資料庫實作方式大致可分成如下四類, MongoDB 屬於其中的文件導向式資料庫 :

 |NoSQL 資料庫種類	 |說明
 |------------------|---------------
 |文件導向式 (Document)	 |MongoDB (Sourceforge), CouchDB, RavenDB
 |鍵值式 (Key-Value)	 |Redis (Flickr), Memcached, Dynamo (Amazon)
 |欄式 (Column)	 |Cassandra (Facebook), BigTable (Google), HBase, Hadoop
 |圖形式 (Graph)	 |Neo4J, GraphDB FlockDB (Twitter)


MongoDB 與 SQL 的術語對應如下 :

| MongoDB 術語	 |SQL 術語
|-----------------|-----------
| database 資料庫	 |database 資料庫
| collection 集合	 |table 資料表
| document 文件	 |row 列/紀錄
| field 欄位	 |column 行/欄

MongoDB 
- 容易使用：不需要預先定義  Schema, 文件的 key , value 沒有固定型態、或 大小。
- 有擴充性：有水平擴充的彈性(增加儲存空間)，內建 load balance
- 其他功能
    - Indexing
    - Aggregation
    - TTL
    - File Storage
- 不犧牲速度

### 第二章 開始使用 

- database 資料庫 -> database 資料庫
- collection 集合 -> table 資料表
- document 文件 -> row 列/紀錄
- field 欄位	 -> column 行/欄

- document 是一筆資料
- document 中 不能有同樣的 key
- MongoDB 有分大小寫
- 資料庫保留字：  
    - admin:記錄有管理權限的使用者
    - local:本地資訊？
    - config:用來儲存各 cluster 的分片資訊。


### 第三章 建立、更新以及刪除文件 

#### 建立
```javascript=
> db.movies.insertOne({"title":"Stand by Me"})
> db.movies.insertMany({"title":"Stand by Me"},
                       {"title":"E.T"}
                        )
```

- 插入的最大的文件大小：16MB

#### 刪除
- deleteOne
- deleteMany
- db.movie.drop()

#### 更新

- updateOne
- updateMany
- replaceOne

使用更新運算子 `$inc`,`$set`


### 第四章 查詢 

**目標**
- 能作範圍查詢、集合查詢、不等式、其他$字元條件式
- 查詢傳回的游標(cursor) 及使用方式
- 游標進階使用。跳過某些查詢結果、限制結果數量、排序結果。


#### 簡介查詢

`find()` : 像是 SQL 的 `SELECT`

#### 查詢條件式


`$lt` < , `$lte` <=, `$gt` >, `$gte` >=

ex: `> db.users.find({"age": {"$gte":18,"$lte":30}})`

#### OR 查詢

 - `$in`,
 - `$or`,

#### Not 查詢

-  `$not`

#### Null

null

#### 正規表示式

- `$regex`
- `> db.user.find({"name": {"$regex": /joe/i}})`

#### 查詢陣列

- `$all` :都符合條件
- `$size` : 陣列大小


``` javascript
db.food.insertOne({"fruit" : ["apple", "banana", "peach"]})
db.food.find({"fruit" : "banana"})
db.food.insertOne({"_id" : 1, "fruit" : ["apple", "banana", "peach"]})
db.food.insertOne({"_id" : 2, "fruit" : ["apple", "kumquat", "orange"]})
db.food.insertOne({"_id" : 3, "fruit" : ["cherry", "banana", "apple"]})
db.food.find({fruit : {$all : ["apple", "banana"]}})
db.food.find({"fruit" : ["apple", "banana", "peach"]})
db.food.find({"fruit.2" : "peach"})
db.food.find({"fruit" : {"$size" : 3}})
db.food.find({"size" : {"$gt" : 3}})
```

- `$slice` : 陣列子集

``` javascript
db.blog.posts.findOne({}, {"comments" : {"$slice" : 10}})
db.blog.posts.findOne({}, {"comments" : {"$slice" : -10}})
db.blog.posts.findOne({}, {"comments" : {"$slice" : [23, 10]}})
db.blog.posts.find({"comments.name" : "bob"}, {"comments.$" : 1})
```

#### 在內嵌文件上查詢

``` javascript
db.people.find({"name" : {"first" : "Joe", "last" : "Schmoe"}})
db.people.find({"name.first" : "Joe", "name.last" : "Schmoe"})
```

#### $where 條件子句


``` javascript
db.foo.insertOne({"apple" : 1, "banana" : 6, "peach" : 3})
db.foo.insertOne({"apple" : 8, "spinach" : 4, "watermelon" : 4})
db.foo.find({"$where" : function () { 
	for (var current in this) { 
		for (var other in this) {
			if (current != other && this[current] == this[other]) 
				{ return true; } 
		}
	}
	return false;
}});
```

#### Cursor 游標

傳回一個指標，可依條件依次傳回下一個結果。

- ` db.next()` : 呼叫下一個傳回值
- `db.hasNext()` : 是否有下一個值。

#### 限制、略過、排序

- ` db.limit(3)` : 傳回值少於三個
- `db.skip(4)` : 略過4個值
- `db.sort()` : 排序

``` javascript
var cursor = db.people.find();
cursor.forEach(function(x) { print(x.name); });
var cursor = db.foo.find().sort({"x" : 1}).limit(1).skip(10);
var cursor = db.foo.find().limit(1).sort({"x" : 1}).skip(10);
var cursor = db.foo.find().skip(10).limit(1).sort({"x" : 1});
cursor.hasNext()
```

#### 比較順序

#### 避免大量略過

#### 不使用略過來分頁結果

#### 隨機找文件

#### 永恆游標(Immortal)


## 第二部分 設計你的應用程式 

###  第五章 索引 

- 索引 如同 SQL 的 Index會加快搜索的速度，但是更新時速度也會稍微變慢。
-  不建議使用索引的情形：小集合、小文件，選擇性低的查詢

###  第六章 特別的索引和集合種類 

- 地理資訊索引：`2dsphere`, `2d` 可以儲存 GeoJSON
- 全文檢索的索引：
- GridFS : 用來存大型二進位檔


### 第七章 簡介聚集框架 Aggregation

- 聚集框架 Aggregation 是？類似 pipeline 可以把上一個輸出結果，當成下一個階段的輸入。


### 第八章 交易 

- 交易是？是資料庫中多個操作的組合


### 第九章 應用程式設計 

- Schema design considerations
- Trade-offs when deciding whether to embed data or to reference it
- Tips for optimization
- Consistency considerations
- How to migrate schemas
- How to manage schemas
- When MongoDB isn’t a good choice of data store

為了讓程式更有效率的執行，設定 Schema ，或一些最佳化也是必要的。

[MongoDB University - M320 Data Modeling ADVANCED](https://oreil.ly/BYtSr)


## 第三部分 複製 
### 第十章 設定複製組

Replica set : 備份伺服器的資料。
### 第十一章 複製組的元件 
### 第十二章 從應用程式連接複製組 
### 第十三章 管理 
 
## 第四部分 分片 Sharding
### 第十四章 簡介分片

- 分片 Sharding是？機器間拆分資料的過程，或用 Partitioning。可以用多個效能低的機器，分散儲存資料庫，來合作組成伺服器叢集。
### 第十五章 配置分片 
### 第十六章 選擇分片鍵 
### 第十七章 分片管理 
 
## 第五部分 應用程式管理 
### 第十八章 查看應用程式在做什麼

- 查看目前動作：`db.currentOp()`
- 刪除動作：`db.killOp(123)`
- 資料庫目前資訊 ： `db.stats()`
 
### 第十九章 MongoDB 安全性簡介 

- 身份驗證、加密通訊、加密資料


### 第二十章 持久性 

- 如何保持資料的一致性

## 第六部分 伺服器管理 
### 第二十一章 在正式環境中設定MongoDB 

- 原本的 `mongo.exe`
- 進階的 `mongosh.exe`

停止 MongoDB  的另一種方法
- `use admin`
- `db.shutdownServer()`


### 第二十二章 監控MongoDB 
### 第二十三章 製作備份 
### 第二十四章 部署MongoDB 
 
## 附錄 A 部署MongoDB 
## 附錄 B MongoDB 內部運作 

#### BSON

- MongoDB 中資料是用二進位的JSON ： BSON 儲存的。
- BSON的優點有
    - 效率
    - 移動性
    - 效能




# 參考資料
1. [@Oreilly](https://www.oreilly.com/library/view/mongodb-the-definitive/9781491954454/)
2. [Book github](https://github.com/mongodb-the-definitive-guide-3e/mongodb-the-definitive-guide-3e)
3. [MongoDB 官方 doc](https://docs.mongodb.com/mongodb-shell/)
4. [MongoDB 學習筆記 (二) : 樹莓派安裝 MongoDB](http://yhhuang1966.blogspot.com/search/label/MongoDB)
5. [MongoDB 基礎入門教學：MongoDB Shell 篇](https://blog.gtwang.org/programming/getting-started-with-mongodb-shell-1/)
6. [[MongoDb] 常用指令](https://dotblogs.com.tw/grayyin/2020/06/01/133724)
7. [7 天新手到進階學 MongoDB](https://zh-tw.coderbridge.com/series/800ffff9f7524d35ac6ecc51fffda4b9)
8. [MongoDB University - M320 Data Modeling ADVANCED](https://oreil.ly/BYtSr)



[google]: https://www.google.com "Search Engine"