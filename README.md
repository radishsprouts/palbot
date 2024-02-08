# palbot

## 概要
パルワールドサーバーの管理をなるべくディスコードのアプリコマンドで行う事を目的としています。<br>
<br>
・アプリコマンドでサーバーのインストール(SteamCMDにパスが通ってる事が前提)、アンインストール、既にインストールされているサーバーも管理可<br>
・アプリコマンドでサーバーの起動、停止、再起動（サーバーがクラッシュすると自動再起動）<br>
・定期再起動対応、再起動の３０分前、１０分前、５分前、１分前、１０秒前、５秒前から１秒前までカウントダウンがゲーム内に通知<br>
・定期バックアップ機能、アプリコマンドでロールバック<br>
・アプリコマンドでゲームのパラメータの変更ができ、サーバー起動中は次の再起動で自動的に適用<br>
・サーバーごとにプレイヤー一覧を表示（参加退出通知方式ではないので、ディスコード通知が煩雑にならない）<br>
・アプリコマンドからKick/Banする時はSteamIDではなくプレイヤー名一覧から選択できる<br>
・ホワイトリスト対応<br>
・ログインした事のあるプレイヤーをデータベースに記録しているので、アプリコマンドから全プレイヤーのPlayerUIDとSteamIDが確認可<br>
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
config.yml<br>
![rapture_20240206062534](https://github.com/radishsprouts/palbot/assets/3961684/80c63543-e298-4eb5-b4f3-517bd56fcdb4)<br>
<br>
## 使用方法<br>
#### 簡単なコマンド説明（ドキュメント間に合ってません）<br>
##### サーバーのインストール<br>
```/palserver install <server_name>```<br>
<br>
##### サーバーのアンインストール<br>
```/palserver uninstall <server_name>```<br>
<br>
##### インストール済みサーバーの追加<br>
```/palserver add_installed_server <server_name>```<br>
<br>
ボットを起動したら、まず最初にアプリコマンドの/palrcon addserverでサーバーを追加してください。<br>
![rapture_20240206062804](https://github.com/radishsprouts/palbot/assets/3961684/8c059f6f-224b-41c4-9fef-7957b74ba386)<br>
server_name: サーバー名（半角英数字）<br>
host: パルワールドサーバーのアドレス（例えば127.0.0.1）<br>
rcon_port: RCONのポート<br>
rcon_password: PalWorldSettings.iniのAdminPassword<br>
playerlist_channel: プレイヤー一覧を表示するチャンネル（公開用）<br>
whitelist_channel: 新規ログインプレイヤーをホワイトリストに追加するか問い合わせするチャンネル（管理用非公開）<br>
<br>
whitelist_channelを指定すればホワイトリストが有効、指定しなければホワイトリストは無効になります。<br>
<br>
プレイヤーリスト表示機能<br>
![rapture_20240204015357](https://github.com/radishsprouts/palbot/assets/3961684/a6ccb2af-20fc-4672-956d-0f3c267d0905)<br>
<br>
<br>
以下のアプリコマンドが使用できます。<br>
![rapture_20240205230358](https://github.com/radishsprouts/palbot/assets/3961684/ff0cf004-2a79-41a3-a29a-4391a1697aef)<br>
<br>
<br>
ホワイトリストを有効にした場合は、新規プレイヤーがログインした時にホワイトリストに追加するかどうか選択できます。<br>
プレイヤーリストが１０秒ごとに更新されるので、そのタイミングでホワイトリストに追加されていないプレイヤーはキックされます。<br>
![rapture_20240205030333](https://github.com/radishsprouts/palbot/assets/3961684/6e994bfc-8628-414a-a52b-26e031d0fd91)<br>
<br>
プレイヤーリストの更新は１０秒ごとですが、ディスコードに表示されるプレイヤーリストの更新は３０秒ごとになりますので、ご注意お願いします。<br>
