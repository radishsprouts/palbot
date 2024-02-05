# palbot

## 概要
パルワールドサーバーのRCON操作をなるべくディスコードのアプリコマンドで行う事を目的としています。<br>
<br>
・サーバーごとにプレイヤー一覧を表示（参加退出通知方式ではないので、ディスコード通知が煩雑にならない）<br>
・アプリコマンドからシャットダウン（再起動）やその他操作が行える（サーバー指定はIPではなく事前に定義したサーバー一覧から選択）<br>
・アプリコマンドからKick/Banする時はSteamIDではなくプレイヤー名一覧から選択できる<br>
・ホワイトリスト対応<br>
・ログインした事のあるプレイヤーを記録しているので、アプリコマンドから全プレイヤーのPlayerUIDとSteamIDが確認可<br>
・ディスコードでの操作なので布団の中からスマホで操作可<br>
<br>
※現在、ShowPlayersがプレイヤーを正しく返さないので、必ずしも全プレイヤーが記録されたり表示されるわけではありません。<br>
パルワールドのサーバープログラムの修正があるまでお待ち下さいますようお願い致します。<br>
<br>
<br>
## 準備
ディスコードボットに必要な権限<br>
![rapture_20240205225606](https://github.com/radishsprouts/palbot/assets/3961684/6223ec36-4a2a-4ff4-a6bf-46116fefd8bc)<br>
<br>
<br>
初回起動時にconfig.ymlが生成されるのでアプリを終了し、ボットトークンやチャンネルIDを書き換えるようお願いします。<br>
config.ymlを書き換えた後、もう１度起動お願いします。<br>
<br>
公開してもいいチャンネル<br>
・DISCORD_CHANNEL_ID_PLAYER_LIST<br>

非公開にするチャンネル（管理用）<br>
・DISCORD_CHANNEL_ID_COMMAND<br>
・DISCORD_CHANNEL_ID_WHITELIST<br>
<br>
config.yml<br>
![rapture_20240205221251](https://github.com/radishsprouts/palbot/assets/3961684/5cd91ba9-0e33-4177-8d90-aa1eff7d5732)<br>
<br>
<br>
## 使用方法
以下のアプリコマンドが使用できます。<br>
![rapture_20240205230358](https://github.com/radishsprouts/palbot/assets/3961684/ff0cf004-2a79-41a3-a29a-4391a1697aef)<br>
<br>
<br>
ホワイトリストを有効にした場合は、新規プレイヤーがログインした時にホワイトリストに追加するかどうか選択できます。<br>
プレイヤーリストが１０秒ごとに更新されるので、そのタイミングでホワイトリストに追加されていないプレイヤーはキックされます。<br>
![rapture_20240205030333](https://github.com/radishsprouts/palbot/assets/3961684/6e994bfc-8628-414a-a52b-26e031d0fd91)<br>
<br>
プレイヤーリストの更新は１０秒ごとですが、ディスコードに表示されるプレイヤーリストの更新は３０秒ごとになりますので、ご注意お願いします。<br>
