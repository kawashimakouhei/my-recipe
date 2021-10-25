# テーブル設計

## users テーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| name               | string | null: false |
| email              | string | null: false |
| encrypted_password | string | null: false |
| affiliation        | string | null: false |

## recipes テーブル

| Column | Type       | Options                        |
| ------ | -----------| -------------------------------|
| name   | string     | null: false                    |
| picture| string     | null: false                    |
| user   | references | null: false, foreign_key: true |

## ingredient テーブル

| Column | Type       | Options                        |
| ------ | -----------| -------------------------------|
| name   | string     | null: false                    |


## recipe_ingredients テーブル

| Column      | Type       | Options                        |
| ----------- | ---------- | ------------------------------ |
| recipe      | references | null: false, foreign_key: true |
| ingredient  | references | null: false, foreign_key: true |

## comment テーブル

| Column    | Type       | Options                        |
| --------- | ---------- | ------------------------------ |
| text      | string     |                                |
| user      | references | null: false, foreign_key: true |
| recipe    | references | null: false, foreign_key: true |


## process テーブル

| Column    | Type       | Options                        |
| --------- | ---------- | ------------------------------ |
| text      | text       |                                |
| recipe    | references | null: false, foreign_key: true |
