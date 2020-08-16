# 0814-homework

－－作業內容  重新使用上課內容操作一次

# 流程的照片放在0814homework中的step_picture

# 預想流程->先建立好資料庫後，再使用前端資料測試，測試完畢之後嘗試抓資料庫資料

1.新增一個資料庫  名稱為news<br>

CREATE DATABASE news DEFAULT CHARACTER SET UTF8

2.建立資料表   newslist<br>
  newsId        //新聞的ID編號  為主鍵  自動增加
  newsDate      //新聞的日期
  newsTitle     //新聞標題
  newsContent   //新聞內容
  newsLink      //新聞連結

 create TABLE newslist
(
	newsId int PRIMARY KEY AUTO_INCREMENT,
    newsDate date DEFAULT null,
    newsTitle varchar(30) DEFAULT "新聞標題",
    newsContent varchar(150),
    newsLink varchar(100)
)

3.新增(五筆)資料進去資料庫，資料皆為測試用<br>
INSERT INTO newslist
(newsDate,newsTitle,newsContent,newsLink)
VALUES
("2020-08-04","Title1","Content1","Link1");<br>
INSERT INTO newslist
(newsDate,newsTitle,newsContent,newsLink)
VALUES
("2020-08-06","Title2","Content2","Link2");<br>
INSERT INTO newslist
(newsDate,newsTitle,newsContent,newsLink)
VALUES
("2020-08-07","Title3","Content3","Link3");<br>
INSERT INTO newslist
(newsDate,newsTitle,newsContent,newsLink)
VALUES
("2020-08-10","Title4","Content4","Link4");<br>
INSERT INTO newslist
(newsDate,newsTitle,newsContent,newsLink)
VALUES
("2020-08-13","Title5","Content5","Link5");

4.複製出前端套版雛形 <br>

複製上課內容的 index_0.html作為作業的index

5.將前端index中預先設好的資料弄到index上顯示<br>

找到ul的id為 "latestNews"
先清空  latestNews的內容
將陣列存到news變數中
alert(news.title);
檢視資料有無錯誤
沒有錯誤的話將資料先串好放到另一字串再使用text()放到li中
並使用addClass()將li套上class  

6.將編輯、刪除按鈕加上去<br>

兩個按鈕的class分別為"editItem"，"deleteItem"
將其標籤及屬性存到一個變數中   
append到剛剛的$li中
再appendTo("latestNews");

7.將刪除功能套用到刪除按鈕中

使用class .deleteItem 對按鈕做點擊事件的程式
需要判定點下刪除按鈕的是哪筆資料
使用this並alert檢查是否判定有誤
//此部分有點問題  在點下deleteItem時有正確判斷到是哪個，但在使用splice刪除後再次點擊按鈕沒有反應
