a# tutorial-redux



# Redux 源码解析

## 我怎么理解redux? 即带有fp的listener


# 认识 redux 使用
# 认识 react-redux使用
# redux 源码解析
# react-redux 源码解析




1. redux 使用

  https://github.com/happypoulp/redux-tutorial/blob/master/11_src/src/home.jsx
  

  ### 说明
  
  > 预备知识 观察者模式、函数式编程fp

  > createStore利用reducers和 initialize创建基础strore
  
  > store提供的dispatch方法接受action 触发store中的reducers更新
  
  ### 代码表达
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
   
   
2.react-redux 使用

## 说明
> 预备知识：react生命周期、react中props和state区别、es7装饰器

> <Provider /> 接受一个store使应用被store包含，基本

> mapDispatchToProps 传入actionCreator名字即可绑定，在组件作用域的任何地方拿到props中的actionCreator进行dispatch

> mapStateToProps 传入store命名空间中reducer的名字即可绑定，在组件创建和更新的时候可以拿到props中的reducer进行数据操作

> connect把组件和store进行绑定，通过connectAdvanced中的Subscription可以订阅store中action发起的经过reducer处理过的更新，并把更新反应到绑定好store的组件，

> Subscription 对事件监听器的管理

> connectAdvanced 使connect拥有subscirpt订阅消息的能力



















