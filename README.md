## usersテーブル

|Column|Type|Options|
|------|----|-------|
|nickname|string|null: false|
|profile|string||
|email|string|null: false, unique: true|
|password|string|null: false|
|point|integer|null: false|
|goodreputation|integer||
|mediumreputation|integer||
|badreputation|integer||
### Association
- has_many :products
-

## categoriesテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false,unique: true|
### Association
- has_many :products


## Productsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|user_id|references|null:false,foreign_key: true|
|category_id|references|null: false, foreign_key: true|
|brand_id|references|foreign_key: true|
|state_id|references|null: false, foreign_key: true|
|delivfee_id|references|null: false, foreign_key: true|
|delivmethod_id|references|null: false, foreign_key: true|
|delivsource_id|references|null: false, foreign_key: true|
|delivday_id|references|null: false, foreign_key: true|
|price|integer|null: false|
|comment|string||
|Favorite|integer||
### Association
- belongs_to :user
- belongs_to :category
- has_many :comments

## commentsテーブル
|Column|Type|Options|
|------|----|-------|
|text|string||
### Association
- belongs_to :product
