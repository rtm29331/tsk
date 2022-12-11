

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

## 個人制作アプリ 
  ### &emsp;ユーザーの必要に応じて情報登録フォームの追加ができる管理アプリです。



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
<br />


## 本番環境(Render) &emsp;https://
  ### &emsp;&emsp;メールアドレス: rtm29331@gmail.com
  ### &emsp;&emsp;パスワード: 123qwe
<br />

## アイデア
  ### 
   #### &emsp;前職で自分の行動スケジュールの管理を毎週Excelで作っていた事もあり、情報の管理をスムーズにできるようにと思い作成しました。<br>&emsp;<br>&emsp;また必要に応じて自分でフォームを追加してカスタマイズできたり、スタッフとの行動スケジュールも共有できれば思いプラスαで追加実装しました。
  ### ■ターゲット
   #### &emsp;ターゲットは何かしらの顧客を扱う職業の社会人。<br>&emsp;その中でも、顧客ごとに必ず登録しておきたい情報があるが、現在利用している顧客管理アプリにはその情報の入力フォームが無いため、備考欄などに追記する形で対応している人たち。
<br />

## このアプリで得られる体験
  #### &emsp;必要に応じて入力フォームの追加と編集ができます。
  #### &emsp;顧客の詳細ページから直接、次の顧客や前の顧客の詳細ページに遷移できます。
  #### &emsp;トップページにその日のタスクが表示されるので、やらなければならない事がすぐにわかります。
<br />

## 実装を完了した機能
  #### &emsp;(1) サインアップ, サインイン, ログアウト機能(devise)
  #### &emsp;(2) 顧客の新規登録, 編集, 削除, 一覧表示機能での遷移機能
  #### &emsp;(３) タスクの新規登録, 削除機能, 一覧表示機能, その日のタスクをトップページに表示する機能
  #### &emsp;(4) テストの実施（model)<br>&emsp;&emsp;RSpec、factory_bot使用
<br />

## 今後実装予定の機能, 仕様
  #### 追加フォームの新規登録, 編集機能
  #### 追加フォームへの情報登録, 編集機能
  #### 自身の構想の他に、知人,友人,前職の同僚などにこのアプリを使ってもらい、そのフィードバックから得たアイデアも含まれています。
  <!-- #### &emsp;●顧客の検索機能。<br>&emsp;&emsp;→ヘッダー部分に検索フォームを設置予定。名前だけでなく、携帯番号やメールアドレスでも検索ができるように実装。 -->
  <!-- #### &emsp;●各顧客詳細ページにおいて、画像投稿機能。<br>&emsp;&emsp;→画像とその画像のタイトルを保存できるだけでも、接客記録の幅が広がるため。 -->
  #### &emsp;●登録済み顧客一覧の名前表示をクリックすると個人の予定や情報が出るように表示
  #### &emsp;●タスクの横に完了ボタンを表示させ、クリックするとそのタスクを非表示にする仕様。<br>&emsp;&emsp;→残りのタスクを明確にするため、ユーザーのモチベーションに繋げるため。
  #### &emsp;●全タスク一覧画面において、完了済みのタスクにはチェックマークを表示させる仕様。<br>&emsp;&emsp;→全タスクで見たときに、意識しなければならないタスクを明確にするため。
  #### &emsp;●AWSでデプロイの導入
<br />

## 使用言語技術
  #### 言語・フレームワーク<br>&emsp;&emsp;ruby 2.6.5/ rails 6.0.0
  #### フロント<br>&emsp;&emsp;HTML/ CSS/ JavaScript/ 
  #### データベース<br>&emsp;&emsp;MySQL2 0.5.3
  #### テスト<br>&emsp;&emsp;RSpec/ factory_bot
  #### 使用Gem<br>&emsp;&emsp;pry-rails/ devise/ rails-i18n<br>&emsp;&emsp; active_hash/ rubocop<br>&emsp;&emsp;factory_bot_rails/ rspec-rails
<br />

## ER図
![5a46dd5647c8bd895509fdebbc0528ee](https://user-images.githubusercontent.com/115970853/206657951-5d94fae8-0ffc-433e-8e6c-f82fd790f793.png)
<br />