<h2 id="best-practices">Best practices</h2>

<h2 id="best-practices">ベストプラクティス</h2>

<h3 id="test-directory">test/*</h3>

 By default `mocha(1)` will use the pattern `./test/*.js`, so
 it's usually a good place to put your tests.

<h3 id="test-directory">test/*</h3>

`mocha(1)`はデフォルトでは`./test/*.js`でテスト対象のファイルを指定しているため、テスト対象ファイルは`./test/`に格納することをおすすめします。

<h3 id="makefiles">Makefiles</h3>

Be kind and don't make developers hunt around in your docs to figure
 out how to run the tests, add a `make test` target to your _Makefile_:

     test:
       ./node_modules/.bin/mocha \
         --reporter list

     .PHONY: test

<h3 id="makefiles">メイクファイル</h3>

自分以外のデベロッパがテストを実行するのにドキュメント中を探しまわらなくても済むように、_Makefile_ に`make test`を追加してください:

     test:
       ./node_modules/.bin/mocha \
         --reporter list

     .PHONY: test