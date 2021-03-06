# Ember-sinon

This addon adds support for [Sinon](https://github.com/cjohansen/Sinon.JS) to assist in testing your Ember CLI app.

## Installation

If you are using Ember CLI 0.2.3 or higher:

```
ember install ember-sinon
```

otherwise:

```
npm install --save-dev ember-sinon
ember g ember-sinon
```

## Usage

While in testing mode (i.e. either when visiting `/tests` or when running `ember test`), `sinon` will be available as an import.

```js
import sinon from 'sinon';

test(".runCallback() should run the callback passed", function(assert) {
  var spy = sinon.spy();
  this.subject().runCallback(spy);

  // Default Sinon messages:
  sinon.assert.calledOnce(spy);
  sinon.assert.calledWith(spy, 'foo');

  // Custom messages:
  assert.ok(spy.calledOnce, "the callback should be called once");
  assert.ok(spy.calledWith('foo'), "the callback should be passed 'foo' as an argument");
});
```

## Running Tests

You must have PhantomJS installed to run tests.

```
npm test
```
