<h2 id="asynchronous-code">Asynchronous code</h2>

<h2 id="asynchronous-code">非同期で実行されるコード</h2>

Testing asynchronous code with Mocha could not be simpler! Simply invoke the callback when your test is complete. By adding a callback (usually named `done`) to `it()` Mocha will know that it should wait for completion.

非同期で実行されるコードをMochaを使ってテストする場合は、シンプルにはできないでしょう。テストが完了語にコールバックを実行します。`it()`にコールバック（大体`done`と名前がつく）を加える事で、Mochaはその実行完了を待つことが出来ます。

    describe('User', function(){
      describe('#save()', function(){
        it('should save without error', function(done){
          var user = new User('Luna');
          user.save(function(err){
            if (err) throw err;
            done();
          });
        })
      })
    })

 To make things even easier, the `done()` callback accepts an error, so we may use this directly:

 更に完結に記述するために、`done()`コールバックは例外を引数にとることができるので、直接利用するのも良いでしょう。:

    describe('User', function(){
      describe('#save()', function(){
        it('should save without error', function(done){
          var user = new User('Luna');
          user.save(done);
        })
      })
    })

  All "hooks", that is `before()`, `after()`, `beforeEach()`, `afterEach()` may be sync or async as well, behaving much like a regular test-case. For example you may wish to populate database with dummy content before each test:

  テストのフック関数である`before()`、`after()`、`beforeEach()`、`afterEach()`は、同期・非同期の両方で定期的なテストケースとして実行されます。これはテスト毎にデータベースにダミーコンテンツを入れたい場合のサンプルです。:

    describe('Connection', function(){
      var db = new Connection
        , tobi = new User('tobi')
        , loki = new User('loki')
        , jane = new User('jane');

      beforeEach(function(done){
        db.clear(function(err){
          if (err) return done(err);
          db.save([tobi, loki, jane], done);
        });
      })

      describe('#find()', function(){
        it('respond with matching records', function(done){
          db.find({ type: 'User' }, function(err, res){
            if (err) return done(err);
            res.should.have.length(3);
            done();
          })
        })
      })
    })

  You may also pick any file and add "root" level hooks, for example add `beforeEach()` outside of `describe()`s then the callback will run before any test-case regardless of the file its in. This is because Mocha has a root `Suite` with no name.

  ファイルを選んで、例えば`describe()`の外に`beforeEach()`を置くようにルートの位置でフックすることで、コールバックは全てのテストの前に実行されるでしょう。これは、Mochaが無名のルートを持っているためです。

    beforeEach(function(){
      console.log('before every test')
    })
