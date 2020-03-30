#chat-space
#chat-space DB

## users_table
|Column|Type|Options|
|------|----|-------|
|id|integer| |
|email|string|null: false|
|password|string| |
|name|string|null: false, index: true|

### Association
- has_many :messages
- has_many :users_groups
- has_many :groups, through: :users_groups

## groups_table
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, index: true|
### Association
- has_many :messages
- has_many :users_groups
- has_many :users, through: :users_groups

##messages_table
|Column|Type|Options|
|------|----|-------|
|body|text| |
|imare|string| |
|group_id|integer|null: false, foreign_kewy: true|
|user_id|integer|null: false, foreign_kewy: true|

### Association
-belogs_to group
-belogs_to user

## users_groups_table
|Column|Type|Options|
|------|----|-------|
|user_id|references|null: false,foreign_kye: true|
|group_id|references|null: false, foreign_key: true|

### Association
-belongs_to :group
-belongs_to :user
