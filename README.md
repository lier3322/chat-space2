# README

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|groupname|string|null: false|
### Association
- has_many  :users,  through:  :groups_user
- has_many :groups_user

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false|
|group_id|integer|null: false|
### Association
- belongs_to :users
- belongs_to :groups

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|username|string|null: false|
### Association
- has_many  :groups,  through:  :groups_user
- has_many :groups_user
- has_many :comments

## commentsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|timestamps|----|null: false|
|image|string|null: true|
|user_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :users



