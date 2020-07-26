## このアプリについて
- タスク管理アプリ
  - 予め管理画面でタスクを登録
  - ユーザを作成したときに管理画面で登録されたタスクが自動で新規ユーザに表示される

## インストール方法

### 仮想環境の用意
```
brew pyenv install
brew pipenv install
vi ~/.zshrc
-----
# 下記をファイルに追記
export PYENV_ROOT="$HOME/.pyenv"
export PATH="$PYENV_ROOT/bin:$PATH"
-----

# 3.8系の任意のpythonをインストール
pyenv install 3.8.5
```

### このアプリのインストール

```
# インストールしたいディレクトリに移動(下記はホームディレクトリに移動)
cd ~

# このリポジトリをインストール
git clone https://github.com/sheep333/django-taskproj.git

# 仮想環境を有効にする
pipenv shell

# migrateを実行してDBにテーブルを作成し、アプリを立ち上げる
cd taskproj
python manage.py migrate
python manage.py runserver
```

### アプリの確認

```
# 管理ユーザの作成
python manage.py createsuperuser

# 管理画面からタスクデータの作成
python manage.py runserver

# 下記URLに接続してcreatesuperuserでログイン
# CategorysとTasksにデータを追加
http://127.0.0.1:8000/admin/

# 下記画面で「会員登録」から会員を作成
# ターミナルに表示されるメールアドレスのリンクをクリックして
# 本登録を行ってログイン
http://127.0.0.1:8000/login/

# 作成したタスクが画面に表示されていることを確認
```
