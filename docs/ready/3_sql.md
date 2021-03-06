# 網頁設計乙級術科題庫分析
(108年度技術士技能檢定-考試速寫版 ver2)

---

## 說明
!>開始作答編寫前，先整理資料庫的建檔(有能力全都編入，時間不夠就不需要)。任何已存在的題目資料都先手動填入mysql，這樣比較易於測試資料庫讀寫。

- 資料庫內的欄位命名沒有特別要求，除了被函式庫固定用的名稱要配合，如id,num這些必須固定 (才能觸發處理)
- 欄位命名技巧上可跟input:type相同方便判斷。譬如input:text，那名字可以取text，為了方便統一文字串都使用text而不使用var_chat
- 每個資料表都需索引，因故新增索引時記得給予AUTO\_INCREMENT

**考場要求的資料庫命名規劃**

1. 建立資料庫名稱 `dbXX`、XX為你的考試座號，透過資料表命名來區分個題目之資料表，舉例q1t3_title代表題組1第3題
2. 如果你抽到某題組，保留該題組之資料表即可，甚至不理會也行。
3. 記得指定**utf8mb4\_unicode\_ci**為預設編碼。

## db01的各項資料表

### 網站標題區
1. 建立q1t3_title，要求4筆
1. 取得01B01~04資料做手動新增，所選圖片搬移到upload
2. dpy只能一個為1，其餘為0

| \#   | 名稱 | 型態      | 編碼與排序           | 屬性     | 空值 | 預設值 | 備註 | 額外資訊        |
| :--- | :--- | :-------- | :------------------- | :------- | :--- | :----- | :--- | :-------------- |
| 1    | id   | int\(10\) |                      | UNSIGNED | 否   | _無_   |      | AUTO\_INCREMENT |
| 2    | img  | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |
| 3    | text | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |
| 4    | dpy  | int\(11\) |                      |          | 否   | _無_   |      |                 |

| id   | img       | text                     | dpy  |
| :--- | :-------- | :----------------------- | :--- |
| 1    | 01B01.jpg | 卓越科技大學校園資訊系統 | 0    |
| 2    | 01B02.jpg | 卓越科技大學校園資訊系統 | 1    |
| 3    | 01B03.jpg | 卓越科技大學校園資訊系統 | 0    |
| 4    | 01B04.jpg | 卓越科技大學校園資訊系統 | 0    |

### 動態文字廣告區(跑馬燈)
1. 建立資料表q1t4_maqe，題目要5筆
2. 從01A02.txt內取得資料做手動新增

| \#   | 名稱 | 型態      | 編碼與排序           | 屬性     | 空值 | 預設值 | 備註 | 額外資訊        |
| :--- | :--- | :-------- | :------------------- | :------- | :--- | :----- | :--- | :-------------- |
| 1    | id   | int\(10\) |                      | UNSIGNED | 否   | _無_   |      | AUTO\_INCREMENT |
| 2    | text | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |
| 3    | dpy  | int\(11\) |                      |          | 否   | _無_   |      |                 |

| id   | text                                                           | dpy  |
| :--- | :------------------------------------------------------------- | :--- |
| 1    | 轉知臺北教育大學與臺灣師大合辦第11屆麋研齋全國硬筆書法比賽活動 | 1    |
| 2    | 轉知:法務部辦理「第五屆法規知識王網路闖關競賽辦法              | 1    |
| 3    | 轉知2012年全國青年水墨創作大賽活動                             | 1    |
| 4    | 欣榮圖書館101年悅讀達人徵文比賽，歡迎全校師生踴躍投稿參加      | 1    |
| 5    | 轉知:教育是人類升沉的樞紐-2013教師生命成長營                   | 1    |

### 動畫圖片輪播區
1. 建立資料表q1t5\_mvim，題目只要求4筆
2. 從img資料夾手動新增有用到的swf與gif之檔名，記得檔案搬移到upload

| \#   | 名稱 | 型態      | 編碼與排序           | 屬性     | 空值 | 預設值 | 備註 | 額外資訊        |
| :--- | :--- | :-------- | :------------------- | :------- | :--- | :----- | :--- | :-------------- |
| 1    | id   | int\(10\) |                      | UNSIGNED | 否   | _無_   |      | AUTO\_INCREMENT |
| 2    | text | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |
| 3    | dpy  | int\(11\) |                      |          | 否   | _無_   |      |                 |

