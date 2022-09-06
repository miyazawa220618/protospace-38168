# テーブル設計

## users テーブル

| Column             | Type   | Options                      |
| ------------------ | ------ | ---------------------------- |
| email              | string | nill: false,uniqueness: true |
| encrypted_password | string | nill: false                  |
| name               | string | nill: false                  |
| profile            | text   | nill: false                  |
| occupation         | text   | nill: false                  |
| position           | text   | nill: false                  |

### Association

- has_many :prototypes
- has_many :comments

## prototypes テーブル

| Column     | Type       | Options                        |
| ---------- | ---------- | ------------------------------ |
| title      | string     | nill: false                    |
| catch_copy | text       | nill: false                    |
| concept    | string     | nill: false                    |
| user       | references | nill: false, foreign_key: true |

### Association

- has_many :comments
- belongs_to :user

## comments テーブル

| Column    | Type       | Options                        |
| --------- | ---------- | ------------------------------ |
| content   | text       | nill: false                    |
| prototype | references | nill: false, foreign_key: true |
| user      | references | nill: false, foreign_key: true |

### Association

- belongs_to :user
- belongs_to :prototype