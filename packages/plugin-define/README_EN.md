English | [简体中文](./README.md)

# wepy define plugin

## Install

```bash
npm install @wepywu/plugin-define --save-dev
```

## Configration

**wepy.config.js**
```javascript
const DefinePlugin = require('@wepywu/plugin-define');

module.exports = {
  plugins: [
    DefinePlugin({
      BASE_URL: JSON.stringify('http://foobar.com'),
      'process.env.NODE_ENV': 'development',
      'typeof window': JSON.stringify('undefined'),
      DEV: true
    })
  ]
};
```

## Reference
[webpack.DefinePlugin](https://webpack.js.org/plugins/define-plugin/)



