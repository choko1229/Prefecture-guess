# Prefecture-guess

「はい」か「いいえ」で答えると、出身都道府県を当てるミニゲームです。

- 最初の2問は、アクセス元のIPから推定した都道府県をランダムな県に混ぜて聞き、「はい→いいえ」と答えたらIPの県に確定します
- 外れたら、人口を重みにしたハフマン木で候補を絞り込みます
- `index.html` 1ファイルで動きます（ビルド不要）
- 結果画面から、当てた県名は出さずに質問数だけをSNSでシェアできます
- 別のサーバーに置くときは `index.html` 内の canonical・og:url・og:image と、`robots.txt`・`sitemap.xml` のURLを差し替えてください

## データ
- 人口: 総務省統計局「令和2年国勢調査 人口等基本集計」
- 地図: 国土地理院「地球地図日本」由来の [jpn-atlas](https://www.npmjs.com/package/jpn-atlas)（BSD-3-Clause）を簡略化して埋め込み
- IP位置情報: ipwho.is / geojs.io / ipapi.co（ブラウザから直接取得）
