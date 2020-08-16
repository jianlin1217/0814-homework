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

8.將新增功能套用到新增按鈕中

使用id #newItem 對按鈕做點擊事件的程式
呼叫出對話盒，使用對話盒的id，#newsModal
但此時對話盒會點背景消失
所以需要加上backdrop : static

9.對對話盒做input標籤的讀取
分別有兩個TextField
titleTextBox  以及  ymdTextBox
在點擊確定按鈕後讀取這兩個地方的值
有先用alter()測試資料是否正確
接著使用一變數存成JSON型態
再push到原本的newsList中

10.編輯按鈕操作，呼叫對話盒將值讀取到其中

使用class .editItem來對按鈕事件作操作
再讀取最近li的值來判斷index
將該index的值使用val設定到textBox中

11.測試後與新增按鈕衝突，設定一個判斷變數，並將值正確傳到原本的位置

設定一個變數為 IsNew  等於1時為新增   0為編輯
用if else來作操作
再利用步驟10的index來將值放回原地方

12.將資料庫的資料抓回顯示再上面

抓取失敗
url設定錯誤
url修改成http://localhost/phpmyadmin/db_structure.php?server=1&db=news
也失敗
發現問題惟仍使用XAMPP而非 node.js
且將資料庫改成上課預設的  否則格式會出錯

create database labDB default character set utf8;
use labDB;
create table news
(
  newsId int auto_increment not null primary key,
  ymd char(10),
  title varchar(50)
);
insert into news (ymd, title) values 
  ('2017-05-01', 'News A'),
  ('2017-05-02', 'News B'),
  ('2017-05-03', 'News C'),
  ('2017-05-04', 'News D'),
  ('2017-05-05', 'News E');

用ajax
方法為  get
取得JSON後將資料套到newsList中
刷新將資料顯示在網頁上

13.資料刪除  同時也會刪除到資料庫中的

用ajax
方法為  delete
刪除後
取得JSON後將資料套到newsList中
刷新將資料顯示在網頁上

14.資料編輯

用ajax
方法為 put
編輯後資料傳送到資料庫中
在執行刷新重讀的動作

15.
