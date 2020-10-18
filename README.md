# テーブル設計


## users テーブル
| Column     | Type   | Options     |
| --------   | ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |
### Association
- has_many :prototypes
- has_many :comments


## prototypes テーブル
| Column     | Type   | Options     |
| --------   | ------ | ----------- |
| title      | string | null: false |
| catch_copy | text   | null: false |
| concept    | text   | null: false |
| user       | references 型        |
### Association
- belongs_to :user
- has_many :comments


## comments テーブル
| Column     | Type   | Options     |
| --------   | ------ | ----------- |
| text       | text   | null: false |
| user       | references 型        |
| prototype  | references 型        |
### Association
- belongs_to :user
- belongs_to :prototype











## 中間 テーブル 例


| Column | Type       | Options                        |
| ------ | ---------- | ------------------------------ |
| user   | references | null: false, foreign_key: true |
| room   | references | null: false, foreign_key: true |

### Association

- belongs_to :room
- belongs_to :user