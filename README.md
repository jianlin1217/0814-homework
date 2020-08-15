# 0814-homework

－－作業內容  重新使用上課內容操作一次

# 流程的照片放在0814homework中的step_picture

# 預想流程->先建立好資料庫後，再使用前端資料測試，測試完畢之後嘗試抓資料庫資料

1.新增一個資料庫  名稱為news

CREATE DATABASE news DEFAULT CHARACTER SET UTF8

2.建立資料表   newslist
 ---  newsId        //新聞的ID編號  為主鍵  自動增加
 ---  newsDate      //新聞的日期
 ---  newsTitle     //新聞標題
 ---  newsContent   //新聞內容
 ---  newsLink      //新聞連結

 create TABLE newslist
(
	newsId int PRIMARY KEY AUTO_INCREMENT,
    newsDate date DEFAULT null,
    newsTitle varchar(30) DEFAULT "新聞標題",
    newsContent varchar(150),
    newsLink varchar(100)
)

3.新增(五筆)資料進去資料庫，資料皆為測試用
INSERT INTO newslist
(newsDate,newsTitle,newsContent,newsLink)
VALUES
("2020-08-04","Title1","Content1","Link1");
INSERT INTO newslist
(newsDate,newsTitle,newsContent,newsLink)
VALUES
("2020-08-06","Title2","Content2","Link2");
INSERT INTO newslist
(newsDate,newsTitle,newsContent,newsLink)
VALUES
("2020-08-07","Title3","Content3","Link3");
INSERT INTO newslist
(newsDate,newsTitle,newsContent,newsLink)
VALUES
("2020-08-10","Title4","Content4","Link4");
INSERT INTO newslist
(newsDate,newsTitle,newsContent,newsLink)
VALUES
("2020-08-13","Title5","Content5","Link5");

4.複製出前端套版雛形 (上課內容的 index_0.html


