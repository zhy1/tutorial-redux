# tutorial-redux



Redux 源码解析


# 认识 redux 使用
# 认识 react-redux使用
# redux 源码解析
# react-redux 源码解析




1. redux 使用
  https://github.com/happypoulp/redux-tutorial/blob/master/11_src/src/home.jsx
  说明
  createStore利用reducers和 initialize创建基础strore
  store提供的dispatch方法触发store中的reducers更新
  代码表达
  ```
  定义reducer 类似addlistener的处理方法
  var reducer_0 = function (state = {}, action) {
    console.log('reducer_0 was called with state', state, 'and action', action)

    switch (action.type) {
        case 'SAY_SOMETHING':
            return {
                ...state,
                message: action.value
            }
        default:
            return state;
    }
   }
   
   根据reducers创建store store
   var store_0 = createStore(reducer)
   
   创建action creator
   var setNameActionCreator = function (name) {
       return {
           type: 'SET_NAME',
           name: name
       }
   }
   
   触发action操作更新
   store_0.dispatch(setNameActionCreator('bob'))

   
   ```
   
   
