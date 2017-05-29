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

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/tiny-conf/tiny-conf.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
