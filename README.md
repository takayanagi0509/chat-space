#chat-space
#chat-space DB

## users_table
|Column|Type|Options|
|------|----|-------|
|id|integer| |
|email|string|null: false|
|password|string| |
|name|text|null: false, index: true|

### Association
- has_many :messages
- has_many :users_groups_table
- has_many :groups

## groups_table
|Column|Type|Options|
|------|----|-------|
|name|text| |
### Association
-has_many :message
-has_many :users_groups_table
-has_many :users

##messages_table
|Column|Type|Options|
|------|----|-------|
|body|text| |
|imare|string| |
|group_id|integer|null: false, foreign_kewy: true|
|users_id|integer|null: false, foreign_kewy: true|

### Association
-belogs_to group
-belogs_to users


## users_groups_table
|Column|Type|Options|
|------|----|-------|
|users_id|references|null: false,foreign_kye: true|
|text|text|null: false,foreign_kye: true|
|groups_id|references|null: false, foreign_key: true|

### Association

-has_many :message
-belongs_to :group
-belongs_to :usere
