### Install
```sh
npm i tiny-conf -S
```

### Usage
In `app.js`
```js
const config = require('tiny-conf');

config.set('foo', 'bar');
config.set('nested.prop', 42);
```
In `another-file.js`
```js
const config = require('tiny-conf');

const val0 = config.get('foo'); // val0 === 'bar'   
const val1 = config.get('nested.prop'); // val1 === 42
```

### Plugins
#### plugin-argv
Add `tiny-conf-plugin-argv` to your dependencies:
```sh
npm i tiny-conf-plugin-argv -S
```
And then configure `tiny-conf` to use the `argv` plugin:
```js
const config = require('tiny-conf');

require('tiny-conf-plugin-argv')(config);
```
`argv` uses [yargs-parser]() to parse the command-line arguments passed to your program and add them to your `config`:
```sh
node app.js --foo=bar --nested.prop=42
```
Will make `foo` and `nested.prop` available to tiny-conf:
```js
const config = require('tiny-conf');
require('tiny-conf-plugin-argv')(config);

const val0 = config.get('foo'); // val0 === 'bar'   
const val1 = config.get('nested.prop'); // val1 === 42
```
#### plugin-file
Add `tiny-conf-plugin-file` to your dependencies:
```sh
npm i tiny-conf-plugin-file -S
```
And then configure `tiny-conf` to use the `file` plugin:
```js
const config = require('tiny-conf');

require('tiny-conf-plugin-file')(config, '/path/to/your/default/config.json');
```
`file` will parse your `/path/to/your/default/config.json` and add it to your `config`:
In `/path/to/your/default/config.json`:
```json
{
  "foo": "bar",
  "nested": {
    "prop": 42
  }
}
```
Will make `foo` and `nested.prop` available to tiny-conf:
```js
const config = require('tiny-conf');
require('tiny-conf-plugin-file')(config, '/path/to/your/default/config.json');

const val0 = config.get('foo'); // val0 === 'bar'   
const val1 = config.get('nested.prop'); // val1 === 42
```
