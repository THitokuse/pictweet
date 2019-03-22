# DB設計

## tweetsテーブル
|Column|Type|Option|
|------|----|------|
|id|integer(11)|null: false, AI|
|text|text||
|user_id|integer(11)|null: false, foreign_key: true|

### Association
- belongs_to :user
- has_many :comments
- has_many :photos

## usersテーブル
|Column|Type|Option|
|------|----|------|
|id|integer(11)|null: false, AI|
|nickname|varchar(255)|null: false|
|email|varchar(255)|null: false|
|password|varchar(255)|null: false|

### Association
- has_many :tweets
- has_many :comments

## commentsテーブル
|Column|Type|Option|
|------|----|------|
|id|integer(11)|null: false, AI|
|text|text||
|user_id|integer(11)|null: false|
|tweet_id|integer(11)|null: false|

### Association
- belongs_to :tweets
- has_many :comments
