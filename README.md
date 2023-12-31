# python-practice
Python学習用手順書

## WIP: 環境構築
想定OSはWindowsです（TBD: バージョン）

### 0. 前提：使用するOS
**WSL2 Ubuntu**の想定で手順を記載しています  
（※インストールに管理者権限が必要）  

ターミナルは`Windows Terminal`がおすすめ  
Microsoft Storeからインストール可能

### 1. モジュールのインストール
インストール対象一覧
1. python: 言語。これがないと何もできない
2. python-venv: プロジェクト毎に環境を分けて管理する
3. python-pip: インストールするパッケージの管理
4. git: ファイルのバージョン管理（やる？）

以下コマンドを一つずつ実行
```
# Pythonインストール
sudo apt install python3

# pipインストール
sudo apt install python3-pip

# venvインストール
sudo apt install python3-venv

# gitインストール
sudo apt install git
```

Pythonがインストールされたことを確認
```
python3 --version
git --version
# → Pythonとgitのバージョンが表示されたらOK
```

### 2. エイリアスの設定
`python3`コマンドを`python`コマンドで叩けるようにする

1. 設定ファイルをvimエディタで開く
    ```
    vim ~/.bashrc
    ```

1. `i`キー押下で入力モードにする
1. 末尾に以下を追記
    ```
    # Alias user definitions.
    alias python='python3'
    ```
1. `Esc`キー押下でコマンドモードにする
1. `:wq!`と入力→`Enter`キー押下でファイルを保存して閉じる
1. ターミナルで以下コマンドを叩き、変更した内容を反映する
   ```
   source ~/.bashrc
   ```
1. 反映されたことを確認
   ```
   python --version
   # → Pythonのバージョンが表示されたらOK
   ```

### 3. 作業フォルダを作成
```
cd  # ルートディレクトリに移動
mkdir workspaces  # `workspaces`ディレクトリを作成（名前は任意）
cd workspaces  # `workspaces`ディレクトリに移動
```

### 4. Gitからリポジトリをクローン（やる？）
（モブプロするならコードはGit上で管理できるとやりやすい）
```
git clone {リポジトリのURL}
```

### 5. VSCodeのインストール

以下URLにアクセスし、「Windows」を選択してインストール  
https://code.visualstudio.com/download

### 6. VSCodeの拡張機能のインストール
一括インストール用のスクリプトを用意する予定  
クローンしたリポジトリの中に入っているので叩く  
```
ここにコマンドが入る
```

### 以上

## 仮想環境
### 新規仮想環境の作成
※基本誰かが作ったものに相乗り想定なので、実施することはなさそう

```
python -m venv {仮想環境名}
```

### 仮想環境の起動
```
source {仮想環境名}/bin/activate
```
CLIの先頭に{仮想環境名}が表示されていればOK

### 仮想環境の停止
```
deactivate
```
CLIの先頭に{仮想環境名}が表示されなくなっていればOK

## Pythonプロジェクトの実行
* 単一ファイルの場合
  ```
  python {ファイル名.py}
  ```
  もしくはVSCode右上の▷ボタン押下
* Flaskアプリの場合
  ```
  Under construction
  ```

## 変更内容のGitHubへの反映方法（やるなら）
VSCodeの拡張機能「GitLens」を使う  
*Under construction*