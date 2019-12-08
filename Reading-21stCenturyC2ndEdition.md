---
title: 21世紀C語言（第二版）
description: 21st Century C, 2nd Edition
image: 
tags: Reading,Templates 
robots: noindex, nofollow
lang: zh-tw
---

**21世紀C語言（第二版）**
21st Century C, 2nd Edition

新時代的C語言建議

　　「你的C語言開發環境是否只有vi與cc？C語言的記憶體管理是否仍像90年代一樣令人困擾？Ben Klemens純熟的說明這些及其他常見的問題，展示透過工具簡化C語言開發，幫助開發人員除錯、追蹤記憶體洩漏、組織編譯過程以及管理原始程式碼版本」 -Dave Kitabjian NetCarrier Telecom軟體開發團隊主管

　　該是拋開對C語言舊有想法，由源頭重新學習的時候了，不論是新入門或重新複習，所有的讀者都可以從《21世紀C語言》的最新改版中，學到其他C語言書籍缺乏的最新技巧。

　　C語言不只是現代程式語言的基礎，本身也是現代程式語言，適合撰寫高效率、最先進的應用程式。請拋開大型主機時代的程式建議，學習這個與時俱進，十分簡單的程式語言所需要的工具。無論您目前喜好哪種程式語言，很快就能夠體會到21世紀C語言真的超酷。

　　‧利用shell工具、makefile、文字編輯器、除錯程式及記憶體檢查程式設定C語言開發環境
　　‧使用Autotools，這個C語言跨平台套件管理的實質標準
　　‧認識C語言中需要拋棄或忽略的陳舊觀念
　　‧使用C語言標準函式解決字串處理問題
　　‧在函式上使用結構化輸入的現代語法特性
　　‧建立以高階物件為基礎的函式庫與程式
　　‧使用現有C語言函式庫進行進階數學運算、與網際網路伺服器連線及操作資料庫

　　這個版本還新增了並行執行緒、虛擬表格、C99數值型別等諸多內容。
<!--more-->


