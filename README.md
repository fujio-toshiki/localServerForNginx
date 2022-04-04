# ローカルサーバー(Nginx)
Dockerを使ったお手軽ローカルサーバー立ち上げツールです。  
ローカルサーバーが用意してないプロジェクトで  
簡易的に表示を確認するときに使用できます。

## 1. Dependencies (事前準備)
- [Docker for Mac](https://docs.docker.com/desktop/mac/install/)

## 2. Docker Command
### 構築、作成、起動
	docker-compose up -d
### コンテナ削除
	docker-compose rm
### DBデータも含めてコンテナ削除
	docker-compose rm -v
### ログ閲覧
	docker-compose logs
### コンテナ一覧
	docker-compose ps
### コンテナのシェルに入る
	docker exec -it {コンテナ名} /bin/bash

## 3. URL
```
http://localhost:8000
```

### ポート番号について
ポート番号は`8000`で設定しております。  
ポート番号を変更したい場合は以下を参考にして変更してください。

#### 変更例
`./docker-compose.yml`7行目を変更することで、ポート番号を変更可能です。

例)  
ポート番号を`8081`に変更する場合
```
- "8080:80"
↓
- "8081:80"
```

## 4. 公開ディレクトリ
公開ディレクトリは`./htdocs/~`で設定しております。  
ポート番号を変更したい場合は以下を参考にして変更してください。

#### 変更例
`docker/nginx/conf.d/default.conf`12行目を変更することで、公開フォルダを変更可能です。

例)  
公開ディレクトリを`./dist/~`に変更する場合
```
root /var/www/html/htdocs;
↓
root /var/www/html/dist;
```




