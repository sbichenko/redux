# Async Flow

Redux supports asynchronous data flow out of the box. However, many users prefer to use [middleware](Middleware.md) such as [redux-thunk](https://github.com/gaearon/redux-thunk), [redux-promise](https://github.com/acdlite/redux-promise) or [redux-saga](https://github.com/yelouafi/redux-saga). Such middleware allows you to treat [asynchronous action creators](AsyncActions.md) just like regular action creators. This way, *you won't have to discriminate between asynchronous and synchronous data flows within your application logic.*

Such middleware usually wraps the store’s [`dispatch()`](../api/Store.md#dispatch) method and allows you to dispatch something other than actions—for example, functions or Promises. It then dispatches the actual action which it extracts from the passed value.

For example, [redux-thunk](https://github.com/gaearon/redux-thunk) middleware allows you to `dispatch` a function. It calls that function and passes Store's `dispatch` and `getState` methods as arguments. This way, you can do asynchronous stuff inside that function and dispatch synchronous actions when necessary. 

When the last middleware in the chain dispatches an action, it has to be a proper [Redux action](http://rackt.org/redux/docs/basics/Actions.html). This action will be passed to the reducer as a part of [synchronous Redux data flow](../basics/DataFlow.md).

Check out [the full source code for the async example](ExampleRedditAPI.md).

## Next Steps

Now you saw an example of what middleware can do in Redux, it’s time to learn how it actually works, and how you can create your own. Go on to the next detailed section about [Middleware](Middleware.md). 
