<h2 id="suite-specific-timeouts">Suite specific timeouts</h2>

  Suite-level timeouts may be applied to entire test "suites", or disabled
  via `this.timeout(0)`. This will be inherited by all nested suites and test-cases
  that do not override the value.

    describe('a suite of tests', function(){
      this.timeout(500);

      it('should take less than 500ms', function(done){
        setTimeout(done, 300);
      })

      it('should take less than 500ms as well', function(done){
        setTimeout(done, 200);
      })
    })

<h2 id="suite-specific-timeouts">各スイートごとのタイムアウト</h2>

スイート単位でのタイムアウトを全ての『スイーツ』に設定することも出来ます。`this.timeout(0)`とすると、入れ子になったスイーツ全体に継承され、テストケース側で上書きしていなければ、テストケースそのものにも継承されます。

    describe('a suite of tests', function(){
      this.timeout(500);

      it('should take less than 500ms', function(done){
        setTimeout(done, 300);
      })

      it('should take less than 500ms as well', function(done){
        setTimeout(done, 200);
      })
    })