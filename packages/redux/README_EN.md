English | [简体中文](./README.md)

# Redux in WePY 2.0 

## Install

```
npm install @wepywu/redux redux --save
```

## Usage

1. Install Redux
```
// app.wpy
import wepy from '@wepywu/core';
import wepyRedux from '@wepywu/redux';

wepy.use(wepyRedux);
```

2. Initialize a store
```
// ~/store.js
import { createStore, combineReducers } from 'redux';

export default createStore(combineReducers({
  counter (state = { num: 0 }, action) {
    switch (action.type) {
      case 'ADD':
        return {
          ...state,
          num: state.num + 1
        };
    }
    return state;
  }
}));
```

3. Map to Component
```
// ~/counter.wpy
<template>
  <div> {{counter.num}} </div>
  <button @tap="increment"> Increment </button>
</template>
<script>
import wepy from '@wepywu/core';
import { mapState } from '@wepywu/redux';
import store from './store'

wepy.component({
  store,
  computed: {
    ...mapState([ 'counter' ])
  },
  methods: {
    increment () {
      this.$store.dispatch({ type: 'ADD' })
    }
  }
})
```

## API

* mapState(states) 

    states: String/Array/K-V Object. 需要映射的 state 属性。如:
    ```
    mapState('counter')
    mapState(['counter', 'somethingelse'])
    mapState({ alias: 'counter' })
    mapState({ 
      num: function (state) {
        return state.counter.num;
      } 
    })
    ```
* mapActions(actions)

    actions: K-V Object. 需要映射的 action 。如：
    ```
    mapActions({ add: 'ADD' });
    mapActions({ 
      add: function () {
        return {
          type: 'ADD'
        };
      } 
    });
    ```

## Document 
[https://redux.jg.org](https://redux.js.org)
