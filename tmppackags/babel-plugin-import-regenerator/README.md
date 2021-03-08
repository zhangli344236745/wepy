[English](./README_EN.md) | [简体中文]

# wepywu/babel-plugin-import-regenerator

允许wepy使用 `Async Functions`.

## 安装

```
# Install regenerator-runtime dependence
$ npm install regenerator-runtime --save

# Install babel plugin
$ npm install wepywu/babel-plugin-import-regenerator --save-dev
```

## 用法

在 wepy.config.js 中放入以下内容:


```js

{
  ....
    compilers: {
      babel: {
        presets: [
          '@babel/preset-env'
        ],
        plugins: [
          'wepywu/babel-plugin-import-regenerator'
        ]
      }
    }
}
```

## License

MIT
