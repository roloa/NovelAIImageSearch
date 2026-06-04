# NovelAIImageSearch
search NovelAI images in your folder with prompt metadata.

NovelAIで生成した画像を検索できます。

自分用に作ったものを最低限公開しているだけなので、自己責任・サポート無しでお願いします。

## サンプル

https://roloa.github.io/NovelAIImageSearch/

## 使い方

### 1. Pillowをインストールする

```bash
pip install Pillow
```

### 2. インデックスを作成する

画像をプロジェクトフォルダより下に配置し、次のスクリプトを実行します。

画像フォルダは入れ子になっていても大丈夫です。

```bash
python create_index.py
```

処理が完了すると、検索に使用するindex.jsonが生成されます。

tag_count.jsonも生成されますが、これは今のところ何にも使われません。

### 3. Webサーバーを起動する

このツールはブラウザから利用します。

プロジェクトのルートディレクトリで次のコマンドを実行してください。

```bash
python -m http.server 8000
```

### 4. ブラウザで開く

Webサーバー起動後、ブラウザで以下のURLにアクセスしてください。

```text
http://localhost:8000/
```

検索画面が表示されれば準備完了です。

### 補足

画像を追加・削除した場合は、再度インデックス生成を実行してください。

```bash
python create_index.py
```

## 機能

プロンプトに含まれる単語単位で検索します。

AND検索できます。

-(マイナス)をキーワードの先頭につけてマイナス検索できます。

