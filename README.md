# README

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
### Association
- has_many  :users,  through:  :groups_users
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

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|name|string|null: false|
### Association
- has_many  :groups,  through:  :groups_users
- has_many :groups_users
- has_many :messages

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|--------|
|timestamps|----|null: false|
|image|string|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group


    /.Chat
      /%ul.Details
        /%li.Name masa
        /%li.Diary 2020/07/19
      /.Comment おはよう
    /.Log
      /%ul.Log__details
        /%li.Log__name masa
        /%li.Log__diary 2020/07/18
      /.Log__comment 雨とかクソ鬱

            //%input.Form__content{ type: "text", placeholder: "type a message" }


              //%label{class: "input-box__image"}
          //%input.Emptyform{type: "file"}
          //= icon('far', 'image')
    //%input.Send{ type: "submit", name: "commit" , value: "Send"}