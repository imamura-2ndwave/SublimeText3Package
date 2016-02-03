# Sublime Text 3 Package Install Windows

パッケージのインストールメモ。
Package Controllはインストールされていること。

## フォントの導入

日本語表示に配慮されたプログラミング用「Source Han Code」フォントがおすすめです。

[Source Han Code JP](https://github.com/adobe-fonts/source-han-code-jp)

1. [Release](https://github.com/adobe-fonts/source-han-code-jp/tree/release)ブランチから最新バージョンをダウンロードする。
2. OTFフォルダ内のフォントをインストールする。
3. Sublime Textのユーザー設定に追記する。

Preferences > Settings - User

```
{
    "font_face": "SourceHanCodeJP-Normal"
}
```

フォントの太さは好みで変更。

## 設定の同期

[Package Controllの同期方法](https://packagecontrol.io/docs/syncing#git)

Package Controllの保存先: %appdata%\Sublime Text 3\Packages\User  
保存先のディレクトリを合わせてあげれば、不足しているパッケージ等は起動時に自動的にインストールされる。

### .gitignore

```
*.cache
*_tmp
*~
Package Control.last-run
Package Control.ca-list
Package Control.ca-bundle
Package Control.merged-ca-bundle
Package Control.system-ca-bundle
Package Control.user-ca-bundle
Package Control.cache/
Package Control.ca-certs/
```

## 基本設定

Preferences > Settings - User

```
{
    "color_scheme": "Packages/Theme - Cobalt2/cobalt2.tmTheme",
    "default_encoding": "UTF-8",
    "draw_white_space": "all",
    "enable_tab_scrolling": false,
    "fallback_encoding": "UTF-8",
    "fold_buttons": false,
    "font_face": "SourceHanCodeJP-Normal",
    "font_size": 10,
    "highlight_line": true,
    "highlight_modified_tabs": true,
    "ignored_packages":
    [
        "Vintage"
    ],
    "line_padding_top": 4,
    "scroll_speed": 0.1,
    "shift_tab_unindent": true,
    "show_encoding": true,
    "show_line_endings": true,
    "tab_size": 4,
    "theme": "Cobalt2.sublime-theme",
    "translate_tabs_to_spaces": true,
    "trim_trailing_white_space_on_save": true,
    "word_wrap": false
}
```

## 推奨ショートカットキー設定 Windows

Preference > Key Bindings - User

```
[
    // File Full Path Copy to Clipboard
    { "keys": ["super+i"], "command": "copy_path" },
    // Goto-CSS-Declaration
    {
        "keys": ["ctrl+alt+."], "command": "goto_css_declaration",
        "args": {"goto": "next"}
    },
    {
        "keys": ["ctrl+alt+,"],  "command": "goto_css_declaration",
        "args": {"goto": "prev"}
    },
    // RecentActiveFiles
    { "keys": ["ctrl+r"], "command": "recent_active_files" },
]
```

ファイルのフルパスをコピー: Windows+i

[Sublime Text のサイドバーをhjklキーで移動する](http://m.designbits.jp/14072721/)

## 推奨テーマ

Theme - Cobalt2

Preferences > Settings - User

```
{
    "color_scheme": "Packages/Theme - Cobalt2/cobalt2.tmTheme",
    "theme": "Cobalt2.sublime-theme"
}
```

## Node.js インストール

Sublime Textで構文チェックを行うためにNode.jsをインストールする。

[Nodist](https://github.com/marcelklehr/nodist/releases/)

最新リリースのNodistSetup-v0.7.2.exe インストーラをダウンロードします。

### Nodistをインストール

NodistSetup-v0.7.2.exeを実行してインストールします。
次のコマンドを実行してNodistがインストールされたことを確認します。

```
> nodist -v
0.7.2
```

### Nodist依存ファイルのアップデート(Node.jsのインストール)

```
> nodist update
> node -v
v5.4.1
```

Node.js 5.4.1がインストールされました。

### インストール可能なNodeバージョンの確認して、最新のNode.jsをインストール

次のコマンドでインストール可能なNode.jsのバージョンを確認できます。
```
> nodist dist
```

特に指定はないので、最新バージョンをインストールします。

node.jsの最新バージョンのインストール

```
> nodist latest
> node -v
v5.5.0
```

### インストール済みのNode.jsのバージョン一覧表示

次のコマンドでインストール済のNode.jsのバージョン一覧を表示できます。

```
> nodist ls
```

次のコマンドでnpmのバージョンを確認できます。

```
> npm -v
3.5.2
```

### npmを最新バージョンにアップデート

```
> npm update -g npm
> npm -v
3.6.0
```

### npmでphplintをインストール

```
> npm install -g phplint
> phplint -v
1.7.0
```

### npmでeslintをインストール

Javascriptの構文チェックするためにESLintを導入

- [ESLint 最初の一歩](http://qiita.com/mysticatea/items/f523dab04a25f617c87d)
- [時代はESLint。JSLintでもJSHintでもなくESLint。](http://qiita.com/inuscript/items/dcf48f56d8f484c0a1a8)


#### ESLint の特徴

- すべてのルールを自由に on/off できる
- 自分のプロジェクトに合わせたカスタムルールを簡単に作れる
- 豊富なビルトイン ルール (1.0.0 時点で 173 個) に加えて、たくさんのプラグインが公開されている
- ECMAScript 2015 (ES6) をサポートしている
- React の JSX 記法 をサポートしている
- Babel と連携することで、ECMAScript 2016 (ES7) 以降の構文や Flow 型注釈にも対応できる

```
> npm install -g eslint
> eslint -v
v1.10.3
```

## Ruby インストール手順

Sublime Textで構文チェックを行うためにRubyをインストールする。

[Ruby公式](http://rubyinstaller.org/)

インストーラをダウンロードしてインストールする。
次のコマンドを入力してRubyが正常にインストールされたことを確認する。

```
ruby -v
ruby 2.2.3p173 (2015-08-18 revision 51636) [x64-mingw32]
```

### gem アップデート

```
gem update --system
```

### Sass インストール

```
gem install sass
```

### Compass インストール

```
gem install compass
```

### SCSS Lint インストール

```
gem install scss_lint
```

## 構文チェックパッケージ

### SublimeLinter

構文チェックの基本パッケージ。

#### 表示スタイルの変更（お好み）

Tools > SublimeLinter > Mark Style > Outline

### PHP構文チェック

SublimeLinter-php
SublimeLinter-phplint
SublimeLinter-phpcs
SublimeLinter-phpmd

* 上記3つのプラグインをインストール。

#### SublimeLinter-php, SublimeLinter-phplint

PHP構文チェッカー。不正なPHPコードがあれば、エラーを表示してくれる。

#### SublimeLinter-phpcs

PHP構文チェッカー。PSR2などのコーディング規約に違反している箇所を教えてくれる。

```
> pear upgrade PEAR
> pear install PHP_CodeSniffer
> phpcs --version
```

pearからインストール。

> phpcs -i
The installed coding standards are MySource, PEAR, PHPCS, PSR1, PSR2, Squiz and Zend

* 上記のメッセージが出たらインストール成功

#### SublimeLinter-phpmd

PHP構文チェッカー。不必要な変数宣言などの余分なコードや、長すぎる名前･行といった、いわゆるBuggyなコードを指摘してくれる。

```
> pear channel-discover pear.phpmd.org
> pear channel-discover pear.pdepend.org
> pear install phpmd/PHP_PMD
> phpmd --version
```

### Javascript構文チェック

#### SublimeLinter-contrib-eslint

上記プラグインをインストール。
npm導入済み、ESLint導入済み。

### SCSS構文チェック

#### SublimeLinter-contrib-scss-lint

上記プラグインをインストール。
Ruby導入済み、scss_link導入済み。

### TrailingSpaces

行の末尾にあるスペースをハイライトし、保存時に空白を除去するプラグイン。
下記のコードを追記することで、全角空白にも対応。

Preferences > Package Setting > Trailing Spaces > Setting User

```
{"trailing_spaces_regexp": "[　 \t]+$"}
```
