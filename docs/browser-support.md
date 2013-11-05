<h2 id="browser-support">Browser support</h2>

 Mocha runs in the browser. Every release of Mocha will have new builds of _./mocha.js_ and _./mocha.css_ for use in the browser. To setup Mocha for browser use all you have to do is include the script, stylesheet, tell Mocha which interface you wish to use, and then run the tests. A typical setup might look something like the following, where we call `mocha.setup('bdd')` to use the __BDD__ interface before loading the test scripts, running them `onload` with `mocha.run()`.

    <html>
    <head>
      <meta charset="utf-8">
      <title>Mocha Tests</title>
      <link rel="stylesheet" href="mocha.css" />
    </head>
    <body>
      <div id="mocha"></div>
      <script src="jquery.js"></script>
      <script src="expect.js"></script>
      <script src="mocha.js"></script>
      <script>mocha.setup('bdd')</script>
      <script src="test.array.js"></script>
      <script src="test.object.js"></script>
      <script src="test.xhr.js"></script>
      <script>
        mocha.checkLeaks();
        mocha.globals(['jQuery']);
        mocha.run();
      </script>
    </body>
    </html>

<h3 id="grep-query">grep</h3>

  The client-side may utilize `--grep` as well, however you use the query-string, for example `?grep=api`.

<h2 id="browser-support">ブラウザサポート</h2>

Mochaはブラウザからでも実行することができます。Mochaではリリース毎にブラウザで利用できる、 _./mocha.js_ および、 _./mocha.css_ をビルドします。スクリプトファイルとスタイルシートを読み込み、どのインターフェースを利用するかを設定するだけでMochaをブラウザで利用できます。典型的な設定は以下の様になるでしょう。ここではテストスクリプトが呼び出される前に、`mocha.setup('bdd')` と設定し、__BDD__ インターフェースを利用し、`mocha.run()` で `onload`のタイミングで実行しています。

    <html>
    <head>
      <meta charset="utf-8">
      <title>Mocha Tests</title>
      <link rel="stylesheet" href="mocha.css" />
    </head>
    <body>
      <div id="mocha"></div>
      <script src="jquery.js"></script>
      <script src="expect.js"></script>
      <script src="mocha.js"></script>
      <script>mocha.setup('bdd')</script>
      <script src="test.array.js"></script>
      <script src="test.object.js"></script>
      <script src="test.xhr.js"></script>
      <script>
        mocha.checkLeaks();
        mocha.globals(['jQuery']);
        mocha.run();
      </script>
    </body>
    </html>

<h3 id="grep-query">grep</h3>

クライアントサイドにおいても`--grep`オプションを利用することができますが、この場合、例えば`?grep=api`のようにクエリ・ストリングを利用します。