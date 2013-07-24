<h2 id="test-specific-timeouts">Test specific timeouts</h2>

  Test-specific timeouts may also be applied, or the use of `this.timeout(0)`
  to disable timeouts all together:

    it('should take less than 500ms', function(done){
      this.timeout(500);
      setTimeout(done, 300);
    })

<h2 id="test-specific-timeouts">各テストごとのタイムアウト</h2>

各テストごとにタイムアウトを設定することも出来ますし、`this.timeout(0)`とすることで、すべてのタイムアウト設定を解除することも出来ます:

    it('should take less than 500ms', function(done){
      this.timeout(500);
      setTimeout(done, 300);
    })
