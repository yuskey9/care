
## usersテーブル

| Column             | Type                | Options                 |
|--------------------|---------------------|-------------------------|
| number             | string              | null: false             |
| password           | string              | null: false             |
| name               | string              | null: false             |
| occupation_id      | integer             | null: false             |
| position_id        | integer             | null: false             |



### Association
 - has_many :residents
 - has_many :messages


## residentsテーブル

| Column                 | Type       | Options           |
| ---------------------- | ---------- | ----------------- |
| name                   | string     | null: false       |
| birthday               | integer    | null: false       |
| age                    | integer    | null: false       |
| medical history        | text       | null: false       |
| nursing_care_level_id  | integer    | null: false       |
| food_style_id          | integer    | null: false       |
| excretion_id           | integer    | null: false       |
| bathing_id             | integer    | null: false       |
| walking_state_id       | integer    | null: false       |
| user                   | references | foreign_key: true |



### Association
 - has_many :messages
 - belongs_to :user


## messagesテーブル

| Column      | Type       | Options           |
|-------------|------------|-------------------|
| text        | text       | null: false       |
| resident    | references | foreign_key: true |
| user        | references | foreign_key: true |



### Association

- belongs_to :resident
- belongs_to :user