| id   | text      | dpy  |
| :--- | :-------- | :--- |
| 1    | 01C01.swf | 1    |
| 2    | 01C02.swf | 1    |
| 3    | 01C03.swf | 1    |
| 4    | 01C04.swf | 1    |

### 校園映像區
1. 建立資料表q1t6\_img，題目要求四筆
2. 從img資料夾手動新增JPG\(01-10\)之檔名

| \#   | 名稱 | 型態      | 編碼與排序           | 屬性     | 空值 | 預設值 | 備註 | 額外資訊        |
| :--- | :--- | :-------- | :------------------- | :------- | :--- | :----- | :--- | :-------------- |
| 1    | id   | int\(10\) |                      | UNSIGNED | 否   | _無_   |      | AUTO\_INCREMENT |
| 2    | text | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |
| 3    | dpy  | int\(11\) |                      |          | 否   | _無_   |      |                 |

| id   | text      | dpy  |
| :--- | :-------- | :--- |
| 1    | 01D01.jpg | 1    |
| 2    | 01D02.jpg | 1    |
| 3    | 01D03.jpg | 1    |
| 4    | 01D04.jpg | 1    |

### 進佔總人數區
1. 建立資料表q1t7\_total，會有+1的動作這裡用num為名
2. 隨意新增一筆值如555

| \#   | 名稱 | 型態      | 編碼與排序 | 屬性     | 空值 | 預設值 | 備註 | 額外資訊        |
| :--- | :--- | :-------- | :--------- | :------- | :--- | :----- | :--- | :-------------- |
| 1    | id   | int\(10\) |            | UNSIGNED | 否   | _無_   |      | AUTO\_INCREMENT |
| 2    | num  | int\(11\) |            |          | 否   | _無_   |      |                 |

| id   | num  |
| :--- | :--- |
| 1    | 555  |

### 頁尾版權區
1. 建立資料表q1t8\_footer
2. 隨意新增一筆值如 `這裡是頁尾版權資料`

| \#   | 名稱 | 型態      | 編碼與排序           | 屬性     | 空值 | 預設值 | 備註 | 額外資訊        |
| :--- | :--- | :-------- | :------------------- | :------- | :--- | :----- | :--- | :-------------- |
| 1    | id   | int\(10\) |                      | UNSIGNED | 否   | _無_   |      | AUTO\_INCREMENT |
| 2    | text | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |

| id   | text               |
| :--- | :----------------- |
| 1    | 這裡是頁尾版權資料 |


### 最新消息區
1. 建立資料表q1t9\_news，資料有6筆
2. 從01A01.txt手動新增資料

| \#   | 名稱 | 型態      | 編碼與排序           | 屬性     | 空值 | 預設值 | 備註 | 額外資訊        |
| :--- | :--- | :-------- | :------------------- | :------- | :--- | :----- | :--- | :-------------- |
| 1    | id   | int\(10\) |                      | UNSIGNED | 否   | _無_   |      | AUTO\_INCREMENT |
| 2    | text | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |
| 3    | dpy  | int\(11\) |                      |          | 否   | _無_   |      |                 |

| id   | text                                                                                          | dpy  |
| :--- | :-------------------------------------------------------------------------------------------- | :--- |
| 1    | 教師研習「世界公民生命園丁國內研習會」 1.主辦單位：世界展望會 2.研習日期：101年11月1...       | 1    |
| 2    | 公告綜合高中一年級英數補救教學時間 上課日期:10/27.11/3.11/10.11/24共計四次...                 | 1    |
| 3    | 102年全國大專校院運動會 「主題標語及吉祥物命名」 網路票選活動 一、活動期間：自10月25...       | 1    |
| 4    | 台灣亞洲藝術文化教育交流學會第一屆年會國際研討會 活動日期：101年3月3～4日\(六、日\) 活動...   | 1    |
| 5    | 11月23日\(星期五\)將於彰化縣田尾鄉菁芳園休閒農場 舉辦「高中職生涯輔導知能研習」 中區學校每... | 1    |
| 6    | 台視百萬大明星節目辦理海選活動 時間:101年10月27日下午13時 地點:彰化                           | 0    |

### 管理登入按鈕
1. 建立資料表q1t10\_admin，資料1筆
2. 新增資料 **null、admin、1234**

