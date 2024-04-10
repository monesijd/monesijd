# 顧泓 學習歷程

# 使用 GitHub 的動機

有鑑於各大學電資學系課程，對程式學習及成長脈絡十分重視，而現今 GitHub 平台對於個人程式有著相當有系統的管理機制，可以透過該平台詳實記錄我的學習歷程，藉由版本控制系統 Git ，可以輕易地找到某一個時段某一段程式的程式碼，查詢當時的思考邏輯，這對初學程式的我來說幫助很大。

# 簡介

姓名: 顧泓

熟悉的程式語言: C, Python

GitHub: https://github.com/monesijd

# APCS 紀錄

2022年10月23日: 實作2級 觀念3級

2023年01月08日: 實作3級 觀念2級

**2023年06月04日: 實作3級 觀念4級**

# 解題歷程

這邊記錄我自己解題的紀錄

## beecrowd

一開始學習程式的時候，查詢網路後，我找到了 beecrowd 的解題網站。雖然這個網站是英文，但題目都較為基礎，我認為非常適合拿來練習新學的程式。
相關的解題紀錄，放在https://github.com/monesijd/beecrowd

## Zerojudge

我有空的時候會找 ZeroJudge 上的題目練習培養手感，寫的程式碼我會根據題目代號作為命名依據，放在 https://github.com/monesijd/zerojudge

# 專案開發

## 專案一

開發一個可以查詢登革熱資訊的 line 機器人，機器人放在 render.com 使用免費方案，repo 在 https://github.com/monesijd/line_bot

## 專案二

開發可以執行 Python 程式並將結果回傳至頻道的機器人，repo 在 https://github.com/monesijd/discord_bot

# 軟體開發實務

## 版本控制系統 Git

## 編輯器

### VScode

### Neovim

```
Normal mode (按 ESC 或 Ctrl-C)
hjkl 左上下右
yy 複製當下的這一行 (補充 如果前面有數字 就可以一口氣複製多行，比如 10yy 代表複製 10 行)
p 將複製的內容貼到當下位置的下一行
dd 刪除當前的這一行
G 移動到檔案最後一行 (補充 如果前面有數字 可以跳到指定的行數，比如 1G 代表跳到第一行)
dG 從當前的這一行到檔案的最後一行通通刪掉
gg 代表的是跳到第一行
i 從游標位置開始輸入
o 從游標位置下一行開始輸入
O 從游標位置上一行開始輸入
x 從游標的位置刪掉右邊的一個字元，前面如果有數字代表一次刪掉幾個字元，比如 10x 代表往右刪掉 10 個字元
X 從游標的位置刪掉左邊的一個字元
w 從游標位置跳到下一個 word (指的是英語系國家的 word) 的開頭
/ 往下搜尋 (在搜尋的畫面中，按下 n (next) 代表跳到下一個符合樣式的位置，按下 N 代表跳到上一個符合樣式的位置)
^ 游標移動到該行字串的開頭
$ 游標移動到該行字串的結尾
V 可以進到 visual mode，會看到反白的效果，此時移動游標會以行為單位反白
u undo 復原回到上一步
ctrl-r redo 回到下一步


Insert mode (按下 i/I/a/A/o/O)
ctrl-p 補全


Command mode (按下 :)
w 寫入
q 離開
! 強制
set nu(mber)
```

### 正規表示式 (Regular Expression)

```
. 符合任一個字元
[A-Z] 符合任一大寫字母
[a-z] 符合任一小寫字母
[a-zA-Z] 符合任一字母
[0-9] 可以簡寫成 \d 代表的是 decimal，然後 \D 和 \d 是反義，所以 \D 等同 [^0-9]
[A-Za-z0-9_] 可以簡寫成 \w 代表的是 word，然後 \W 和 \w 是反義，所以 \W 等同 [^A-Za-z0-9_]
[ \t\n\r\f\v] 可以簡寫成 \s 代表的是 space，然後 \S 和 \s 是反義，所以 \S 等同 [^ \t\n\r\f\v]
\b 比對到邊界，boundry 的意思，本身不佔字元。\B 是反義

Quantifiers 量詞 (用來指定前一個字元出現的數量)
? 0或1個字元
* 0或多個字元
+ 1或多個字元
{n, m} 必須出現介於 n 和 m 次數之間

greedy 行為
re.findall(r'a.+b', 'acbddddddb') => 回傳 ['acbddddddb']

non-greedy 行為 (量詞後面加上一個問號)
re.findall(r'a.+?b', 'acbddddddb') => 回傳 ['acb']

定位符號
^ 代表比對開頭的位置
$ 代表比對結尾的位置

findall 和 search 的差別
findall 是管家婆，同一行文字就算比對到，還是會繼續往下比對直到字串結束。search 同一行比對到就不會再比對

search 和 match 的差別
search 只要字串中有符合正規表示式的文字即可，而 match 會特別只從頭比對

正規表示式最好先編譯再比對
re.* 的呼叫都會即時編譯才比對，當行數很多時會耗用無謂的資源，此時可以先呼叫
re.compile() 做編譯再比對，可以讓效能拉到最高

記憶小括號 (capturing group)
() 來記憶你要搜尋的文字內容，根據左小括號出現的順序來決定他的編號，編號從 1 開始。
有時候根據需要，可以用 \ 加上編號來指定被小括號包起來的字串，比如 \1 代表要比對第一組小括號的文字內容，此種語法叫做回朔，英文叫做 back reference
```

練習用正規表示式撈雄中網站的最新消息：

```python3
import re
import ssl
import urllib.request


ssl._create_default_https_context = ssl._create_unverified_context
bot = urllib.request.urlopen('https://www.kshs.kh.edu.tw/view/index.php?WebID=269')
content = bot.read().decode('utf8')

for each_news in re.findall(r'28016.+NowSubId=0">(.+)</a>', content):
    print(each_news)
```

# 程式語言

## C

### 指標

## Python

### 物件導向
