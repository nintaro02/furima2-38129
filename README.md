# README
#DB設計
## users table
|Column               | Type        | Options       |
|---------------------|-------------|---------------|
|nickname             |string       |null:false     |
|email                |string       |null:false     |
|encrypted_password   |string       |null:false     |
|first_name           |string       |null:false     |
|first_name_kana      |string       |null:false     |
|family_name          |string       |null:false     |
|family_name_kana     |string       |null:false     |
|birth_day            |date         |null:false     |

### Association
* has_many :orders

## addresses table
|Column               |Type         |Options                    |
|---------------------|-------------|---------------------------|
|post_code            |string       |null:false                 |
|prefecture_id        |integer      |null:false                 |
|city                 |string       |null:false                 |
|address              |string       |null:false                 |
|building_name        |string       |                           |
|phone_number         |string       |null:false                 |

### Association
* belongs_to :orders

## orders table

|Column               |Type         |Options                    |
|---------------------|-------------|---------------------------|
|user_id              |integer      |null:false                 |
|item_id              |integer      |null:false                 |

### Association
* belongs_to :user
* belongs_to :items

## item table
|Column               |Type         |Options                    |
|---------------------|-------------|---------------------------|
|nickname             |string       |null:false                 |
|price_id             |integer      |null:false                 |
|description          |text         |null:false                 |
|status_id            |integer      |null:false                 |
|shipping_cost_id     |integer      |null:false                 |
|shipping_days_id     |integer      |null:false                 |
|prefecture_id        |integer      |null:false                 |
|category_id          |integer      |null:false,foreign_key:true|
|user_id              |integer      |null:false,foreign_key:true|
### Association
* belongs_to :user