| \#   | 名稱 | 型態      | 編碼與排序           | 屬性 | 空值 | 預設值 | 備註 | 額外資訊        |
| :--- | :--- | :-------- | :------------------- | :--- | :--- | :----- | :--- | :-------------- |
| 1    | id   | int\(11\) |                      |      | 否   | _無_   |      | AUTO\_INCREMENT |
| 2    | acc  | text      | utf8mb4\_unicode\_ci |      | 否   | _無_   |      |                 |
| 3    | pwd  | text      | utf8mb4\_unicode\_ci |      | 否   | _無_   |      |                 |

| id   | acc   | pwd  |
| :--- | :---- | :--- |
| 1    | admin | 1234 |

### 選單管理功能

1. 建立資料表q1t12\_menu，資料3筆
2. 上級為0代表主選單 \(0\)，或某一索引值\(ID\)之次選單
3. 手動新增2筆資料 
   **null、管理登入、login.php、0、1**
   **null、網站首頁、index.php、0、1**
   **null、更多內容、news.php、2、1**

| \#   | 名稱   | 型態      | 編碼與排序           | 屬性     | 空值 | 預設值 | 備註 | 額外資訊        |
| :--- | :----- | :-------- | :------------------- | :------- | :--- | :----- | :--- | :-------------- |
| 1    | id     | int\(10\) |                      | UNSIGNED | 否   | _無_   |      | AUTO\_INCREMENT |
| 2    | text   | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |
| 3    | link   | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |
| 4    | parent | int\(11\) |                      |          | 否   | _無_   |      |                 |
| 5    | dpy    | int\(11\) |                      |          | 否   | _無_   |      |                 |

| id   | text     | link      | parent | dpy  |
| :--- | :------- | :-------- | :----- | :--- |
| 1    | 管理登入 | login.php | 0      | 1    |
| 2    | 網站首頁 | index.php | 0      | 1    |
| 3    | 更多內容 | news.php  | 2      | 1    |


## db02的各項資料表

### 網站標題區

1. 需要紀錄今日瀏覽與累計瀏覽
2. 建立資料表q2t3\_visit

| \#   | 名稱 | 型態      | 編碼與排序 | 屬性     | 空值 | 預設值 | 備註 | 額外資訊        |
| :--- | :--- | :-------- | :--------- | :------- | :--- | :----- | :--- | :-------------- |
| 1    | id   | int\(10\) |            | UNSIGNED | 否   | _無_   |      | AUTO\_INCREMENT |
| 2    | date | date      |            |          | 否   | _無_   |      |                 |
| 3    | num  | int\(11\) |            |          | 否   | _無_   |      |                 |

隨便建立今天的資料

| id   | date       | num  |
| :--- | :--------- | :--- |
| 1    | 2019-10-12 | 100  |

### 會員登入登出

1. 做為會員管理，admin與user做在一起。admin必需id=1
2. 建立資料表q2t6\_user，參考帳密表\(02A08.txt\)
3. 此資料表提供題目6.9.10.15使用

| \#   | 名稱 | 型態      | 編碼與排序           | 屬性     | 空值 | 預設值 | 備註 | 額外資訊        |
| :--- | :--- | :-------- | :------------------- | :------- | :--- | :----- | :--- | :-------------- |
| 1    | id   | int\(10\) |                      | UNSIGNED | 否   | _無_   |      | AUTO\_INCREMENT |
| 2    | acc  | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |
| 3    | pwd  | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |
| 4    | mail | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |

依據題目要求預先塞資料\(02A08.txt\)

| id   | acc   | pwd   | mail               |
| :--- | :---- | :---- | :----------------- |
| 1    | admin | 1234  | admin@labor.gov.tw |
| 2    | test  | 5678  | test@labor.gov.tw  |
| 3    | mem01 | mem01 | mem01@labor.gov.tw |
| 4    | mem02 | mem02 | mem02@labor.gov.tw |

### 主題內容

1. 這裡不是給首頁主題，而是給分類網誌使用。首頁主題用dreamweaver+HTML完成即可
2. 建立資料表 q2t7\_blog，將資料整理近來，cls用數字替代分類網誌。
3. 此題目除了第7題\(分類網誌\)，第11+16題\(最新文章\)、第12題\(人氣文章\)也會用到。只是select的方式不同
4. 總和第7.11.12.16題，欄位會需要分類、標題、內文、讚數、顯示
5. 文章整理起來為：分類\(02A02.txt\)、標題+內文\(02A03~02A06.txt\)，資料只有給四篇，依題目示意圖將內文拆成2篇\(一\)跟\(二\)

