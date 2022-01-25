# テーブル設計

## prototypes テーブル

| Column | Type   | Options     |
| ------ | ------ | ----------- |
| title   | string | null: false |
| catch_copy   | text | null: false |
| concept  | text | null: false |
| users    | references | null: false, foreign_key: true |

### Association

- has_many :messages



## users テーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| name               | string | null: false |
| email              | string | null: false |
| encrypted_password | string | null: false |
| profile              | text| null: false |
| occupation               | text | null: false |
| position               | string | null: false |

### Association

- has_many :messages




## messages テーブル

| Column  | Type       | Options                        |
| ------- | ---------- | ------------------------------ |
| content | string     |                                |
| user    | references | null: false, foreign_key: true |
| ptototype    | references | null: false, foreign_key: true |

### Association

- belongs_to :prototype
- belongs_to :user
