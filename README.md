# 下載Mysql
```
https://dev.mysql.com/downloads/installer/
```


# 安裝Mysql
```
C:\Program Files (x86)\MySQL\Samples and Examples 8.0\Sample Databases\World
```


http://tsuozoe.pixnet.net/blog/post/21283890-mysql-%E5%9F%BA%E6%9C%AC%E6%93%8D%E4%BD%9C%E8%AA%9E%E6%B3%95


#
```
Show BATABASES;

use world;

world是mysql內建的範例資料庫
總共有三個資料表(Tables):
[1]City資料表
[2]Country資料表
[3]CountryLanguage資料表

show tables;

DESCRIBE  city;

Select * 
from City;

Select id, NAME
from City;

Select id, NAME
from City
where id=4075;


DESCRIBE Country;

Select * 
from Country;

DESCRIBE  CountryLanguage;

Select * 
from CountryLanguage;
```


#

```
建立資料庫CREATE DATABASE
刪除資料庫DROP DATABASE 


建立資料表CREATE TABLE
刪除資料表DROP TABLE


新增資料

查詢的各種指令

```

#
```
DROP DATABASE IF EXISTS world;

CREATE DATABASE world CHARACTER SET big5;

CHARACTER SET==字元集==


USE world;

--
-- Table structure for table `City`
--

DROP TABLE IF EXISTS `City`;

NOT NULL==不能沒填資料
AUTO_INCREMENT==自動增加
DEFAULT ''==預設是空的
PRIMARY KEY==主鍵

CREATE TABLE `City` (
  `ID` int(11) NOT NULL AUTO_INCREMENT,
  `Name` char(35) NOT NULL DEFAULT '',
  `CountryCode` char(3) NOT NULL DEFAULT '',
  `District` char(20) NOT NULL DEFAULT '',
  `Population` int(11) NOT NULL DEFAULT '0',
  PRIMARY KEY (`ID`)
)ENGINE=MyISAM AUTO_INCREMENT=4080;


INSERT INTO `City` VALUES 
(1,'Kabul','AFG','Kabol',1780000);

--
-- Dumping data for table `City`
--
-- ORDER BY:  `ID`

INSERT INTO `City` VALUES (1,'Kabul','AFG','Kabol',1780000);
INSERT INTO `City` VALUES (2,'Qandahar','AFG','Qandahar',237500);
INSERT INTO `City` VALUES (3,'Herat','AFG','Herat',186800);
INSERT INTO `City` VALUES (4,'Mazar-e-Sharif','AFG','Balkh',127800);
INSERT INTO `City` VALUES (5,'Amsterdam','NLD','Noord-Holland',731200);
INSERT INTO `City` VALUES (6,'Rotterdam','NLD','Zuid-Holland',593321);
INSERT INTO `City` VALUES (7,'Haag','NLD','Zuid-Holland',440900);
INSERT INTO `City` VALUES (8,'Utrecht','NLD','Utrecht',234323);
INSERT INTO `City` VALUES (9,'Eindhoven','NLD','Noord-Brabant',201843);
INSERT INTO `City` VALUES (10,'Tilburg','NLD','Noord-Brabant',193238);
INSERT INTO `City` VALUES (11,'Groningen','NLD','Groningen',172701);
INSERT INTO `City` VALUES (12,'Breda','NLD','Noord-Brabant',160398);
INSERT INTO `City` VALUES (13,'Apeldoorn','NLD','Gelderland',153491);
INSERT INTO `City` VALUES (14,'Nijmegen','NLD','Gelderland',152463);
INSERT INTO `City` VALUES (15,'Enschede','NLD','Overijssel',149544);
INSERT INTO `City` VALUES (16,'Haarlem','NLD','Noord-Holland',148772);
INSERT INTO `City` VALUES (17,'Almere','NLD','Flevoland',142465);
INSERT INTO `City` VALUES (18,'Arnhem','NLD','Gelderland',138020);
INSERT INTO `City` VALUES (19,'Zaanstad','NLD','Noord-Holland',135621);
INSERT INTO `City` VALUES (20,'´s-Hertogenbosch','NLD','Noord-Brabant',129170);
INSERT INTO `City` VALUES (21,'Amersfoort','NLD','Utrecht',126270);
INSERT INTO `City` VALUES (22,'Maastricht','NLD','Limburg',122087);
INSERT INTO `City` VALUES (23,'Dordrecht','NLD','Zuid-Holland',119811);
INSERT INTO `City` VALUES (24,'Leiden','NLD','Zuid-Holland',117196);
INSERT INTO `City` VALUES (25,'Haarlemmermeer','NLD','Noord-Holland',110722);
INSERT INTO `City` VALUES (26,'Zoetermeer','NLD','Zuid-Holland',110214);
INSERT INTO `City` VALUES (27,'Emmen','NLD','Drenthe',105853);
INSERT INTO `City` VALUES (28,'Zwolle','NLD','Overijssel',105819);
INSERT INTO `City` VALUES (29,'Ede','NLD','Gelderland',101574);
INSERT INTO `City` VALUES (30,'Delft','NLD','Zuid-Holland',95268);
INSERT INTO `City` VALUES (31,'Heerlen','NLD','Limburg',95052);
INSERT INTO `City` VALUES (32,'Alkmaar','NLD','Noord-Holland',92713);
INSERT INTO `City` VALUES (33,'Willemstad','ANT','Curaçao',2345);
INSERT INTO `City` VALUES (34,'Tirana','ALB','Tirana',270000);
INSERT INTO `City` VALUES (35,'Alger','DZA','Alger',2168000);

```

  enum('Asia','Europe','North America',
  'Africa','Oceania','Antarctica',
  'South America') NOT NULL DEFAULT 'Asia',

