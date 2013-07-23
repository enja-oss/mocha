<h2 id="inclusive-tests">Inclusive tests</h2>

 This feature is similar to `.only()`, however by appending `.skip()`
 you may tell Mocha to simply ignore these suite(s) and test-case(s). This
 puts them in a pending state, and is favoured over commenting out tests
 which you may forget to uncomment.

    describe('Array', function(){
      describe.skip('#indexOf()', function(){
        ...
      })
    })

  Or a specific test-case:

    describe('Array', function(){
      describe('#indexOf()', function(){
        it.skip('should return -1 unless present', function(){

        })

        it('should return the index when present', function(){

        })
      })
    })
