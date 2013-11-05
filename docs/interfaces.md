<h2 id="interfaces">Interfaces</h2>

  Mocha "interface" system allows developers to choose their style of DSL. Shipping with __BDD__, __TDD__, and __exports__ flavoured interfaces.

<h3 id="bdd-interface">BDD</h3>

  The "__BDD__" interface provides `describe()`, `it()`, `before()`, `after()`, `beforeEach()`, and `afterEach()`:

    describe('Array', function(){
      before(function(){
        // ...
      });

      describe('#indexOf()', function(){
        it('should return -1 when not present', function(){
          [1,2,3].indexOf(4).should.equal(-1);
        });
      });
    });

<h3 id="tdd-interface">TDD</h3>

  The "__TDD__" interface provides `suite()`, `test()`, `setup()`, and `teardown()`.

    suite('Array', function(){
      setup(function(){
        // ...
      });

      suite('#indexOf()', function(){
        test('should return -1 when not present', function(){
          assert.equal(-1, [1,2,3].indexOf(4));
        });
      });
    });

<h3 id="exports-interface">Exports</h3>

  The "__exports__" interface is much like Mocha's predecessor [expresso](http://github.com/visionmedia/expresso). The keys `before`, `after`, `beforeEach`, and `afterEach` are special-cased, object values
  are suites, and function values are test-cases.

    module.exports = {
      before: function(){
        // ...
      },

      'Array': {
        '#indexOf()': {
          'should return -1 when not present': function(){
            [1,2,3].indexOf(4).should.equal(-1);
          }
        }
      }
    };

<h3 id="qunit-interface">QUnit</h3>

  The qunit-inspired interface matches the "flat" look of QUnit where the test suite title is simply defined before the test-cases.

    function ok(expr, msg) {
      if (!expr) throw new Error(msg);
    }

    suite('Array');

    test('#length', function(){
      var arr = [1,2,3];
      ok(arr.length == 3);
    });

    test('#indexOf()', function(){
      var arr = [1,2,3];
      ok(arr.indexOf(1) == 0);
      ok(arr.indexOf(2) == 1);
      ok(arr.indexOf(3) == 2);
    });

    suite('String');

    test('#length', function(){
      ok('foo'.length == 3);
    });


<h2 id="interfaces">インターフェイス</h2>

開発者がテストに利用するDSLを選択できるよう、Mochaには"インターフェイス"システムがあります。現在、__BDD__ 、__TDD__ そして __exports__ というインターフェイスが用意されています。

<h3 id="bdd-interface">BDD</h3>

"__BDD__" インターフェイスでは`describe()`、`it()`、`before()`、`after()`、`beforeEach()`、`afterEach()`が利用できます:

    describe('Array', function(){
      before(function(){
        // ...
      });

      describe('#indexOf()', function(){
        it('should return -1 when not present', function(){
          [1,2,3].indexOf(4).should.equal(-1);
        });
      });
    });

<h3 id="tdd-interface">TDD</h3>

The "__TDD__" interface provides `suite()`, `test()`, `setup()`, and `teardown()`.

"__TDD__" インターフェイスでは`suite()`、`test()`、`setup()`、そして `teardown()`が利用できます:

    suite('Array', function(){
      setup(function(){
        // ...
      });

      suite('#indexOf()', function(){
        test('should return -1 when not present', function(){
          assert.equal(-1, [1,2,3].indexOf(4));
        });
      });
    });

<h3 id="exports-interface">Exports</h3>

"__exports__" インターフェイスはMochaの前身にあたる[expresso](http://github.com/visionmedia/expresso)で利用していたインターフェイスで、オブジェクトのキー内の`before`、`after`、`beforeEach`、`afterEach`を特殊ケースとして扱い、オブジェクトの値をスイートとして、そして関数をテストケースとして扱います。

    module.exports = {
      before: function(){
        // ...
      },

      'Array': {
        '#indexOf()': {
          'should return -1 when not present': function(){
            [1,2,3].indexOf(4).should.equal(-1);
          }
        }
      }
    };

<h3 id="qunit-interface">QUnit</h3>

QUnitにインスパイアされたインターフェイスはQUnitと同じく、テスト・スイートのタイトルがテストケースの前に定義される"フラット"な見た目をしています:

    function ok(expr, msg) {
      if (!expr) throw new Error(msg);
    }

    suite('Array');

    test('#length', function(){
      var arr = [1,2,3];
      ok(arr.length == 3);
    });

    test('#indexOf()', function(){
      var arr = [1,2,3];
      ok(arr.indexOf(1) == 0);
      ok(arr.indexOf(2) == 1);
      ok(arr.indexOf(3) == 2);
    });

    suite('String');

    test('#length', function(){
      ok('foo'.length == 3);
    });
