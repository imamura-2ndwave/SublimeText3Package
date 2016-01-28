# Sublime Text 3 Package Install Windows

パッケージのインストールメモ。
Package Controllはインストールされていること。

## 推奨フォント

(Source Han Code JP)[https://github.com/adobe-fonts/source-han-code-jp]

Preferences > Settings - User

{
    "font_face": "SourceHanCodeJP-Normal"
}

## 設定の同期

[packagecontrol/docs/syncing](https://packagecontrol.io/docs/syncing#git)

SavePath: %appdata%\Sublime Text 3\Packages\User

### .gitignore

Package Control.last-run
Package Control.ca-list
Package Control.ca-bundle
Package Control.system-ca-bundle
Package Control.cache/
Package Control.ca-certs/

## 基本設定

Preferences > Settings - User

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

## 推奨ショートカットキー設定 Windows

Preference > Key Bindings - User

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

ファイルのフルパスをコピー: Windows+i

[Sublime Text のサイドバーをhjklキーで移動する](http://m.designbits.jp/14072721/)

## 推奨テーマ

Theme - Cobalt2

Preferences > Settings - User

{
    "color_scheme": "Packages/Theme - Cobalt2/cobalt2.tmTheme",
    "theme": "Cobalt2.sublime-theme"
}

## 構文チェックパッケージ

[SublimeLinter](http://sublimelinter.readthedocs.org/en/latest/index.html)

* 上記プラグインは必須。

### PHP構文チェック

SublimeLinter-php
SublimeLinter-phpcs
SublimeLinter-phpmd

* 上記3つのプラグインをインストール。

#### SublimeLinter-php

PHP構文チェッカー。不正なPHPコードがあれば、エラーを表示してくれる。

#### SublimeLinter-phpcs

PHP構文チェッカー。PSR2などのコーディング規約に違反している箇所を教えてくれる。

> pear upgrade PEAR
> pear install PHP_CodeSniffer
> phpcs --version

* pearからインストール。

> phpcs -i
The installed coding standards are MySource, PEAR, PHPCS, PSR1, PSR2, Squiz and Zend

* 上記のメッセージが出たらインストール成功

#### SublimeLinter-phpmd

PHP構文チェッカー。不必要な変数宣言などの余分なコードや、長すぎる名前･行といった、いわゆるBuggyなコードを指摘してくれる。

> pear channel-discover pear.phpmd.org
> pear channel-discover pear.pdepend.org
> pear install phpmd/PHP_PMD
> phpmd --version

### SCSS構文チェック

#### SublimeLinter-contrib-scss-lint

* 上記プラグインをインストール。

> gem install scss_lint

* Gemのインストール。

### Compass

### TrailingSpaces

行の末尾にあるスペースをハイライトし、保存時に空白を除去するプラグイン。
下記のコードを追記することで、全角空白にも対応。

Preferences > Package Setting > Trailing Spaces > Setting User

{"trailing_spaces_regexp": "[　 \t]+$"}
