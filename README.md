# Sublime Text 3 Package Windows

(Sublime Text 3)[http://www.sublimetext.com/3]

## Sublime Text 3入門

[“恋に落ちるエディタ”「Sublime Text」 完全入門ガイド！](http://liginc.co.jp/designer/archives/6774)

## Package Controllのインストール

Package Controllの導入は必須です。

コマンドでインストールする

1. View > Console

import urllib.request,os,hashlib; h = '2915d1851351e5ee549c20394736b442' + '8bc59f460fa1548d1514676163dafc88'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)

### エラーの場合

コマンドでインストール場合は手動でインストールする。
[packagecontrol/installation](https://packagecontrol.io/installation#Manual)

1. Preferences > Browse Packages…
2. %appdata%\Sublime Text 3\Installed Packages
3. [Package Control.sublime-package](https://packagecontrol.io/Package%20Control.sublime-package)を配置

## 推奨フォントのインストール

日本語表示に配慮された「Source Han Code」フォントがおすすめです。

### Source Han Code JPの特徴

(Source Han Code JP)[https://github.com/adobe-fonts/source-han-code-jp]

Source Han Code JPの特徴として以下のものが挙げられます。

* ASCII文字は「Source Code Pro」が適用されている。
* それ以外の文字には「源ノ角ゴシック」が適用されている。
* 半角文字と全角文字の横幅の比が 2:3 に調整されている。
* 文字の太さは7種類の中から選べる。
* Adobe社がオープンソースで開発している。

### Source Han Code JPのインストール

1. Latest releaseからSource code (zip)をダウンロードする。
2. WindowsならOTFフォルダのフォントをすべてインストール
3. MacならOTCフォルダのSourceHanCodeJP.ttcをインストール

## 設定の同期

Sublime Textの同期は
Sublime Text 3\Packages\Userの配下をコピーすれば同じ環境になります。
* フォルダをコピーして、起動すれば足りないパッケージは自動的にインストールされ、不要なパッケージはアンインストールされます。

参考：[packagecontrol/docs/syncing](https://packagecontrol.io/docs/syncing#git)

### 設定の同期 Windows

「Windows」ブランチをダウンロードしてください。
保存先: %appdata%\Sublime Text 3\Packages\User

### 設定の同期 Mac

「Mac」ブランチをダウンロードしてください。
保存先:

## 導入パッケージ一覧

Alignment
AlignTab
All Autocomplete
ApacheConf.tmLanguage
AutoFileName
BracketHighlighter
Case Conversion
Color Highlighter
Compass
CSS Format
DocBlockr
Goto-CSS-Declaration
Package Control
PHP-Twig
Pretty JSON
RecentActiveFiles
SCSS
SideBarEnhancements
Sublime Bookmarks
SublimeCodeIntel
SublimeLinter
SublimeLinter-json
SublimeLinter-phpcs
SublimeLinter-phpmd
Sublimerge Pro
Tag
Theme - Cobalt2
TrailingSpaces

## 導入パッケージ一覧 Windows Only

IMESupport

## 導入パッケージ一覧 Mac Only

# 未導入パッケージ

## 日本化対応プラグイン

### Japanize

メニューの日本語化パッケージ

## 文字コード対策プラグイン

### ConvertToUTF8

SublimeTextは標準でShitf JISやEUCなどの日本語のエンコーディングに対応していません。
ファイルを開くタイミングで、UTF-8に変換してファイルの保存タイミングで元の文字コードに戻すプラグインです。

### Codecs33

ConvertToUTF8のバグ(?)問題を解決するプラグイン。
