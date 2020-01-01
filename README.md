<img src="https://github.com/naru380/node-secret-board/blob/images/posts_page.png">
<br>


# 匿名掲示板
Node.jsの学習で作成した匿名掲示板


## 環境構築手順
### 1. Node.jsとnpmのインストール
まず、Node.jsとnpmをインストールする
```shell-session
sudo apt update
sudo apt install nodejs
sudo apt install npm
```
次に、Node.jsをバージョンアップする
```shell-session
sudo npm cache clean
sudo npm install -g n
sudo n stable
```
ここで、`node -v`でNode.jsのバージョンを確認できるが、<br>
nodeコマンドが見つからない場合は、次のコマンドで修正する
```
sudo apt install nodejs-legacy
```

### 2. データベースの作成
まず、PostgreSQLをインストール
```shell-session
sudo apt install -y postgresql-10
```
次に、postgresユーザーでログインする
```
sudo su - postgres
```
次に、PostgreSQLのCLIを起動して、postgresユーザーのパスワードを変更する
```
psql
alter role postgres with password 'postgres';
```
続けて、データベースを作成する
```
create database secret_board;
```


## 実行方法
```shell-session
npm install
node index.js
```

## ログイン方法
アカウントの管理は`users.htpasswd`で管理を行なっている
<br>
初期で用意してあるアカウントは以下（実際にはパスワードがハッシュ値化されている）

|ユーザー名|パスワード|
|----|----|
|admin|apple|
|guest1|1234|
|guest2|5678|

※ admin は管理者用のアカウント
