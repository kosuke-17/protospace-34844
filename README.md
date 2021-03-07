# テーブル設計

## users  テーブル

| Colum       | Type    | Options     |
| ----------- | ------- | ----------- |
| email       | string  | null: false |
| password    | string  | null: false |
| name        | string  | null: false |
| profile     | text    | null: false |
| occupation  | text    | null: false |
| position    | text    | null: false |

### Association

- has_many :comments
- has_many :prototypes

## comments  テーブル

| Colum      | Type        | Options     | 
| ---------- | ----------- | ----------- |
| text       | text        | null: false |
| user       | references  |             |
| prototype  | references  |             |

### Association

- belong_to :users
- belong_to :prototypes

## prototypes  テーブル

| colum       | Type                | Option     |
| ----------- | ------------------- | ----------- |
| title       | string              | null: false |
| catch_copy  | text                | null: false |
| concept     | text                | null: false |
| image       |                     |             |
| user        | references          |             |

### Association

- belong_to :users
- has_many :comments