| \#   | 名稱  | 型態      | 編碼與排序           | 屬性     | 空值 | 預設值 | 備註 | 額外資訊        |
| :--- | :---- | :-------- | :------------------- | :------- | :--- | :----- | :--- | :-------------- |
| 1    | id    | int\(10\) |                      | UNSIGNED | 否   | _無_   |      | AUTO\_INCREMENT |
| 2    | cls   | int\(11\) |                      |          | 否   | _無_   | 分類 |                 |
| 3    | title | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   | 標題 |                 |
| 4    | text  | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   | 內文 |                 |
| 5    | num   | int\(11\) |                      |          | 否   | _無_   | 讚數 |                 |
| 6    | dpy   | int\(11\) |                      |          | 否   | _無_   | 顯示 |                 |

參考02A02+02A03~02A06.txt，寫入資料庫 \(本解析的示範表格內，此解析教學因字多影響版型，故以...帶過\)

| id   | cls  | title                                               | text                                                                                                    | num  | dpy  |
| :--- | :--- | :-------------------------------------------------- | :------------------------------------------------------------------------------------------------------ | :--- | :--- |
| 1    | 1    | 缺乏運動已成為影響全球死亡率的第四大危險因子 \(一\) | 缺乏運動已成為影響全球死亡率的第四大危險因子-國人無規律運動之比率高達72.2% 資料來源： 行政...           | 1    | 1    |
| 2    | 1    | 缺乏運動已成為影響全球死亡率的第四大危險因子 \(二\) | 許多上班族時常抱怨沒時間或空間運動，國民健康局製作15分鐘「上班族健康操」，不受場地、服裝的限制，每...   | 1    | 1    |
| 3    | 2    | 菸害防治法規 \(一\)                                 | 第二十三條　　違反第五條或第十條第一項規定者，處新臺幣一萬元以上五萬元以下罰鍰，並得按次連續處罰。 ...  | 1    | 1    |
| 4    | 2    | 菸害防治法規 \(二\)                                 | 第二十八條　　違反第十二條第一項規定者，應令其接受戒菸教育；行為人未滿十八歲且未結婚者，並應令其父母... | 1    | 1    |
| 5    | 3    | 降低罹癌風險 建構健康生活型態 \(一\)                | 癌症防治  三管齊下 Part 1 降低罹癌風險建構健康生活型態  撰文：徐文媛　諮詢對象...                       | 1    | 1    |
| 6    | 3    | 降低罹癌風險 建構健康生活型態 \(二\)                | 在推廣動態生活，建立國人運動習慣上，透過訂定國人健康體能指標，調查全國及各縣巿的運動盛行率，並以每年... | 1    | 1    |
| 7    | 4    | 長期憋尿 泌尿系統問題多 \(一\)                      | 資料來源：中央健康保險局雙月刊第98期 上稿日期：2012/08/10 文／游小雯 諮詢／郭育...                      | 1    | 1    |
| 8    | 4    | 長期憋尿 泌尿系統問題多 \(二\)                      | 3、前列腺炎與副睪丸炎： 男性若水份攝取不夠或憋尿使排尿次數過少，細菌就有機會透過尿道引發感染；嚴...     | 1    | 1    |

### 最新文章

1. 題目資料與第7題資料表共用即可。只差在額外的按讚系統
2. 建立資料表q2t11\_good，用來紀錄q2t6\_user與q2t7\_user的關係表
3. 只要有文章與用戶有關連性就新增或刪除資料。

| \#   | 名稱 | 型態      | 編碼與排序           | 屬性     | 空值 | 預設值 | 備註 | 額外資訊        |
| :--- | :--- | :-------- | :------------------- | :------- | :--- | :----- | :--- | :-------------- |
| 1    | id   | int\(10\) |                      | UNSIGNED | 否   | _無_   |      | AUTO\_INCREMENT |
| 2    | user | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |
| 3    | blog | int\(11\) |                      |          | 否   | _無_   |      |                 |

為了快速方便這裡不塞資料，一開始都是沒有成立。需要按讚就insert，不需要就delete

### 問卷調查

1. 顯示問卷內容，可透過登入進行參與投票。
2. 問卷題目分為標題與選項，可以透過parent方式做成同一個table q2t13\_vote
3. 此資料表與13.17題共用

