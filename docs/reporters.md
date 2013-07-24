<h2 id="reporters">Reporters</h2>

  Mocha reporters adjust to the terminal window,
  and always disable ansi-escape colouring when
  the stdio streams are not associated with a tty.

<h3 id="dot-matrix-reporter">Dot Matrix</h3>

  The "dot" matrix reporter is simply a series of dots
  that represent test cases, failures highlight in red,
  pending in blue, slow as yellow.

   ![dot matrix reporter](images/reporter-dot.png)

<h3 id="spec-reporter">Spec</h3>

  The "spec" reporter outputs a hierarchical view
  nested just as the test cases are.

   ![spec reporter](images/reporter-spec.png)
   ![spec reporter with failure](images/reporter-spec-fail.png)

<h3 id="nyan-reporter">Nyan</h3>

  The "nyan" reporter is exactly what you might expect:

  ![js nyan cat reporter](http://f.cl.ly/items/3f1P1d2U1y1E0K1W1M0m/Screen%20Shot%202012-08-22%20at%203.59.08%20PM.png)

<h3 id="tap-reporter">TAP</h3>

  The TAP reporter emits lines for a [Test-Anything-Protocol](http://en.wikipedia.org/wiki/Test_Anything_Protocol) consumer.

  ![test anything protocol](images/reporter-tap.png)

<h3 id="landing-strip-reporter">Landing Strip</h3>

  The Landing Strip reporter is a gimmicky test reporter simulating
  a plane landing :) unicode ftw

  ![landing strip plane reporter](images/reporter-landing.png)
  ![landing strip with failure](images/reporter-landing-fail.png)

<h3 id="list-reporter">List</h3>

  The "List" reporter outputs a simple specifications list as
  test cases pass or fail, outputting the failure details at
  the bottom of the output.

  ![list reporter](images/reporter-list.png)

<h3 id="progress-reporter">Progress</h3>

  The progress reporter implements a simple progress-bar:

  ![progress bar](images/reporter-progress.png)

<h3 id="json-reporter">JSON</h3>

  The JSON reporter outputs a single large JSON object when
  the tests have completed (failures or not).

  ![json reporter](images/reporter-json.png)

<h3 id="json-stream-reporter">JSON Stream</h3>

  The JSON Stream reporter outputs newline-delimited JSON "events" as they occur, beginning with a "start" event, followed by test passes or failures, and then the final "end" event.

  ![json stream reporter](images/reporter-json-stream.png)

<h3 id="jsoncov-reporter">JSONCov</h3>

  The JSONCov reporter is similar to the JSON reporter, however when run against a library instrumented by [node-jscoverage](https://github.com/visionmedia/node-jscoverage) it will produce coverage output.

<h3 id="htmlcov-reporter">HTMLCov</h3>

  The HTMLCov reporter extends the JSONCov reporter. The library being tested should first be instrumented by [node-jscoverage](https://github.com/visionmedia/node-jscoverage), this allows Mocha to capture the coverage information necessary to produce a single-page HTML report.

  Click to view the current [Express test coverage](coverage.html) report. For an integration example view the mcoha test coverage support [commit](https://github.com/visionmedia/express/commit/b6ee5fafd0d6c79cf7df5560cb324ebee4fe3a7f) for Express.

  ![code coverage reporting](http://f.cl.ly/items/3T3G1h1d3Z2i3M3Y1Y0Y/Screen%20Shot%202012-02-23%20at%208.37.13%20PM.png)

<h3 id="min-reporter">Min</h3>

  The "min" reporter displays the summary only, while still outputting errors
  on failure. This reporter works great with `--watch` as it clears the terminal
  in order to keep your test summary at the top.

  ![](http://f.cl.ly/items/460B2r3p3M3k2D3J250m/Screen%20Shot%202012-03-24%20at%2010.46.01%20AM.png)

<h3 id="doc-reporter">Doc</h3>

 The "doc" reporter outputs a hierarchical HTML body representation
 of your tests, wrap it with a header, footer, some styling and you
 have some fantastic documentation!

  ![doc reporter](images/reporter-doc.png)

 For example suppose you have the following JavaScript:

    describe('Array', function(){
      describe('#indexOf()', function(){
        it('should return -1 when the value is not present', function(){
          [1,2,3].indexOf(5).should.equal(-1);
          [1,2,3].indexOf(0).should.equal(-1);
        })
      })
    })

 The command `mocha --reporter doc array` would yield:

    <section class="suite">
      <h1>Array</h1>
      <dl>
        <section class="suite">
          <h1>#indexOf()</h1>
          <dl>
          <dt>should return -1 when the value is not present</dt>
          <dd><pre><code>[1,2,3].indexOf(5).should.equal(-1);
    [1,2,3].indexOf(0).should.equal(-1);</code></pre></dd>
          </dl>
        </section>
      </dl>
    </section>

  The SuperAgent request library [test documentation](http://visionmedia.github.com/superagent/docs/test.html) was generated with Mocha's doc reporter using this simple make target:

    test-docs:
    	make test REPORTER=doc \
    		| cat docs/head.html - docs/tail.html \
    		> docs/test.html

  View the entire [Makefile](https://github.com/visionmedia/superagent/blob/master/Makefile) for reference.

<h3 id="xunit-reporter">XUnit</h3>

   Documentation needed.

<h3 id="teamcity-reporter">TeamCity</h3>

   Documentation needed.

<h3 id="markdown-reporter">Markdown</h3>

  The "markdown" reporter generates a markdown TOC and body for your
  test suite. This is great if you want to use the tests as documentation
  within a Github wiki page, or a markdown file in the repository that
  Github can render. For example here is the Connect [test output](https://github.com/senchalabs/connect/blob/90a725343c2945aaee637e799b1cd11e065b2bff/tests.md).

<h3 id="html-reporter">HTML</h3>

 The __HTML__ reporter is currently the only browser reporter
 supported by Mocha, and it looks like this:

 ![HTML test reporter](images/reporter-html.png)



<h2 id="reporters">レポータ</h2>

Mochaにおけるレポータはターミナルウィンドウ向けに調整されており、
ttyと関連のないstdioストリームでは常にansi-escapeによるカラーを利用できないようにしてあります。

<h3 id="dot-matrix-reporter">Dot Matrix</h3>

"dot"マトリックスレポータでは、単純に連続するドットをテストケースとし、テストに失敗した場合は赤、ペンディングは青、テスト実行が遅い場合には黄色を使って表示します。

![dot matrix reporter](images/reporter-dot.png)

<h3 id="spec-reporter">Spec</h3>

"spec"レポータはテストケースと同じ階層で結果を表示します。

![spec reporter](images/reporter-spec.png)
![spec reporter with failure](images/reporter-spec-fail.png)

<h3 id="nyan-reporter">Nyan</h3>

"nyan"レポータは(おそらく)想像した通りに結果を表示します。

![js nyan cat reporter](http://f.cl.ly/items/3f1P1d2U1y1E0K1W1M0m/Screen%20Shot%202012-08-22%20at%203.59.08%20PM.png)

<h3 id="tap-reporter">TAP</h3>

TAPレポータは[Test-Anything-Protocol](http://en.wikipedia.org/wiki/Test_Anything_Protocol)を利用するツール用に結果を出力します。

![test anything protocol](images/reporter-tap.png)

<h3 id="landing-strip-reporter">Landing Strip</h3>

Landing Stripレポータは、ギミック的なレポータで飛行機の着陸の様子をシミュレートします :) unicode ftw

![landing strip plane reporter](images/reporter-landing.png)
![landing strip with failure](images/reporter-landing-fail.png)

<h3 id="list-reporter">List</h3>

"List"レポータは、テストケースがパスしたか、失敗したかを使ってシンプルな仕様リストを出力します。また、出力の下にテストケースが失敗した場合の詳細を追記します。

![list reporter](images/reporter-list.png)

<h3 id="progress-reporter">Progress</h3>

Progressレポータはシンプルなプログレスバーを表示します。

![progress bar](images/reporter-progress.png)

<h3 id="json-reporter">JSON</h3>

JSONレポータはテストが完了した際に(失敗でも、成功でも)、1つのJSONオブジェクトを出力します。

![json reporter](images/reporter-json.png)

<h3 id="json-stream-reporter">JSON Stream</h3>

JSON Streamレポータは改行区切りのJSONイベントを発生ベースで出力します。まず、"start"イベントから始まり、テストの成功、あるいは失敗、そして最後に"end"イベントで終わります。

![json stream reporter](images/reporter-json-stream.png)

<h3 id="jsoncov-reporter">JSONCov</h3>

JSONCovレポータはJSONレポータと似ていますが、[node-jscoverage](https://github.com/visionmedia/node-jscoverage)を利用しているライブラリに対して実行すると、カバレッジを出力します。

<h3 id="htmlcov-reporter">HTMLCov</h3>

HTMLCovレポータはJSONCovレポータの拡張で、テスト下にあるライブラリはまず、[node-jscoverage](https://github.com/visionmedia/node-jscoverage)で精査されます。Mocha側でカバレッジに関する情報をキャプチャし、1ページのHTMLレポートを出力することができます。

現時点での[Expressのテストカバレッジはこちらです。](coverage.html)、また、Mochaのテストカバレッジサポートのインテグレーションについての例はExpressへの[コミット](https://github.com/visionmedia/express/commit/b6ee5fafd0d6c79cf7df5560cb324ebee4fe3a7f)を参照してください。

![code coverage reporting](http://f.cl.ly/items/3T3G1h1d3Z2i3M3Y1Y0Y/Screen%20Shot%202012-02-23%20at%208.37.13%20PM.png)

<h3 id="min-reporter">Min</h3>

"min"レポータはテスト失敗時のエラーを出力しつつ、サマリのみを表示します。このレポータはテストサマリを画面上部に固定するためにターミナルをクリアするため、`--watch`オプションと相性がいいです。

![](http://f.cl.ly/items/460B2r3p3M3k2D3J250m/Screen%20Shot%202012-03-24%20at%2010.46.01%20AM.png)

<h3 id="doc-reporter">Doc</h3>

"doc"レポータはテストの階層構造をHTMLとして出力します。ヘッダ、そしてフッタ、スタイルを追加すれば素晴らしいドキュメンテーションになるでしょう!

![doc reporter](images/reporter-doc.png)

例として以下のJavaScriptを見てください:

    describe('Array', function(){
      describe('#indexOf()', function(){
        it('should return -1 when the value is not present', function(){
          [1,2,3].indexOf(5).should.equal(-1);
          [1,2,3].indexOf(0).should.equal(-1);
        })
      })
    })

`mocha --reporter doc array`とすると以下が出力されます:

    <section class="suite">
      <h1>Array</h1>
      <dl>
        <section class="suite">
          <h1>#indexOf()</h1>
          <dl>
          <dt>should return -1 when the value is not present</dt>
          <dd><pre><code>[1,2,3].indexOf(5).should.equal(-1);
    [1,2,3].indexOf(0).should.equal(-1);</code></pre></dd>
          </dl>
        </section>
      </dl>
    </section>

SuperAgentのリクエストライブラリの[テストドキュメント](http://visionmedia.github.com/superagent/docs/test.html)は"doc"レポータを以下の簡単なmakeターゲットにより生成されています:

    test-docs:
    	make test REPORTER=doc \
    		| cat docs/head.html - docs/tail.html \
    		> docs/test.html

こちらの[Makefile](https://github.com/visionmedia/superagent/blob/master/Makefile)を参照してください。

<h3 id="xunit-reporter">XUnit</h3>

要ドキュメンテーション

<h3 id="teamcity-reporter">TeamCity</h3>

要ドキュメンテーション

<h3 id="markdown-reporter">Markdown</h3>

"markdown"レポータはマークダウン形式で目次とテスト・スイーツを生成します。テストをGithub wikiページなど、Githubでマークダウンファイルが自動変換されるページ上で利用するドキュメンテーションとするのに便利です。  
例として、Connectの[テスト出力はこちら](https://github.com/senchalabs/connect/blob/90a725343c2945aaee637e799b1cd11e065b2bff/tests.md)です。

<h3 id="html-reporter">HTML</h3>

__HTML__ レポータは現時点ではMocha内で唯一ブラウザで利用できるレポータです。以下のように表示されます。

![HTML test reporter](images/reporter-html.png)
