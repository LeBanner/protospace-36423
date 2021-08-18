# README

# テーブル設計

## users テーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| email              | string | NOT NULL    |
| password           | string | NOT NULL    |
| name               | string | NOT NULL    |
| profile            | text   | NOT NULL    |
| occupation         | text   | NOT NULL    |
| position           | text   | NOT NULL    |

### Association

- has_many :comments
- has_many :prototypes


## comments テーブル

| Column   | Type       | Options                       |
| -------- | ---------- | ----------------------------- |
| text     | text       | NOT NULL                      |
| user     | references | null: false,foreign_key: true |
| prototype| references | null: false,foreign_key: true |

### Association

- belongs_to : user
- belongs_to : prototypes



## prototypes テーブル

| Column             | Type       |  Options                       |
| ------------------ | ---------- | -------------------------------|
| title              | string     | NOT NULL                       |
| catch_copy         | string     | NOT NULL                       |
| concept            | string     | NOT NULL                       |
| user               | references | null: false, foreign_key: true |

### Association

belongs_to : user
has_many :comments