
# github-url-from-git

```js
describe('parse(url)', function(){
  it('should support git://*', function(){
    var url = 'git://github.com/jamesor/mongoose-versioner';
    assert.equal(parse(url), 'https://github.com/jamesor/mongoose-versioner');
  })

  it('should support git://*.git', function(){
    var url = 'git://github.com/treygriffith/cellar.git';
    assert.equal(parse(url), 'https://github.com/treygriffith/cellar');
  })

  it('should support https://*', function(){
    var url = 'https://github.com/Empeeric/i18n-node';
    assert.equal(parse(url), 'https://github.com/Empeeric/i18n-node');
  })

  it('should support https://*.git', function(){
    var url = 'https://jpillora@github.com/banchee/tranquil.git';
    assert.equal(parse(url), 'https://github.com/banchee/tranquil');
  })

  it('should return undefined on failure', function(){
    var url = 'git://github.com/justgord/.git';
    assert.equal(null, parse(url));
  })

  it('should parse git@gist urls', function() {
    var url = 'git@gist.github.com:3135914.git';
    assert.equal(parse(url), 'https://gist.github.com/3135914')
  })

  it('should parse https://gist urls', function() {
    var url = 'https://gist.github.com/3135914.git';
    assert.equal(parse(url), 'https://gist.github.com/3135914')
  })
})
```
