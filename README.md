# travis-broken-example

An example that will cause a build failure

Testing Travis CI
Testing Slack

## Travis status
[![Build Status](https://travis-ci.org/takenoco82/travis-broken-example.svg?branch=master)](https://travis-ci.org/takenoco82/travis-broken-example)

## Slack連携
``` sh
# gem install travis だとエラーになって面倒なので homebrew でインストール
% brew install travis

# ログイン
% travis login
We need your GitHub login to identify you.
This information will not be sent to Travis CI, only to api.github.com.
The password will not be displayed.

Try running with --github-token or --auto if you don't want to enter your password anyway.

Username: {username}
Password for {username}: ***************
Successfully logged in as {username}!

# 暗号化
% travis encrypt -r {username}/{repository} "{slack workspace}:{token}"
Please add the following to your .travis.yml file:

  secure: "ZRoS...  # これを .travis.yml に貼り付ける

```

コピペするのが面倒な場合、以下の方法でも可能
``` sh
% cd {repository}
% travis encrypt -r {username}/{repository} "{slack workspace}:{token}" --add notifications.slack
```

## 参考
- [ド素人のための Travis CI の使い方 (公式ガイドより) - Qiita](https://qiita.com/YumaInaura/items/8021d38cb202950fb18c)
- [図解: Travis CIの結果をSlack通知する方法 - Qiita](https://qiita.com/nwtgck/items/17840855cb76f60fa1fe)
