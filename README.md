# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false, unique: true|
|name|string|null: false, add_index: true|
### Association
  has_many :group_users
  has_many :groups, though: groups_users
  has_many :messages


groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false, unique: true|
### Association
  has_many :groups_users
  has_many  :messeages
  has_many :users, through: groups_users

groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

messagesテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|
|image|string|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user