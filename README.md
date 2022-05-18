# README

---
userテーブル

|レコード|型|空かどうか|制約|
|------------------|---   |---     |---       |
|email             |string|NOT NULL|ユニーク制約|
|encrypted_password|string|NOT NULL|          |
|name              |string|NOT NULL|          |
|profile           |text  |NOT NULL|          |
|occupation        |text  |NOT NULL|          |
|position          |text  |NOT NULL|          |

- has_many :prototypes
- has_many :comments

---

prototypesテーブル

|レコード   |型         |空かどうか|制約   |
|----------|---       |---     |---    |
|title     |string    |NOT NULL|       |
|catch_copy|text      |NOT NULL|       |
|concept   |text      |NOT NULL|       |
|user      |references|NOT NULL|外部キー|

- has_many :comments
- belongs_to :user

---

commentsテーブル

|レコード  |型         |空かどうか|制約   |
|---------|---       |---     |---    |
|content  |text      |NOT NULL|       |
|prototype|references|NOT NULL|外部キー|
|user     |references|NOT NULL|外部キー|

- belongs_to :user
- belongs_to :prototype