

## テーブル設計

### users テーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| email              | string | null: false |
| encrypted_password | string | null: false |
| last_name          | string | null: false |
| first_name         | string | null: false |
| last_kana          | string | null: false |
| first_kana         | string | null: false |

#### Association
- has_one  :form
- has_many :clients

### clients テーブル

| Column             | Type       | Options                        |
| ------------------ | ---------- | ------------------------------ |
| last_name          | string     | null: false                    |
| first_name         | string     | null: false                    |
| last_kana          | string     | null: false                    |
| first_kana         | string     | null: false                    |
| email              | string     | null: false                    |
| phone_num          | string     | null: false                    |
| post_num           | string     |                                |
| prefecture         | string     |                                |
| city               | string     |                                |
| details            | string     |                                |
| build_num          | string     |                                |
| birthday           | date       |                                |
| user               | references | null: false, foreign_key: true |

#### Association
- belongs_to :user
- has_one :addinfos
- has_many :tasks

### forms テーブル

| Column             | Type       | Options                        |
| ------------------ | ---------- | ------------------------------ |
| f_name1            | string     |                                |
| f_name2            | string     |                                |
| f_name3            | string     |                                |
| f_name4            | string     |                                |
| f_name5            | string     |                                |
| f_name6            | string     |                                |
| f_name7            | string     |                                |
| f_name8            | string     |                                |
| f_name9            | string     |                                |
| f_name10           | string     |                                |
| user               | references | null: false, foreign_key: true |

#### Association
- belongs_to :user
- has_many :clients

### addinfos テーブル

| Column             | Type       | Options                        |
| ------------------ | ---------- | ------------------------------ |
| add_text1          | string     |                                |
| add_text2          | string     |                                |
| add_text3          | string     |                                |
| add_text4          | string     |                                |
| add_text5          | string     |                                |
| add_text6          | string     |                                |
| add_text7          | string     |                                |
| add_text8          | string     |                                |
| add_text9          | string     |                                |
| add_text10         | string     |                                |
| client             | references | null: false, foreign_key: true |

#### Association
- belongs_to :client

### tasks テーブル

| Column             | Type       | Options                        |
| ------------------ | ---------- | ------------------------------ |
| task               | string     | null: false                    |
| date               | date       | null: false                    |
| redirect           | integer    |                                |
| client             | references | null: false, foreign_key: true |
| user               | references | null: false, foreign_key: true |

#### Association
- belongs_to :client
<br />

ユーザーの必要に応じて情報登録フォームの追加ができる顧客管理アプリです。

(https://github.com/rtm29331/tsk/files/10192655/VSCode.pdf)