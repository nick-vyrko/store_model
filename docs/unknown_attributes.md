# Unknown attributes

Sometimes JSON structure changes and it contains more keys than attributes defined in your `StoreModel::Model` class. In such cases, "unknown" attributes can be found inside the `#unknown_attributes` hash:

```ruby
class Configuration
  include StoreModel::Model

  attribute :color, :string
end

configuration = Configuration.new(color: "red", archived: true)
configuration.unknown_attributes # => { "archived" => true }
```