| \#   | 名稱   | 型態      | 編碼與排序           | 屬性     | 空值 | 預設值 | 備註 | 額外資訊        |
| :--- | :----- | :-------- | :------------------- | :------- | :--- | :----- | :--- | :-------------- |
| 1    | id     | int\(10\) |                      | UNSIGNED | 否   | _無_   |      | AUTO\_INCREMENT |
| 2    | text   | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |
| 3    | parent | int\(11\) |                      |          | 否   | _無_   |      |                 |
| 4    | num    | int\(11\) |                      |          | 否   | _無_   |      |                 |

根據02A07.txt先塞好資料

| id   | text                                                                                                    | parent | num  |
| :--- | :------------------------------------------------------------------------------------------------------ | :----- | :--- |
| 1    | 問題一：你最常做什麼運動來促進健康體能呢?                                                               | 0      | 0    |
| 2    | 問題二：二手菸沒有安全劑量，只要有暴露，就會有危險，請問它會造成身體上哪些危害?                         | 0      | 0    |
| 3    | 健走或爬樓梯、慢跑等較不受時間、場地限制的運動。                                                        | 1      | 0    |
| 4    | 仰臥起坐、抬腿及伏地挺身、伸展操、瑜珈等室內運動。                                                      | 1      | 0    |
| 5    | 球類運動、游泳、跳舞、騎腳踏車等加強心肺功能的運動。                                                    | 1      | 0    |
| 6    | 舉重鍛鍊、彈力帶、啞鈴等運用輔助器材鍛鍊肌耐力的運動。                                                  | 1      | 0    |
| 7    | 增加罹患冠狀動脈心臟病及罹病死亡之風險。                                                                | 2      | 0    |
| 8    | 對孩子的的健康會產生許多影響，例如容易咳嗽或打噴嚏、罹患氣喘或讓症狀更嚴重、會因刺激耳咽管，感染中耳... | 2      | 0    |
| 9    | 孕婦吸入二手菸易造成流產、早產、胎盤早期剝離、子宮感染等疾病。                                          | 2      | 0    |
| 10   | 長期的暴露會造成更嚴重的胸腔問題和過敏症，還會增加心臟病和肺癌的罹患率。                                | 2      | 0    |
| 11   | 以上皆是。                                                                                              | 2      | 0    |

## db03的各項資料表

### 網站標題區

後台帳號登入使用admin/1234，由於沒有要求且沒有帳戶管理功能。可以直接用PHP處理不用做SQL

### 預告海報

1. 作為首頁的slider輪播
2. 建立資料表 q3t5\_img

| \#   | 名稱 | 型態      | 編碼與排序           | 屬性     | 空值 | 預設值 | 備註 | 額外資訊        |
| :--- | :--- | :-------- | :------------------- | :------- | :--- | :----- | :--- | :-------------- |
| 1    | id   | int\(10\) |                      | UNSIGNED | 否   | _無_   |      | AUTO\_INCREMENT |
| 2    | text | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |
| 3    | img  | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |
| 4    | odr  | int\(11\) |                      |          | 否   | _無_   |      |                 |
| 5    | dpy  | int\(11\) |                      |          | 否   | _無_   |      |                 |

塞入約9筆資料

| id   | text  | img       | odr  | dpy  |
| :--- | :---- | :-------- | :--- | :--- |
| 1    | 03A01 | 03A01.jpg | 0    | 1    |
| 2    | 03A02 | 03A02.jpg | 0    | 1    |
| 3    | 03A03 | 03A03.jpg | 0    | 1    |
| 4    | 03A04 | 03A04.jpg | 0    | 1    |
| 5    | 03A05 | 03A05.jpg | 0    | 1    |
| 6    | 03A06 | 03A06.jpg | 0    | 1    |
| 7    | 03A07 | 03A07.jpg | 0    | 1    |
| 8    | 03A08 | 03A08.jpg | 0    | 1    |
| 9    | 03A09 | 03A09.jpg | 0    | 1    |

另外還要個資料表儲存特效的參數紀錄，建立q3t5_effect。

| \#   | 名稱 | 型態      | 編碼與排序 | 屬性     | 空值 | 預設值 | 備註 | 額外資訊        |
| :--- | :--- | :-------- | :--------- | :------- | :--- | :----- | :--- | :-------------- |
| 1    | id   | int\(10\) |            | UNSIGNED | 否   | _無_   |      | AUTO\_INCREMENT |
| 2    | once | int\(11\) |            |          | 否   | _無_   |      |                 |

設定內容為1~3都可

