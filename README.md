# infra2
## 1.MriaDBを導入する
##### 以下のサイトを参考にして作成した
##### https://www.digitalocean.com/community/tutorials/how-to-install-mariadb-on-ubuntu-20-04-ja
##### ダウンロード方法
##### sudo apt update
##### sudo apt install mariadb-server
##### sudo mysql_secure_installation
##### sudo mariadb （起動させる）
## 2.MriaDBの基本操作

#### データベース作成
#### MariaDB [(none)]> CREATE DATABASE mysystem;

#### データベース一覧
#### MariaDB [(none)]> show databases;

#### データベース指定
#### use[データベース名]　(今回はmysystem)

#### テーブル作成(一例)
#### CREATE TABLE items(
####  item_id  INTEGER PRIMARY KEY,
####  item_name  VARCHAR(10) NOT NULL,
####  price BIGINT,
####  zaiko INTEGER,
#### created_at DATETIME
#### );

#### テーブルに値の追加 
#### INSERT INTO items
#### VALUES('11', '商品３', 400, 200, '2022-09-10');
#### テーブル中身確認
#### SELECT * FROM items（テーブル名）;
 | item_id | item_name | price | zaiko | created_at          |
 |---------|-----------|-------|-------|---------------------|
 |       9 | 商品2     |   200 |   100 | 2022-09-07 00:00:00 |
 |      11 | 商品3     |   400 |   200 | 2022-09-10 00:00:00 |
 |      12 | 商品２    |   380 |   100 | 2022-09-07 00:00:00 |


#### データ取り出し
#### MariaDB [mysystem]> SELECT item_id,item_name,price
#### -> FROM items
#### -> WHERE item_id=11;

| item_id | item_name | price |
|---------|-----------|-------|
|      11 | 商品3     |   400 |

#### 昇順変更
#### SELECT * FROM items ORDER BY item_id ASC;
#### MariaDB [mysystem]> SELECT * FROM items ORDER BY item_id ASC;
 | item_id | item_name | price | zaiko | created_at          |
 |---------|-----------|-------|-------|---------------------|
 |       9 | 商品2     |   200 |   100 | 2022-09-07 00:00:00 |
 |      11 | 商品3     |   400 |   200 | 2022-09-10 00:00:00 |
 |      12 | 商品２    |   380 |   100 | 2022-09-07 00:00:00 |



#### 降順変更
#### MariaDB [mysystem]> SELECT * FROM items ORDER BY item_id DESC;
 | item_id | item_name | price | zaiko | created_at          |
 |---------|-----------|-------|-------|---------------------|
 |      12 | 商品２    |   380 |   100 | 2022-09-07 00:00:00 |
 |      11 | 商品3     |   400 |   200 | 2022-09-10 00:00:00 |
 |       9 | 商品2     |   200 |   100 | 2022-09-07 00:00:00 |

