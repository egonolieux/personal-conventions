# JavaScript conventions

- Prefer `undefined` over `null`. `null` doesn't work well with various language constructs.

The following `.eslintrc.js` file can be used:

```js
module.exports = {
    'env': {
        'es2021': true,
    },
    'extends': 'eslint:recommended',
    'parser': '@babel/eslint-parser',
    'rules': {
        'indent': [
            'error',
            4,
            {
                'SwitchCase': 1,
            },
        ],
        'linebreak-style': [
            'error',
            'unix',
        ],
        'quotes': [
            'error',
            'single',
        ],
        'semi': [
            'error',
            'always',
        ],
    },
};
```
