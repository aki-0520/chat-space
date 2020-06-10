# DB設計

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|id|integer|null: false|
|email|string|null: false|
|password|string|null: false|
|username|string|null: false|
### Association
- has_many :groups_users
- has_many :messages

## groupsテーブル
Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false|
|group_id|string|null: false|
### Association
- has_many :groups_users
- has_many :messages

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|string|null: false|
|group_id|integer|null: false|
|user_id|integer|null: false|
### Association
- belongs_to :user
- belongs_to :group_user