```
DROP TABLE IF EXISTS `Country`;

CREATE TABLE `Country` (
  `Code` char(3) NOT NULL DEFAULT '',
  `Name` char(52) NOT NULL DEFAULT '',
  `Continent` enum('Asia','Europe','North America','Africa','Oceania','Antarctica','South America') NOT NULL DEFAULT 'Asia',
  `Region` char(26) NOT NULL DEFAULT '',
  `SurfaceArea` float(10,2) NOT NULL DEFAULT '0.00',
  `IndepYear` smallint(6) DEFAULT NULL,
  `Population` int(11) NOT NULL DEFAULT '0',
  `LifeExpectancy` float(3,1) DEFAULT NULL,
  `GNP` float(10,2) DEFAULT NULL,
  `GNPOld` float(10,2) DEFAULT NULL,
  `LocalName` char(45) NOT NULL DEFAULT '',
  `GovernmentForm` char(45) NOT NULL DEFAULT '',
  `HeadOfState` char(60) DEFAULT NULL,
  `Capital` int(11) DEFAULT NULL,
  `Code2` char(2) NOT NULL DEFAULT '',
  PRIMARY KEY (`Code`)
) ENGINE=MyISAM;


INSERT INTO `Country` VALUES 
('ABW','Aruba','North America','Caribbean',
193.00,NULL,103000,78.4,828.00,793.00,
'Aruba',
'Nonmetropolitan Territory of The Netherlands',
'Beatrix',129,'AW');



```
# Mysql教科書



```
MySQL新手入門超級手冊-第二版(適用MySQL 8.x與MariaDB 10.x)
作者： 張益裕  出版社：碁峰   出版日期：2018/07/11

http://www.codedata.com.tw/database/mysql-tutorial-getting-started

第1章 資料庫概論與 MySQL
第2章 基礎查詢
第3章 運算式與函式
第4章 結合與合併查詢
第5章 資料維護
第6章 字元集與資料庫
第7章 儲存引擎與資料型態
第8章 表格
第9章 索引
第10章 子查詢
第11章 Views

第12章 Prepared Statements
第13章 Stored Routines 入門
第14章 Stored Routines 的變數與流程
第15章 Stored Routines 進階
第16章 Triggers

第17章 資料庫資訊
第18章 錯誤處理與查詢
第19章 匯入與匯出資料
第20章 效率
附錄 A MariaDB
```
