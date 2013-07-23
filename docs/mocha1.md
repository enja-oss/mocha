<h2 id="usage">mocha(1)</h2>


    Usage: mocha [debug] [options] [files]

    Commands:

      init <path>
      initialize a client-side mocha setup at <path>

    Options:

      -h, --help                      output usage information
      -V, --version                   output the version number
      -r, --require <name>            require the given module
      -R, --reporter <name>           specify the reporter to use
      -u, --ui <name>                 specify user-interface (bdd|tdd|exports)
      -g, --grep <pattern>            only run tests matching <pattern>
      -i, --invert                    inverts --grep matches
      -t, --timeout <ms>              set test-case timeout in milliseconds [2000]
      -s, --slow <ms>                 "slow" test threshold in milliseconds [75]
      -w, --watch                     watch files for changes
      -c, --colors                    force enabling of colors
      -C, --no-colors                 force disabling of colors
      -G, --growl                     enable growl notification support
      -d, --debug                     enable node's debugger, synonym for node --debug
      -b, --bail                      bail after first test failure
      -A, --async-only                force all tests to take a callback (async)
      --recursive                     include sub directories
      --debug-brk                     enable node's debugger breaking on the first line
      --globals <names>               allow the given comma-delimited global [names]
      --check-leaks                   check for global variable leaks
      --interfaces                    display available interfaces
      --reporters                     display available reporters
      --compilers <ext>:<module>,...  use the given module(s) to compile files

<h3 id="watch-option">-w, --watch</h3>

  Executes tests on changes to JavaScript in the CWD, and once initially.

<h3 id="compilers-option">--compilers</h3>

  coffee-script is no longer supported out of the box. CS and similar transpilers
  may be used by mapping the file extensions (for use with --watch) and the module
  name. For example `--compilers coffee:coffee-script`.

<h3 id="bail-option">-b, --bail</h3>

  Only interested in the first exception? use `--bail` !

<h3 id="debug-option">-d, --debug</h3>

  Enables node's debugger support, this executes your script(s) with `node debug <file ...>` allowing you to step through code and break with the __debugger__ statement.

<h3 id="globals-option">--globals &lt;names&gt;</h3>

  Accepts a comma-delimited list of accepted global variable names. For example suppose your app deliberately exposes a global named `app` and `YUI`, you may want to add `--globals app,YUI`.

<h3 id="ignore-leaks-option">--check-leaks</h3>

  By default Mocha will not check for global variables leaked while running tests, to enable this pass `--check-leaks`, to specify globals that are acceptable use `--globals`, for example `--globals jQuery,MyLib`.

<h3 id="require-option">-r, --require &lt;name&gt;</h3>

  The `--require` option is useful for libraries such as [should.js](http://github.com/visionmedia/should.js), so you may simply `--require should` instead of manually invoking `require('should')` within each test file. Note that this works well for `should` as it augments `Object.prototype`, however if you wish to access a module's exports you will have to require them, for example `var should = require('should')`.

<h3 id="ui-option">-u, --ui &lt;name&gt;</h3>

  The `--ui` option lets you specify the interface to use, defaulting to "bdd".

<h3 id="reporter-option">-R, --reporter &lt;name&gt;</h3>

  The `--reporter` option allows you to specify the reporter that will be used, defaulting to "dot". This flag may also be used to utilize third-party reporters. For example if you `npm install mocha-lcov-reporter` you may then do `--reporter mocha-lcov-reporter`.

<h3 id="timeout-option">-t, --timeout &lt;ms&gt;</h3>

  Specifies the test-case timeout, defaulting to 2 seconds. To override you may pass the timeout in milliseconds, or a value with the `s` suffix, ex: `--timeout 2s` or `--timeout 2000` would be equivalent.

<h3 id="slow-option">-s, --slow &lt;ms&gt;</h3>

  Specify the "slow" test threshold, defaulting to 75ms. Mocha uses this to highlight test-cases that are taking too long.

<h3 id="grep-option">-g, --grep &lt;pattern&gt;</h3>

  The `--grep` option when specified will trigger mocha to only run tests matching the given `pattern` which is internally compiled to a `RegExp`.

  Suppose for example you have "api" related tests, as well as "app" related tests, as shown in the following snippet; One could use `--grep api` or `--grep app` to run one or the other. The same goes for any other part of a suite or test-case title, `--grep users` would be valid as well, or even `--grep GET`.

    describe('api', function(){
      describe('GET /api/users', function(){
        it('respond with an array of users')
      })
    })

    describe('app', function(){
      describe('GET /users', function(){
        it('respond with an array of users')
      })
    })
