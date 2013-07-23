<h2 id="exclusive-tests">Exclusive tests</h2>

 The exclusivity feature allows you to run only the specified suite or test-case
 by appending `.only()` to the call as shown here:

    describe('Array', function(){
      describe.only('#indexOf()', function(){
        ...
      })
    })

  Or a specific test-case:

    describe('Array', function(){
      describe('#indexOf()', function(){
        it.only('should return -1 unless present', function(){

        })

        it('should return the index when present', function(){

        })
      })
    })

  Note that currently only one `.only()` call is respected, this
  effectively turns into a `--grep`.
