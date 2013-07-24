<h2 id="mocha.opts">mocha.opts</h2>

 Mocha will attempt to load `./test/mocha.opts`, these are concatenated with `process.argv`, though command-line args will take precedence. For example suppose you have the following _mocha.opts_ file:

    --require should
    --reporter dot
    --ui bdd

  This will default the reporter to `dot`, require the `should` library,
  and use `bdd` as the interface. With this you may then invoke `mocha(1)`
  with additional arguments, here enabling growl support and changing
  the reporter to `spec`:

    $ mocha --reporter list --growl

<h2 id="mocha.opts">mocha.opts</h2>

Mochaでは`./test/mocha.opts`というファイルから`process.argv`を結合してコマンドを実行することができます。(コマンドライン上の引数が優先される。)例えば、以下の _mocha.opts_ ファイルがあるとします:

    --require should
    --reporter dot
    --ui bdd

この設定では、レポータに`dot`スタイルを利用し、`should`ライブラリをrequireし、そして、インターフェースに`bdd`を利用します。その上で`mocha(1)`に対して追加の引数を渡すこともできます。以下では、growlサポートを追加し、レポータに`list`スタイルを利用します:

    $ mocha --reporter list --growl
