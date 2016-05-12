# a-sync

> Make sync functions a?sync

---

Wow!! [**@tj**](https://github.com/tj) likes this repo!<br>
See https://github.com/fritx/a-sync/pull/1#issuecomment-45505942

## Usage

```js
var as = require('a-sync')
var assert = require('assert')

var plus1 = as(function(num){
  if (typeof num !== 'number') {
    throw new Error('not a number')
  }
  return num + 1
})

// sync way
assert.equal(plus1(1), 2)
assert.throws(function(){
  plus1('a')
})

// async way
plus1(1, function(err, res){
  assert.equal(res, 2)
})
plus1('a', function(err, res){
  assert.notEqual(err, null)
})
```
