# Git 管理の手順

user.name と user.email は既に設定してあるとする。

### 1. ディレクトリの作成と git の初期化

```bash
mkdir PersonalSite
cd PersonalSite
git init
```

### 2. リモートリポジトリの作成

事前に GitHub で空の新規リポジトリを作成する。

> [!warning]
> (もし仮に `README.md` を追加してしまったらローカルとリモートの紐づけ後にプルしないと、気付かずに作ったローカルの `README.md` と競合するかも。)

```bash
// リモートリポジトリの在処をoriginに紐づけ、それをremoteとして登録
git remote add origin git@~~~~~~.git
```

### 3. ステージングとコミット

```bash
git add "ファイル名 or ディレクトリ名('.'-> 今いるディレクトリ) or -A(すべてのファイル)"

// コミット
git commit -m "ここに書いた内容をメッセとして指定"
```

ステージングとコミットを同時に行う場合は次も可能

```bash
git commit -am "同上"
```

> [!warning]
> 上記の方法だと管理外のファイルはステージングされないので注意

### 4. プッシュ

以下のように書くことで `local`ブランチを`origin` リポジトリの `remote` ブランチに反映させられる。

```bash
git push origin "local":"remote"
```

> [!tip]
> ブランチ名が`local`と`remote`で同じ時、`remote`側は省略できる。
>
> ```
> git push origin local
> ```

さらに初めのプッシュの際に`push -u`とすると以降は

```bash
git push
```

のみで push 可
