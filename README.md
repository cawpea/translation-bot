# Translation Bot

A Slack bot to translate messages between English and Japanese by using Google Cloud Translation API. 
This bot that [takram-design-engineering/translation-bot](https://github.com/takram-design-engineering/translation-bot) based.

- It translate into English if you post Japanese messages.
- It translate into Japanese if you post English messages.
- You can also include emoji.
- If you want not to translate messages, Add exclamation[!] top of messages.

<img src="https://github.com//masaki-ohsumi/translation-bot/blob/master/.doc/image1.png?raw=true" width="520">

## Requirements

- Enable [Google Cloud Translation API](https://cloud.google.com/translate/) and get TRANSLATE_KEY
- [Add a Slack bot](https://slack.com/apps/build/custom-integration)
- Ruby (>= 2.0)

This bot is tested on Ubuntu 16.04.

## Install

    git clone git@github.com:takram-design-engineering/translation-bot.git
    cd translation-bot
    sudo gem install bundler
    bundle install

### Register as a systemd service (optional)

    sudo cp ~/translation-bot/systemd/translation-bot.service /etc/systemd/system/
    sudo systemctl enable translation-bot.service

Reload systemd after editing `/etc/systemd/system/translation-bot.service`.

    sudo systemctl daemon-reload

## Run the server

For development:

    TRANSLATE_KEY=xxxxx SLACK_API_TOKEN=xxxxx bundle exec ruby bot.rb

For systemd:

    sudo systemctl start translation-bot.service

## License

The MIT License  
Copyright (c) 2017 Takram