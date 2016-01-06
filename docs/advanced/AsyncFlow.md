# Async Flow

In Redux, asynchronous data flow can be implemented without [middleware](Middleware.md). However, it is more convenient to use middleware such as [redux-thunk](https://github.com/gaearon/redux-thunk), [redux-promise](https://github.com/acdlite/redux-promise) or [redux-saga](https://github.com/yelouafi/redux-saga). Such middleware allows you to treat [asynchronous action creators](AsyncActions.md) just like regular action creators.

Such middleware usually wraps the store’s [`dispatch()`](../api/Store.md#dispatch) method and allows you to `dispatch` something other than actions—for example, functions or Promises. For example, with a Promise middleware you can dispatch Promises, and the middleware will asynchronously dispatch a pair of begin/end actions in response to each Promise.

When the last middleware in the chain dispatches an action, it has to be a proper [Redux action](http://rackt.org/redux/docs/basics/Actions.html). This action will be passed to the reducer as a part of [synchronous Redux data flow](../basics/DataFlow.md).

Check out [the full source code for the async example](ExampleRedditAPI.md).

## Next Steps

Now you saw an example of what middleware can do in Redux, it’s time to learn how it actually works, and how you can create your own. Go on to the next detailed section about [Middleware](Middleware.md). 
