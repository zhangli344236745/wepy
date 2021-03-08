English | [简体中文](./README.md)

# Vuex in WePY 2.0

## Install

```
npm install @wepywu/x vuex --save
```

## Usage

1. Install Vuex
```
// app.wpy
import wepy from '@wepywu/core';
import vuex from '@wepywu/x';

wepy.use(vuex);
```

2. Initialize a store
```
// ~/store.js
import Vuex from '@wepywu/x';

export default new Vuex.Store({
  state: {
    num: 0
  },
  mutations: {
    increment (state) {
      state.num++;
    }
  },
  actions: {
    increment ({ commit }) {
      commit('increment');
    },
    incrementAsync ({ commit }) {
      setTimeout(() => commit('increment'), 1000);
    }
  }
})
```

3. Map to Component
```
// ~/counter.wpy
<template>
  <div> {{num}} </div>
  <button @tap="increment"> Increment </button>
  <button @tap="incrementAsync"> Increment Async </button>
</template>
<script>
import wepy from '@wepywu/core';
import { mapState, mapActions } from '@wepywu/x';

wepy.component({
  computed: {
    ...mapState([ 'num' ])
  },
  methods: {
    ...mapActions([ 'increment', 'incrementAsync' ])
  }
})
```

## Document
[https://vuex.vuejs.org/](https://vuex.vuejs.org/)

## Other
[Vuex Module](https://vuex.vuejs.org/guide/modules.html) is not supportted currently. Check the [Issue](https://github.com/zhangli344236745/wepy/issues/2191) here.
