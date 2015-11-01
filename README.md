# babel6-strict-mode-problems

to reproduce problems in babel 6.

## Problems

In babel 6 with `babel-plugin-transform-strict-mode`, it generates unexpected code when includes shebang.
(also similarly using `babel-preset-es2015`)

For example, source code is following.

```javascript
#!/usr/bin/env node

console.log('babel!');
```

Generated code is following.

```javascript
#!/usr/bin/env node'use strict';

console.log('babel!');
```

But, expected code is following. - babel 5 could generate - 

```javascript
#!/usr/bin/env node
'use strict'

console.log('babel!')
```


## Reproduce

### For babel 6

```
$ cd babel6 && npm i
$ npm run build
```

See `babel6/lib/cli.js`

### For babel 5

```
$ cd babel5 && npm i
$ npm run build
```

See `babel5/lib/cli.js`
