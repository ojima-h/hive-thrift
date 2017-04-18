# HiveThriftCli

This is a gem packege of Hive Thrift client library.

The original thrift source is [here](https://github.com/apache/hive/blob/master/service-rpc/if/TCLIService.thrift).

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'hive-thrift-cli'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install hive-thrift-cli

## Development

After checking out the repo, run `bin/setup` to install dependencies. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

### How to build new version

1. Install thrift (>= 0.9.3)

2. Update hive version in `lib/hive_thrift_cli/version`.

3. Compile thrift source:

    ```
    bundle exec rake thrift
    ```

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/ojima-h/hive-thrift-cli.

