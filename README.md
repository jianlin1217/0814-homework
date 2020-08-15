# 0814-homework

－－作業內容  重新使用上課內容操作一次

作業內容放在0814homework中

1.新增一個資料庫  名稱為news

CREATE DATABASE news DEFAULT CHARACTER SET UTF8

2.建立資料表   
newslist
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

3.