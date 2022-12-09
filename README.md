

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


| root | 
![e21bccb6de968b7040384f434d138ce8](https://user-images.githubusercontent.com/115970853/206650343-8dcec689-133f-40a1-aa7e-d8c0a2f47cd4.png)

| 顧客一覧 |
![5f25e08911c6d660161a15291335297c](https://user-images.githubusercontent.com/115970853/206652559-2128ada2-99c2-4eb8-b5ed-92092ebcea9c.png)

| 顧客詳細上部 | 
![5f25e08911c6d660161a15291335297c](https://user-images.githubusercontent.com/115970853/206653516-5829d904-548b-463b-a46a-50cb9ee92e1d.png)

| 顧客詳細下部 |
 ![6b53660fb7ebc073c0945a80747ac657](https://user-images.githubusercontent.com/115970853/206653832-fdac5427-a6e8-4f16-a5fd-3fc61e748042.png)

 | 1週間のタスク一覧＆タスク作成 |
 ![9e782ee55db983c40c14cc0414512bf6](https://user-images.githubusercontent.com/115970853/206654102-a4c205e0-0fc1-4e59-ba1e-01b4c4b4916a.png)

| 全タスク一覧 |
![06ceb7eba73d1298e1a113ba7acff423](https://user-images.githubusercontent.com/115970853/206654408-b98b33c5-dc8e-4765-8074-5da044de94d9.png)



