# carrierwave-dropbox

Forked from [sponee/carrierwave-dropbox](https://github.com/sponee/carrierwave-dropbox), that is a fork from the original gem [robin850/carrierwave-dropbox](https://github.com/robin850/carrierwave-dropbox).

Note: I only made this fork to fix an old project. It solves the uploading of new images. For images created with API v1, I had the file column, that contains the `name: 'example.jpg'`, with the `file_id: 'id:eJMyGwTw12AAGDIEN5AAQ'`).

This gem allows you to easily upload your medias on Dropbox using the awesome
[CarrierWave](https://github.com/carrierwaveuploader/carrierwave) gem.

## Installation

First, you have to create a [Dropbox app](https://www.dropbox.com/developers/apps).
You can either create a "full dropbox" or "app folder" application. Please see
[this wiki](https://github.com/janko-m/paperclip-dropbox/wiki/Access-types) for
further information and gotchas.

Then, add this line to your application's Gemfile:

~~~ruby
gem 'carrierwave-dropbox', git: 'https://github.com/afaundez/carrierwave-dropbox.git'
~~~

Add a initializer with:

~~~ruby
CarrierWave.configure do |config|
  config.dropbox_access_token = ENV["ACCESS_TOKEN"]
end
~~~

Get an `access_token` for your dropbox app by *by pressing the button that says "Generate" in the OAuth 2 section of your app settings page* (see [dropbox oauth-guide](https://www.dropbox.com/developers/reference/oauth-guide)).


Then you can either specify in your uploader:

~~~ruby
class ImageUploader < CarrierWave::Uploader::Base
  storage :dropbox
end
~~~

## License

Please see the `LICENSE` file for further information.
