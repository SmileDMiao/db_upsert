# DbUpsert
upsert in postgresql and mysql
PG: INSERT ... ON CONFLICT DO UPDATE
Mysql: INSERT ... DUPLICATE KEY UPDATE
This is my practice gem code, the code is simple and there are some else gem does better than this,such as **gem 'upsert'** and **gem 'activerecord-import'**

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'db_upsert'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install db_upsert

## Usage
```ruby
fields = %w(name email city created_at updated_at)
rows = [
 ["smile", '2268571581@qq.com', 'shanghai', '2016-01-01', '2016-01-01'],
 ['malzahar', 'm8023zsm@live.com', 'beijing', '2016-01-01', '2016-01-01'],
]
# mysql
User.bulk_write_mysql(fields, rows, :conflict => [:name])
# posrgresql
User.bulk_write_pg(fields, rows, :conflict => [:name])
```


## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/[USERNAME]/db_upsert. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.


## License

The gem is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).