![21世紀C語言（第二版）](https://www.books.com.tw/img/001/082/38/0010823824.jpg =50%x50%)
* [圖書資料](http://www.books.com.tw/products/0010823824)
* 書名：21世紀C語言（第二版）
* 原文名稱：21st Century C, 2nd Edition
* 語言：繁體中文
* ISBN：9789865021368
* 頁數：408
* 出版社：歐萊禮
* 作者：Ben Klemens
* 譯者：莊弘祥
* 出版日期：2019/06/06
* 類別：電腦資訊
 
Task list: :smile:

- [x] 初稿
- [ ] 再讀
- [ ] 筆記
- [ ] 完成

# 目錄
* 第一部分 環境
    * 第一章 簡化編譯過程的設定
    * 第二章 除錯、測試、文件
    * 第三章 打包專案
    * 第四章 版本控制
    * 第五章 攜手合作
* 第二部分 語言
    * 第六章 指標好伙伴
    * 第七章 教科書過分強調的進階語法
    * 第八章 教科書輕忽帶過的重要語法
    * 第九章 簡化文字處理
    * 第十章 更好的結構
    * 第十一章 C 語言的物件導向程式設計
    * 第十二章 平行執行緒
    * 第十三章 函式庫
* 結語
* 附錄A C 語言概述
* 術語表
* 參考文獻
* 索引

# 前言

C 的標準
* K & R 1978
* ANSI C89 1989 
* ISO C99 1999
    * 加入數值、科學計算，type-generic, 單行註解，for開頭宣告變數
* C11 2011
    * 泛型類別，安全性

POSIX 標準
* Unix
* POSIX (Portable Operating System Interface)
    * 提供 Unix 類作業系統共通的標準
    * c的 copen
* BSD
    * asprintf
    * clang
* GNU
    * gcc

# 第一部分 環境
OS: Windows,Linux,MacOS
Compiler: gcc-mingw64,clang,llvm,msvc
Editor: MSCode, vim, code-block


## 第一章 簡化編譯過程的設定

* 設定 MinGW, LLVM，設定 VSCode
  * https://junyou.tw/vscode-c/
  * https://blog.darkthread.net/blog/write-c-with-vscode/
  * Install package for mingw64: mingw-get.exe
  * [VSCode integration with cmder:](https://github.com/cmderdev/cmder/wiki/Seamless-VS-Code-Integration)

Makefile
* 用來簡化編譯流程
* 設定：`ln -s mingw64-make.exe make.exe`
```makefile
CC:=gcc
exe:=main.exe
obj:=hello-world.c

all:$(obj)
	$(CC) -o $(exe) $(obj)  

clean:
	rm -f $(exe)
```
* 最上面是變數取代
* 下面的 `all`, `clean` 是工作名稱
* 之前可打 `make all`, `make clean` ，就會執行 block內的動作。
* `make -p > make_rules` : 可看 make 的參數


`Here` document 用法
* 直接在 shell 輸入 , 不過只有 `POSIX` 的 shell能用
```sh
$ echo "print('hii')" | python -
$ hi
$ python - << "XXXX"
$ heredoc> print('hellosdjfdkals;fjdsa;')
$ heredoc>
$ heredoc> XXX
$ hellosdjfdkals;fjdsa;
```

## 第二章 除錯、測試、文件
* 如何 Debug , 
* Debug,Testing,Document的工具，
* GDB,Doxygen,CWEB,Valgrind

GDB,LLDB

* 使用：`gdb a.ext`
* 會進入互動指令空間
* GDB 指令
* frame 是？執行期間，每一個函式會指派一個 frame ，有獨立的變數資源空間。 stack frame

* 執行
    * run
    * run args
* 暫停
    * b func_name // 函式前停 
    * b pro.c:105 //檔案第幾行停
    * info break [GDB]
    * break list [LLDB]
    * watch curl [GDB] // 如果變數變化就停
    * watch set var curl [LLDB]
    * dis 3/ena 3/del 3 //中斷點操作 [GDB]
    * break dis 3/break ena 3/break del 3 [LLDB]
* 檢視變數
    * p url //print url
    * p *an_array@10 [GDB] //列出 ARRAY前10元素
    * mem read -tdouble -c10
    * info args/info var [GDB] //所有參數，變數值
    * frame var [LLDB] //所有參數，變數值
    * disp url //監看 url
    * undisp 3
* 執行緒
    * info thread [GDB]
    * thread list [LLDB]
    * thread 2 [GDB]
    * thread select 2 [LLDB]
* Frame
    * bt //列出 frame 堆疊
    * f 3 //檢視 frame 3
    * up 3/down 3 //依數字，在frame切換
* 單步執行
    * s //單步執行，會進函式
    * n //單步執行，不進函式
    * u //執行到目前行的下一行
    * c //執行到下一個斷點、或結尾
    * ret / ret 3 [GDB]
    * j 105 [GDB]
* 檢視程式
    * L //列出附近10行程式
* 重複
    * Enter
* 編譯
    * make [GDB]
* 輔助資訊
    * help
* 改變變數
    * set *$prt = 9 //改變變數值
    * set $vd = my_model -> dataset -> vector -> data //設定變數值
    * mem read -tdouble -c10 $vd //


* `p` 之前的結果，也可以拿來用
```c
$16 = 20
(gdb) p x+3
$17 = (int *) 8
(gdb) p *$17
$18 = 8
```

* [程式碼內加入監視](https://b8807053.pixnet.net/blog/post/336154079-%5B%E8%BD%89%E8%B2%BC%5Dgdb-%E4%BB%8B%E7%B4%B9)
```c
#ifdef DEBUG
                printf("No: %d, Password= %04d\n",i,password[i]);
#endif
```
```sh
gcc -o Password -DDEBUG Password.c
#以下是執行結果之一：
No: 1, Password= 7815
No: 2, Password= 6157
No: 3, Password= 7479
No: 4, Password= 9017
Segmentation fault
```



以下是 gdb 的常見指令（其中 () 內為簡短指令）：
* help (h)：顯示指令簡短說明。例：help breakpoint
* file：開啟檔案。等同於 gdb filename
* run (r)：執行程式，或是從頭再執行程式。
* kill：中止程式的執行。
* backtrace (bt)：堆疊追蹤。會顯示出上層所有的 frame 的簡略資訊。
* print (p)：印出變數內容。例：print i，印出變數 i 的內容。
* list (l)：印出程式碼。若在編譯時沒有加上 -g 參數，list 指令將無作用。
* whatis：印出變數的型態。例： whatis i，印出變數 i 的型態。
* breakpoint (b, bre, break)：設定中斷點
* 使用 info breakpoint (info b) 來查看已設定了哪些中斷點。
* 在程式被中斷後，使用 info line 來查看正停在哪一行。
* continue (c, cont)：繼續執行。和 breakpoint 搭配使用。
* frame：顯示正在執行的行數、副程式名稱、及其所傳送的參數等等 frame 資訊。
* frame 2：看到 #2，也就是上上一層的 frame 的資訊。
* next (n)：單步執行，但遇到 frame 時不會進入 frame 中單步執行。
* step (s)：單步執行。但遇到 frame 時則會進入 frame 中單步執行。
* until：直接跑完一個 while 迴圈。
* return：中止執行該 frame（視同該 frame 已執行完畢），
* 並返回上個 frame 的呼叫點。功用類似 C 裡的 return 指令。
* finish：執行完這個 frame。當進入一個過深的 frame 時，如：C 函式庫，
* 可能必須下達多個 finish 才能回到原來的進入點。
* up：直接回到上一層的 frame，並顯示其 stack 資訊，如進入點及傳入的參數等。
* up 2：直接回到上三層的 frame，並顯示其 stack 資訊。
* down：直接跳到下一層的 frame，並顯示其 stack 資訊。
* 必須使用 up 回到上層的 frame 後，才能用 down 回到該層來。
* display：在遇到中斷點時，自動顯示某變數的內容。
* undisplay：取消 display，取消自動顯示某變數功能。
* commands：在遇到中斷點時要自動執行的指令。
* info：顯示一些特定的資訊。如： info break，顯示中斷點，
* info share，顯示共享函式庫資訊。
* disable：暫時關閉某個 breakpoint 或 display 之功能。
* enable：將被 disable 暫時關閉的功能再啟用。
* clear/delete：刪除某個 breakpoint。
* set：設定特定參數。如：set env，設定環境變數。也可以拿來修改變數的值。
* unset：取消特定參數。如：unset env，刪除環境變數。
* show：顯示特定參數。如：show environment，顯示環境變數。
* attach PID：載入已執行中的程式以進行除錯。其中的 PID 可由 ps 指令取得。
* detach PID：釋放已 attach 的程式。
* shell：執行 Shell 指令。如：shell ls，呼叫 sh 以執行 ls 指令。
* quit：離開 gdb。或是按下 <Ctrl><C> 也行。
* <Enter>：直接執行上個指令


[Dr. Memoy](https://github.com/DynamoRIO/drmemory/wiki/Downloads)
* 跟 Valgrind 一樣的工具, 記憶體檢測
* [Dr.Memory doc](http://drmemory.org/docs/)

Unit Test

Programming as lib

Test Coverage

Error check

文件工具
1. Doxygen : 從程式碼中取出註解，產生文件
2. CWEB : 程式碼類似一般的英文

## 第三章 打包專案

* Unix下打包工具：Automake, Autotools,libtools
* Windows下有 CMake

## 第四章 版本控制

Git

## 第五章 攜手合作

* 載入動態物件 dlopen、靜態物件 dlsym
* Windows 下有 LoadLibrary, GetProcAddress
* Work with Python
 
# 第二部分 語言
## 第六章 指標好伙伴

* 指標，指標運算、命令指標變數，記憶體管理， `ifdef`

## 第七章 教科書過分強調的進階語法

[cite](https://michaelchen.tech/review/21st-century-c-2nd-edition/)
* 在 main 函式 return 0;
* 在程式最頂端命名所有變數 (註：C89 的限制。)
* 在執行期設置陣列長度
* 減少 cast 的次數
* 少用 enum
* 適當地用 goto 而非完全不用
* 少用 float，多用 double
* 用安全的函式，包括 strtol 或 strtod 等，將字串轉為數字


## 第八章 教科書輕忽帶過的重要語法

* Macro
* #pragma once
* static , extern
* const pitfalls
 
## 第九章 簡化文字處理

* asprintf
* strtok 切字串
* Unicode

## 第十章 更好的結構

* C99 後的一些新特性

## 第十一章 C 語言的物件導向程式設計

OOP

## 第十二章 平行執行緒

* OpenMP
* PThreads
* C11 what's new

## 第十三章 函式庫

* GLib
* POSIX
* GUN Scientific Library
* SQLite
* libxml
* cURL

# 結語

# 附錄A C 語言概述

## 術語表
## 參考文獻
## 索引


 
# 參考資料
1. [Author,Ben Klemens](https://ben.klemens.org/)
2. [Book github](https://github.com/b-k/21st-Century-Examples)
3. [2017 iT 邦幫忙鐵人賽 - C-Programming 系列](https://ithelp.ithome.com.tw/users/20103639/ironman/1195)
4. [[書籍回顧] 21st Century C, 2nd Edition 評價](https://michaelchen.tech/review/21st-century-c-2nd-edition/)



[google]: https://www.google.com "Search Engine"