| id   | once |
| :--- | :--- |
| 1    | 3    |

### 主題內容

1. 院線片電影資料
2. 建立資料表 q3t7\_movie

| \#   | 名稱   | 型態      | 編碼與排序           | 屬性     | 空值 | 預設值 | 備註 | 額外資訊        |
| :--- | :----- | :-------- | :------------------- | :------- | :--- | :----- | :--- | :-------------- |
| 1    | id     | int\(10\) |                      | UNSIGNED | 否   | _無_   |      | AUTO\_INCREMENT |
| 2    | title  | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |
| 3    | cls    | int\(11\) |                      |          | 否   | _無_   |      |                 |
| 4    | length | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |
| 5    | date   | date      |                      |          | 否   | _無_   |      |                 |
| 6    | corp   | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |
| 7    | maker  | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |
| 8    | video  | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |
| 9    | img    | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |
| 10   | text   | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |
| 11   | odr    | int\(11\) |                      |          | 否   | _無_   |      |                 |
| 12   | dpy    | int\(11\) |                      |          | 否   | _無_   |      |                 |

題目沒有給文字，隨意輸入。

| id   | title     | cls  | length  | date       | corp    | maker | video      | img       | text            | odr  | dpy  |
| :--- | :-------- | :--- | :------ | :--------- | :------ | :---- | :--------- | :-------- | :-------------- | :--- | :--- |
| 1    | 電影名稱A | 1    | 1分30秒 | 2019-04-18 | 發行商A | 導演A | 03B01v.mp4 | 03B01.png | 內容與劇情介紹A | 0    | 1    |
| 2    | 電影名稱B | 2    | 1分30秒 | 2019-04-18 | 發行商B | 導演B | 03B02v.mp4 | 03B02.png | 內容與劇情介紹B | 0    | 1    |
| 3    | 電影名稱C | 3    | 1分30秒 | 2019-04-18 | 發行商C | 導演C | 03B03v.mp4 | 03B03.png | 內容與劇情介紹C | 0    | 1    |
| 4    | 電影名稱D | 4    | 1分30秒 | 2019-04-18 | 發行商D | 導演D | 03B04v.mp4 | 03B04.png | 內容與劇情介紹D | 0    | 1    |
| 5    | 電影名稱E | 1    | 1分30秒 | 2019-04-18 | 發行商E | 導演E | 03B05v.mp4 | 03B05.png | 內容與劇情介紹E | 0    | 1    |
| 6    | 電影名稱F | 2    | 1分30秒 | 2019-04-18 | 發行商F | 導演F | 03B06v.mp4 | 03B06.png | 內容與劇情介紹F | 0    | 1    |

### 訂票管理

1. 訂票資訊，只需要索引、電影ID、訂票日、場次、座位號，購買日
2. 其中座位號為字串型陣列，PHP在處理時要特別轉換處理
3. 建立q3t8\_book

| \#   | 名稱    | 型態      | 編碼與排序           | 屬性     | 空值 | 預設值 | 備註 | 額外資訊        |
| :--- | :------ | :-------- | :------------------- | :------- | :--- | :----- | :--- | :-------------- |
| 1    | id      | int\(10\) |                      | UNSIGNED | 否   | _無_   |      | AUTO\_INCREMENT |
| 2    | movie   | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |
| 3    | date    | date      |                      |          | 否   | _無_   |      |                 |
| 4    | time    | int\(11\) |                      |          | 否   | _無_   |      |                 |
| 5    | seat    | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |
| 6    | buydate | date      |                      |          | 否   | 無     |      |                 |

這裡資料因較複雜\(字串型陣列\)，因故不特別手動輸入。

## db04的各項資料表

### 商品分類

1. 商品有分大分類與中分類，可利用parent來做區分與歸屬關係
2. 建立資料表q4t4\_class

| \#   | 名稱   | 型態      | 編碼與排序           | 屬性 | 空值 | 預設值 | 備註 | 額外資訊        |
| :--- | :----- | :-------- | :------------------- | :--- | :--- | :----- | :--- | :-------------- |
| 1    | id     | int\(11\) |                      |      | 否   | _無_   |      | AUTO\_INCREMENT |
| 2    | title  | text      | utf8mb4\_unicode\_ci |      | 否   | _無_   |      |                 |
| 3    | parent | int\(11\) |                      |      | 否   | _無_   |      |                 |

根據0401.txt手動加入資料

