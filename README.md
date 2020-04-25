# Minio Client SDK for Ruby [![Slack](https://slack.minio.io/slack?type=svg)](https://slack.minio.io)

The Minio Client SDK for Ruby provides simple APIs to access Minio or any Amazon S3 compatible object storage server.

<blockquote>
The Minio Ruby SDK is work in progress. Please do not use it in development or production.
</blockquote>

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'minio-ruby'
```

And then execute to install the deps.

```
bundle
```

Or install it yourself as:

```
gem install minio-ruby
```

## Usage

### Initialize the client

```
require 'minio'

MinioRuby::Client.configure do |cfg|
  cfg.endpoint = "<minio-server-endpoint>"
  cfg.access_key = "<my-access-key>"
  cfg.secret_key = "<my-secret-key>"
end
client = MinioRuby::Client.new
```

### Interact with the MinIO server

```
# List the buckets
client.list_buckets

# Create new bucket
client.make_bucket "my-bucket-1"

# Check if bucket exists
client.bucket_exists? "my-bucket-1"

# Put object
client.put_object("my-bucket-1", "my-file.txt", File.read("my-object.txt"))

# Get object
client.get_object "my-bucket-1", "my-file.txt"

# remove bucket
client.remove_bucket "my-bucket-1"

```

## Development

To build the minio gem yourself

```sh
bundle exec rake gems:build
```

Install the built gem file.

```sh
gem install minio-0.0.1.gem
```

## Contributing

[Contributors Guide](https://github.com/minio/minio-ruby/blob/master/CONTRIBUTING.md)
