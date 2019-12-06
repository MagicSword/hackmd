---
title: 月亮般輕盈：用Lua成為指令稿語言大師
description: 用Lua成為指令稿語言大師
image: 
tags: reading, library, lua
robots: noindex, nofollow
lang: zh-tw
---

**月亮般輕盈：用Lua成為指令稿語言大師**


Lua是一種可嵌入、高效、輕量級、功能強大的指令稿語言，主要應用在遊戲領域。另外，基於Nginx的OpenResty也是使用Lua編寫指令稿的，很多伺服器（如Redis）也支援使用Lua編寫指令稿。

　　作為一門以純C程式碼編寫的專案，Lua程式碼優美、結構組織緊湊，是經典的C語言專案。

　　本書討論Lua語言的設計原理，架構如下：

　　■ 第一部分說明Lua 中的資料結構，如透用資料是如何表示的，Lua 的字串以及表類型的實現原理。
　　■ 第二部分是本書最重要的部分，主要討論Lua 虛擬機器的實現，分類說明Lua 虛擬機器中的一些重點指令。
　　■ 第三部分的內容比較雜，討論垃圾回收、模組實現、熱更新、程式碼協同等的實現原理。
  
本書特色

* 　　√  揭示Lua實現原理
* 　　√ 經典的純C語言專案分析
* 　　√ 一線開發人員傾力打造
<!--more-->


![月亮般輕盈：用Lua成為指令稿語言大師](https://www.books.com.tw/img/001/080/73/0010807362.jpg =50%x50%)
* [圖書資料](http://www.books.com.tw/products/0010807362)
* 書名：月亮般輕盈：用Lua成為指令稿語言大師
* 語言：繁體中文
* ISBN：9789863797272
* 頁數：304
* 出版社：佳魁資訊
* 作者：codedump
* 出版日期：2018/12/05
* 類別：電腦資訊
 
Task list: :smile:

- [x] 初稿
- [ ] 再讀
- [ ] 筆記
- [ ] 完成

# 目錄

前  言

Chapter01 概述
1.1 前世今生
1.2 原始程式組織
1.3 Lua 虛擬機工作流程

Chapter02 Lua 中的資料類型
2.1 C 語言中實現通用資料結構的一般做法
2.2 Lua 通用資料結構的實現

Chapter03 字串
3.1 概述
3.2 字串實現

Chapter04 表
4.1 資料結構
4.2 操作演算法

Chapter05 Lua 虛擬機器
5.1 Lua 執行過程概述
5.2 資料結構與堆疊
5.3 指令的解析
5.4 指令格式
5.5 指令的執行
5.6 偵錯工具

Chapter06 指令的解析與執行
6.1 Lua 詞法
6.2 設定值類別指令
6.3 表相關的操作指令
6.4 函數相關的操作指令
6.5 數值計算類別指令
6.6 關係邏輯類別指令
6.7 循環類別指令

Chapter07 GC 演算法
7.1 原理
7.2 資料結構
7.3 實際流程
7.4 進度控制

Chapter08 環境與模組
8.1 環境相關的變數
8.2 模組

Chapter09 偵錯器工作原理
9.1 鉤子功能
9.2 獲得目前程式資訊
9.3 列印變數
9.4 檢視檔案內容
9.5 中斷點的增加
9.6 檢視目前堆疊資訊
9.7 step 和next 指令的實現

Chapter10 例外處理
10.1 原理
10.2 Lua 實現

Chapter11 程式碼協同
11.1 概念
11.2 相關的API
11.3 實現

AppendixA 參考資料

# 前言

* Lua 出生於 1993 巴西里約熱內盧 Pontifical Catholic University(PUC-Rio), Tecgraf Lab.
* 作者是 Roberto Ierusalimschy , Luiz Henrique de Figueiredo , Waldemar Celes
* 因巴西政府在 1977~1992 的市場保護 政策，不能進口外國軟體，所以 Tecgraf 實驗室 客製了許多軟體。
* DEL(Date Entry Language), SOL(Simple Object Language) 是 Lua的前身
* 常用於嵌入，例 game , WOW addons.
* 穩定版本	5.3.5 （ 2018年7月10日，​16個月前 ）

Lua 特性

* 定位：嵌入式的指令碼語言
* 可攜性：
* 良好的嵌入性：
* 非常小的尺寸：
* 效率很高，速度快：


 
# 參考資料
1. [book github](https://github.com/lichuang/Lua-5.1.4-codedump)
2. [Author site](https://www.codedump.info/)
3. [Lua official site](https://www.lua.org/)
4. 



[google]: https://www.google.com "Search Engine"