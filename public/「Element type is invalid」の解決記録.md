---
title: 「Element type is invalid」の解決記録
tags:
  - 駆け出しエンジニア
private: false
updated_at: "2025-06-28T17:22:57+09:00"
organization_url_name: null
slide: false
ignorePublish: false
---

# はじめに

React 学習中、`npm start`で開発サーバー（localhost:3000）を立ち上げた際、画面に何も表示されなかった。

# 問題

React のコンポーネントを分割して実装した際、コンソールに以下のエラーが出ていて画面が真っ白になりました。

```
Uncaught Error: Element type is invalid: expected a string (for built-in components) or a class/function (for composite components) but got: undefined.
```

どうやら、コンポーネントとして使うべきものが「undefined」になっているときに表示されるようです。

# 解決方法

原因は、**コンポーネントファイル名やエクスポート名・import 名のスペル不一致**でした。  
私の場合「ColorfulMessage」と「ColorfullMessage」が混合しており、統一ミスがありました。  
ファイル名、export、import 文のすべてを`ColorfulMessage`で揃えることで、エラーが解消しました。

# おわりに

React はスペル不一致や大文字小文字のミスにとても厳格らしく、今後はコピペを多用しようと思いました。
同じエラーで悩んでいる方は、まず import/export やファイル名の「スペルミス」をまず確認してみてください。

# 参考

- [Qiita: React の import/export トラブル例](https://qiita.com/search?q=react+import+export)
