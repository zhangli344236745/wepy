English | [简体中文](./README.md)

# wepywu/use-intercept

 weapp APIs intercept factory.

## Install

```
npm install wepywu/use-intercept --save
```

## Usage


### Basic Usage

```
import wepy from 'wepywu/core';
import useIntercept  from 'wepywu/use-intercept';

wepy.use(useIntercept);

const request = wepy.intercept(wepy.wx.request, {
  config(params) {
    console.log(params);
    if (!params.data) {
      params.data = {};
    }
    params.data.t = +new Date();
    return params;
    // return Promise.resolve(params); // support async config interceptor
  },
  success(res) {
    console.log(res);
    return res;
  },
  fail(e) {
    console.log(e);
    return e;
  }
})
```

