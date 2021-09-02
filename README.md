# Auto Paste URL

クリップボードを監視し、URL 文字列が含まれていれば「ダウンロードリンク」を生成するアプリ。シングル HTML ファイルで動作する。


## Demo

__[Enter The Demo Site](https://neos21.github.io/auto-paste-url/)__


## Details

対象 URL をファイルとしてダウンロードしたい時に、ブラウザの「名前を付けてリンク先を保存」を使いたくて作成した。`ime.nu` などを使っても良いのだが URL を組み立てる手間があったのでクリップボードを監視するアプリとした。

クリップボードの監視には Async Clipboard API (`navigator.clipboard.readText()`) を使用している。旧来の `document.execCommand('paste')` は廃止されており動作するブラウザがもうほぼ存在しないため使用していない。

### Bookmarklet

オマケで以下の Bookmarklet を用意した。本アプリで生成するのと同等のダウンロードリンクが作れるモノ。クリップボード監視が不要ならコレでも良いかも。

```javascript
data:text/html,<script>u=prompt('URL?');document.documentElement.innerHTML=`<a href="${u}" target="_blank" rel="noopener noreferrer" download>${u}</a>;`</script>
```

`ime.nu` を使うのであれば以下のような Bookmarklet でも良いだろう。

```javascript
javascript:(()=>{location.href='http://ime.nu/'+location.href})();
javascript:(()=>{window.open('http://ime.nu/'+location.href))();
```


## Links

- [Neo's World](https://neos21.net/)
- [GitHub Pages - auto-paste-url : Auto Paste URL](https://neos21.github.io/auto-paste-url)
