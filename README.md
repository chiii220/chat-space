# README

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

#### usersテーブル

|Column|Type|Options|
|------|----|-------|
|email|integer|null: false, foreign_key: true|
|password|integer|null: false, foreign_key: true|

##### Association
- has_many :groups: through: :groups_users
- has_many :messages

###### messagesテーブル

|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|


###### Association
- belongs_to :group
- belongs_to :user

###### groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|text||
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

###### Association
- has_many :messages
- has_many :users, through: :groupes_users