| id   | title        | parent |
| :--- | :----------- | :----- |
| 1    | 流行皮件     | 0      |
| 2    | 流行鞋區     | 0      |
| 3    | 流行飾品     | 0      |
| 4    | 背包         | 0      |
| 5    | 男用皮件     | 1      |
| 6    | 女用皮件     | 1      |
| 7    | 少女鞋區     | 2      |
| 8    | 紳士流行鞋區 | 2      |
| 9    | 時尚手錶     | 3      |
| 10   | 時尚珠寶     | 3      |
| 11   | 背包         | 4      |

### 商品介紹

1. 產品存放的資料表，根據題目要求規劃多組欄位。其中商品編號未特別要求可以省略此動作以索引代替
2. 建立資料表 q4t5\_product

| \#   | 名稱  | 型態      | 編碼與排序           | 屬性 | 空值 | 預設值 | 備註 | 額外資訊        |
| :--- | :---- | :-------- | :------------------- | :--- | :--- | :----- | :--- | :-------------- |
| 1    | id    | int\(11\) |                      |      | 否   | _無_   |      | AUTO\_INCREMENT |
| 2    | cls   | int\(11\) |                      |      | 否   | _無_   |      |                 |
| 3    | title | text      | utf8mb4\_unicode\_ci |      | 否   | _無_   |      |                 |
| 4    | price | int\(11\) |                      |      | 否   | _無_   |      |                 |
| 5    | spec  | text      | utf8mb4\_unicode\_ci |      | 否   | _無_   |      |                 |
| 6    | num   | int\(11\) |                      |      | 否   | _無_   |      |                 |
| 7    | img   | text      | utf8mb4\_unicode\_ci |      | 否   | _無_   |      |                 |
| 8    | text  | text      | utf8mb4\_unicode\_ci |      | 否   | _無_   |      |                 |
| 9    | dpy   | int\(11\) |                      |      | 否   | _無_   |      |                 |

根據0403~0410.txt塞入資料

| id   | cls  | title                  | price | spec   | num  | img      | text                                                                                                 | dpy  |
| :--- | :--- | :--------------------- | :---- | :----- | :--- | :------- | :--------------------------------------------------------------------------------------------------- | :--- |
| 1    | 5    | 工訂製長夾             | 1200  | 全牛皮 | 2    | 0403.jpg | 手工製作長夾卡片層6\*2 鈔票層 \*2 零錢拉鍊層 \*1 採用愛馬仕相同的雙針縫法,皮件堅固耐用...            | 1    |
| 2    | 5    | 兩用式磁扣腰包         | 685   | 中型   | 18   | 0404.jpg | 材質:進口牛皮 顏色:黑色荔枝紋+黑色珠光面皮\(黑色縫線\) 尺寸:15cm\*14cm\(高\)\*6c...                  | 1    |
| 3    | 5    | 超薄設計男士長款真皮   | 800   | L號    | 61   | 0405.jpg | 基本:編織皮革對摺長款零錢包 特色:最潮流最時尚的單品 顏色:黑色珠光面皮\(黑色縫線\) 形狀...            | 1    |
| 4    | 7    | 經典牛皮少女帆船鞋     | 1000  | S號    | 6    | 0406.jpg | 以傳統學院派風格聞名，創始近百年工藝製鞋精神 共用獨家專利氣墊技術，兼具紐約工藝精神，與舒適跑格靈... | 1    |
| 5    | 8    | 經典優雅時尚流行涼鞋   | 2650  | LL     | 8    | 0407.jpg | 優雅流線方型楦頭設計，結合簡潔線條綴飾， 獨特的弧度與曲線美，突顯年輕優雅品味， 是年輕上班族不...    | 1    |
| 6    | 10   | 寵愛天然藍寶女戒       | 28000 | 1克拉  | 1    | 0408.jpg | ◎典雅設計品味款 ◎藍寶為珍貴天然寶石之一，具有保值收藏 ◎專人設計製造，以貴重珠寶精緻鑲工製造          | 1    |
| 7    | 11   | 反折式大容量手提肩背包 | 888   | L號    | 15   | 0409.jpg | 特色:反折式的包口設計,釘釦的裝飾,讓簡單的包型更增添趣味性 材質:棉布 顏色:藍色 尺寸:長...             | 1    |
| 8    | 11   | 男單肩包男             | 650   | 多功能 | 7    | 0410.jpg | 特色:男單肩包/電腦包/公文包/雙肩背包多用途 材質:帆不 顏色:黑色 尺寸:深11cm寬42...                    | 1    |


