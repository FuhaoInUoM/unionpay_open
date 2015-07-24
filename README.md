# UnionpayOpen

Welcome to your new gem! In this directory, you'll find the files you need to be able to package up your Ruby library into a gem. Put your Ruby code in the file `lib/unionpay_open`. To experiment with that code, run `bin/console` for an interactive prompt.

TODO: Delete this and the text above, and describe your gem

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'unionpay_open'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install unionpay_open

## Usage

```ruby

# 配置
UnionpayOpen.config do |unionpay|
  unionpay.pfx_file = 'tmp/acp.pfx'
  unionpay.pfx_file_password = '000000'
  unionpay.ca_file = 'tmp/acp.cer'
  unionpay.merchant_no = '111111111111111'
end



# 前台交易请求地址
response = UnionpayOpen::Wap.front_trans_req(signMethod: '01',
                                  txnType: '01',
                                  txnSubType: '01',
                                  bizType: '000201',
                                  channelType: '08',
                                  frontUrl: 'http://test.com',
                                  accessType: "0",
                                  orderId: "abcd1qaz",
                                  txnAmt: "10000",
                                  currencyCode: "156")
```

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake rspec` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/[USERNAME]/unionpay_open. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](contributor-covenant.org) code of conduct.

