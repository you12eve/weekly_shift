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

###　データベース設計

## usersテーブル

|Column     |Type   |Options                  |
|nickname   |string |null: false              |
|password   |string |null: false              |

### アソシエーション

has_many :workers
has_many :comments

## workersテーブル
|Column       |Type   |Options                  |
|name         |string |null: false              |
|note(備考)    |string |                         |

belongs_to :user
has_many :comments


## commentテーブル

|Column     |Type   |Options                       |
|tex        |string |null: false                   |
|user_id    |integer|null: false, foreign_key: true|

belongs_to :user
belongs_to :worker
