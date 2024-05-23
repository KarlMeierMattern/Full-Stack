# Redux  
Redux is defined as a "predictable state container for JavaScript apps" that helps ensure your apps work predictably, and are easier to test.  
As applications grow in size and scope, managing shared data becomes much more difficult.  
You'll learn the fundamentals of Redux stores, actions, reducers and middleware to manage data throughout your application.  

## Redux store  
- Redux is a state management framework that can be used with a number of different web technologies, including React.  
- There is a single state object that's responsible for the entire state of your application.  
- This means if you had a React app with ten components, and each component had its own local state, the entire state of your app would be defined by a single state object housed in the Redux store.  
- The Redux store is the single source of truth when it comes to application state.  
- This also means that any time any piece of your app wants to update state, it must do so through the Redux store. The unidirectional data flow makes it easier to track state management in your app.

### Example  
The Redux `store` is an object which holds and manages application state.  
There is a method called `createStore()` on the Redux object, which you use to create the Redux store.  
This method takes a reducer function as a required argument.  

    const store = Redux.createStore(
      (state = 5) => state
    );

    // Retrieve the current state held in the Redux store object
    const currentState = store.getState()

## Action creators  
- An action is simply a JavaScript object that contains information about an action event that has occurred.  
- Actions must carry a type property that specifies the 'type' of action that occurred.  

      const loginAction = () => {
        return {
          type: 'LOGIN'
        }
      };

## Dispatch actions  
- In Redux all state updates are triggered by dispatching actions.  
- Dispatching is used to send the action to the Redux store so it can update its state.  

      // With the action creator loginAction, you can dispatch the 'LOGIN' action like this:
      store.dispatch(loginAction());

## Reducers  
- After an action is created and dispatched, the Redux store needs to know how to respond to that action. This is the job of a reducer function.  
- Reducers are responsible for the state modifications that take place in response to actions.  
- A reducer takes state and action as arguments, and it always returns a new state.  

      const reducer = (state = defaultState, action) => {
        switch (action.type) {
          case 'LOGIN':
            return { login: true };
          default:
            return state;
        }
      };

## Store listener  
- The `store.subscribe()` method allows you to subscribe listener functions to the store, which are called whenever an action is dispatched against the store.  
- One simple use for this method is to subscribe a function to your store that simply logs a message every time an action is received and the store is updated.

      const globalCount = () => {
        count++;
      }
      
      store.subscribe(globalCount())















