---
title: SQL語法查詢入門｜挖掘數據真相征服大數據時代的第一本書
description: Practical SQL
image: 
tags: reading, sql, postgresql
robots: noindex, nofollow
lang: zh-tw
---

**SQL語法查詢入門｜挖掘數據真相征服大數據時代的第一本書**
Practical SQL

SQL是一種用建立、管理和查詢資料庫的程式語言。無論您是分析師、記者或是從事學術研究的研究人員，都可以運用SQL來發掘隱藏在數據中的故事。

　　本書除了解說SQL以及資料庫的基礎知識之外，還會告訴您如何使用pgAdmin和PostgreSQL資料庫系統來建立、組織和分析真實世界的資料，像是犯罪統計資料或人口普查統計數據，同時也將告訴您如何在資料庫中進行運算，以及排解實際工作過程中常見的障礙。

　　透過本書，您將了解如何：
　　．為您的資料定義正確的數據類型
　　．聚合、排序和過濾數據以查找模式
　　．識別並清除數據中的任何錯誤
　　．搜尋有意義數據的文字
　　．建立進階查詢並自動完成繁瑣的任務
 
<!--more-->


![SQL語法查詢入門｜挖掘數據真相，征服大數據時代的第一本書](https://www.books.com.tw/img/001/082/02/0010820274.jpg =50%x50%)
* [圖書資料](http://www.books.com.tw/products/0010820274)
* 書名：SQL語法查詢入門｜挖掘數據真相征服大數據時代的第一本書
* 原文名稱：Practical SQL
* 語言：繁體中文
* ISBN：9789865020989
* 頁數：472
* 出版社：碁峰
* 作者：Anthony DeBarros
* 譯者：林班侯
* 出版日期：2019/04/29
* 類別：電腦資訊
 
Task list: :smile:

- [x] 初稿
- [ ] 再讀
- [ ] 筆記
- [ ] 完成

# 目錄
第1章｜建立你的第一個資料庫和資料表
初步介紹了PostgreSQL、pgAdmin使用者介面、以及如何將簡易教師資料集匯入到新建資料庫當中。

第2章｜用SELECT 開始探索資料
教各位探索基本的SQL 查詢語法，包括如何排序及篩選資料。

第3章｜了解資料類型
解釋了如何設置資料表欄位來儲存特定型態的資料，從文字到各種形式的數字都有。

第4章｜匯入與匯出資料
說明如何利用SQL 指令從外部檔案載入資料、以及如何加以匯出。各位會試著載入一套美國人口普查資料表，而且後面的章節都會用到它。

第5章｜SQL 的基礎數學計算與統計
涵蓋了算術運算，並介紹各種匯總函式，用來計算總和、平均值及中間值等等。

第6章｜在關聯式資料庫中結合資料表
說明如何透過關鍵欄位結合多個彼此有關聯的資料表、以便進行查詢。各位將學到如何執行結合，也會學到何時應當使用何種結合方式。

第7章｜適合你的資料表設計
涵蓋如何建置資料表才能提升你的資料組織性和正確性，也會告訴各位如何以索引加速查詢。

第8章｜利用群聚（Grouping）和總結（Summarizing）來擷取資訊
說明如何利用匯總函式，從年度調查中找出美國圖書館運用的趨勢。

第9章｜調查與修改資料
會以關於肉品、雞蛋及家禽生產商的記錄資料為例，探討如何找出和修正不完整或不正確的資料。

第10章｜SQL 裡的統計函式
簡介了SQL 中的相關性、回歸及排序等函式，以便讓你從資料中推導出更多結論。

第11章｜日期與時間的處理
以紐約市計程車乘運和美國國鐵（Amtrak）時間表的資料為例，說明在資料庫中如何建立、處理和查詢日期及時間，包括如何處理時區。

第12章｜進階查詢技巧
說明如何使用更繁複的SQL 運算，例如子查詢（subqueries）和交叉製表、以及CASE 敘述，將溫度讀數的資料值重新分類。

第13章｜探勘文字以找出有意義的資料
以美國歷任總統演說辭為例，涵蓋如何利用PostgreSQL 的全文檢索引擎和正規表示式，從雜亂無章的文字中擷取資料。

第14章｜用PostGIS 分析空間資料
介紹了與空間物體有關的資料類型和查詢，讓你可以分析地理特徵，如州境、道路與河流等等。

第15章｜利用檢視表、函式和觸發程序來節省時間
說明如何把資料庫作業自動化，以避免重複性的工作。

第16章｜從指令列操作PostgreSQL
涵蓋如何在你電腦的命令提示畫面使用文字指令，以便連接資料庫並執行查詢。

第17章｜維護你的資料庫
提供若干訣竅與程序，用於追蹤資料庫規模、自訂設定方式、以及備份資料。

第18章｜找出並述說資料背後的故事
提供了基本指南，教大家如何把分析化為概念、如何審閱資料、如何產生結論、以及如何明確地呈現你的發現等等。

附錄A：其他的PostgreSQL 資源
列舉各種可以協助你提升技巧的軟體及文件。


# 導論

民族是什麼？書單

民族的定義：
: 民族認同(national identity)?  
: 血統、語言、文化…

* 第一章 民族新義：從革命到自由主義
* 民眾觀點： 民族主義原型
* 政府觀點
* 民族主義轉型：一八七○-一九一八
* 民族主義高峰：一九一八-一九五○
* 二十世紀晚期民族主義
 
# 參考資料
1. [決戰熱蘭遮][]
2. [熱蘭遮城日誌][]
3. 
4. 



[決戰熱蘭遮]: https://www.books.com.tw/products/0010773335 "決戰熱蘭遮"
[熱蘭遮城日誌]: https://zh.wikipedia.org/wiki/%E7%86%B1%E8%98%AD%E9%81%AE%E5%9F%8E%E6%97%A5%E8%AA%8C "熱蘭遮城日誌"
[google]: https://www.google.com "Search Engine"