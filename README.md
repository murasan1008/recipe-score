# README

# テーブル設計

## users テーブル

| Column            | Type    | Options     |
| ----------------- | ------- | ----------- |
| email             | string  | null: false |
| password          | string  | null: false |
| nickname          | string  | null: false |
| self_introduction | text    |             |

### Association

- has_many :recipes
- has_many :reviews

## recipes テーブル

| Column             | Type       | Options           |
| ------------------ | ---------- | ----------------- |
| name               | string     | null: false       |
| reference          | text       | null: false       |
| user_id            | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- has_many :reviews

## reviews テーブル

| Column     | Type       | Options           |
| ---------- | ---------- | ----------------- |
| content    | text       |                   |
| recipes_id | references | null: false, foreign_key: true |
| user_id    | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- belongs_to :recipe