### 訂單管理

1. 訂單只要能記住會員跟購買資訊，我們能將購買之品項、價格、數量整合為一個陣列\(字串化\)，這樣簡單化
2. 建立資料表 q4t8\_order

| \#   | 名稱  | 型態      | 編碼與排序           | 屬性     | 空值 | 預設值 | 備註               | 額外資訊        |
| :--- | :---- | :-------- | :------------------- | :------- | :--- | :----- | :----------------- | :-------------- |
| 1    | id    | int\(10\) |                      | UNSIGNED | 否   | _無_   |                    | AUTO\_INCREMENT |
| 2    | acc   | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |                    |                 |
| 3    | name  | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |                    |                 |
| 4    | mail  | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |                    |                 |
| 5    | addr  | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |                    |                 |
| 6    | tel   | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |                    |                 |
| 7    | date  | date      |                      |          | 否   | _無_   |                    |                 |
| 8    | buy   | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   | ary\(product+num\) |                 |
| 9    | total | int\(11\) |                      |          | 否   | _無_   |                    |                 |

這裡資料因較複雜\(字串型陣列\)，因故不特別手動輸入。

### 會員管理

1. 依要求規劃會員所需之九項欄位
2. 建立資料表 q4t9\_user

| \#   | 名稱 | 型態      | 編碼與排序           | 屬性     | 空值 | 預設值 | 備註 | 額外資訊        |
| :--- | :--- | :-------- | :------------------- | :------- | :--- | :----- | :--- | :-------------- |
| 1    | id   | int\(10\) |                      | UNSIGNED | 否   | _無_   |      | AUTO\_INCREMENT |
| 2    | acc  | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |
| 3    | pwd  | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |
| 4    | name | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |
| 5    | date | date      |                      |          | 否   | _無_   |      |                 |
| 6    | mail | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |
| 7    | addr | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |
| 8    | tel  | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |

沒有素材，隨便瞎掰一組會員也好

| id   | user | pwd  | name   | date       | mail          | addr      | tel          |
| :--- | :--- | :--- | :----- | :--------- | :------------ | :-------- | :----------- |
| 1    | test | test | 測試01 | 2019-02-21 | test@test.com | test road | 8888-888-888 |

### 管理者

1. 儲存後台管理者資訊，其中會細分五項權限。除了規劃五組欄位，也能使用字串化陣列去紀錄。
2. 建立資料表 q4t10\_admin

| \#   | 名稱   | 型態      | 編碼與排序           | 屬性     | 空值 | 預設值 | 備註 | 額外資訊        |
| :--- | :----- | :-------- | :------------------- | :------- | :--- | :----- | :--- | :-------------- |
| 1    | id     | int\(10\) |                      | UNSIGNED | 否   | _無_   |      | AUTO\_INCREMENT |
| 2    | user   | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |
| 3    | pwd    | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |
| 4    | access | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |

這裡需輸入admin/1234並權限全給。可以先設計測試用的str.php放在根目錄下執行取得編碼後的字串。1代表有0代表沒有

```php
<?php
for($i=0;$i<5;$i++) $ary[$i]=1;
echo serialize($ary);
?>
```

取得`a:5:{i:0;i:1;i:1;i:1;i:2;i:1;i:3;i:1;i:4;i:1;}`，建立預設管理者

| id   | user  | pwd  | access                                            |
| :--- | :---- | :--- | :------------------------------------------------ |
| 1    | admin | 1234 | `a:5:{i:0;i:1;i:1;i:1;i:2;i:1;i:3;i:1;i:4;i:1;}` |

### 頁尾版權區
1. 建立資料表q4t11\_footer
2. 隨意新增一筆值如 `這裡是頁尾版權資料`

| \#   | 名稱 | 型態      | 編碼與排序           | 屬性     | 空值 | 預設值 | 備註 | 額外資訊        |
| :--- | :--- | :-------- | :------------------- | :------- | :--- | :----- | :--- | :-------------- |
| 1    | id   | int\(10\) |                      | UNSIGNED | 否   | _無_   |      | AUTO\_INCREMENT |
| 2    | text | text      | utf8mb4\_unicode\_ci |          | 否   | _無_   |      |                 |

| id   | text               |
| :--- | :----------------- |
| 1    | 這裡是頁尾版權資料 |


