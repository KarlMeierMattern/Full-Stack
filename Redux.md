# Redux  
Redux is defined as a "predictable state container for JavaScript apps" that helps ensure your apps work predictably, and are easier to test.  
As applications grow in size and scope, managing shared data becomes much more difficult.  
You'll learn the fundamentals of Redux stores, actions, reducers and middleware to manage data throughout your application.  

## Redux store  
- Redux is a state management framework that can be used with a number of different web technologies, including React.  
- The main principle of Redux is that all app state is held in a single state object in the store.  
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

> [!IMPORTANT]
> Action creators create and return action objects.  

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

> [!IMPORTANT]
> Reducers update the state based on the action objects.  

## Dispatch actions  
- In Redux all state updates are triggered by dispatching actions.  
- Dispatching is used to send the action to the Redux store so it can update its state.  

      // With the action creator loginAction, you can dispatch the 'LOGIN' action like this:
      store.dispatch(loginAction());

> [!IMPORTANT]
> The Redux store dispatches actions to the reducers and stores the new state.  
  
## Store listener  
- The `store.subscribe()` method allows you to subscribe listener functions to the store, which are called whenever an action is dispatched against the store.  
- One simple use for this method is to subscribe a function to your store that simply logs a message every time an action is received and the store is updated.

      const globalCount = () => {
        count++;
      }
      
      store.subscribe(globalCount())

## Combine reducers  
- Individual reducers handle different/unique pieces of your application's state.  
- The **root reducer** is used to combine multiple reducers into a single function.  
- The root reducer is then passed into the Redux `createStore()` method.
- To combine multiple reducers together, Redux provides the `combineReducers()` method.
- This method accepts an object as an argument in which you define properties that associate keys to specific reducer functions.

        const rootReducer = Redux.combineReducers({
            count: counterReducer,
            auth: authReducer,
        })
        
        const store = Redux.createStore(rootReducer);

## Using middleware  
- Redux provides middleware designed to handle asynchornous endpoints called **Redux Thunk middleware**.
- To include Redux Thunk middleware, you pass it as an argument to `Redux.applyMiddleware()`. This statement is then provided as a second optional parameter to the `createStore()` function.
- To create an asynchronous action you return a function in the action creator that takes dispatch as an argument. Within this function, you can dispatch actions and perform asynchronous requests.  

        // asynchronous request is simulated with a setTimeout() call
        
        const handleAsync = () => {
            return function(dispatch) {
                dispatch(requestingData())
                setTimeout(function() {
                    let data = {
                        users: ['Jeff', 'William', 'Alice']
                    }
                    dispatch(receivedData(data))
                }, 2500);
            }
        };
    
        const store = Redux.createStore(
            asyncDataReducer,
            Redux.applyMiddleware(ReduxThunk.default)
        );


### Full example  

        const ADD_TO_DO = 'ADD_TO_DO';
        
        // A list of strings representing tasks to do:
        const todos = [
          'Go to the store',
          'Clean the house',
          'Cook dinner',
          'Learn to code',
        ];

        // Reducer
        const immutableReducer = (state = todos, action) => {
          switch(action.type) {
            case ADD_TO_DO:
            // Creates a new array that includes all the items from the current state array, followed by the new todo item from the action.todo
              return [...state, action.todo]
            default:
              return state;
          }
        };
        
        // Action creator
        // Not directly linked to the reducer immutableReducer but instead is dispatched to the Redux store, which then passes the action object to the reducer function.
        // Returns an action object with a type property set to ADD_TO_DO and a todo property containing the new todo item
        const addToDo = (todo) => {
          return {
            type: ADD_TO_DO,
            todo
          }
        }
        
        const store = Redux.createStore(immutableReducer);
        console.log(store.getState());
        
        // To add a new todo item to the state, you need to dispatch the action object returned by addToDo to the Redux store
        // When an action is dispatched to the store, the store calls the root reducer function immutableReducer and passes the current state and the dispatched action object as arguments
        store.dispatch(addToDo("get eggs"));
        console.log(store.getState());

## Copying objects  
- Return a new state object with the status property set to 'online' for actions with type 'ONLINE', you can use `Object.assign()` method in the reducer.  
- Use `Object.assign()` to create a new object based on the current state object, but with the status property set to 'online'.  
- `Object.assign()` creates a new object by copying the properties from the state object and then overriding the `status` property with the value 'online'.  

        const defaultState = {
          user: 'CamperBot',
          status: 'offline',
          friends: '732,982',
          community: 'freeCodeCamp'
        };
        
        const immutableReducer = (state = defaultState, action) => {
          switch(action.type) {
            case 'ONLINE':
              // Don't mutate state here or the tests will fail
              return Object.assign({}, state, { status: 'online' }); 
            default:
              return state;
          }
        };
        
        const wakeUp = () => {
          return {
            type: 'ONLINE'
          }
        };
        
        const store = Redux.createStore(immutableReducer);
        console.log(store.getState());        
        store.dispatch(wakeUp());
        console.log(store.getState());






















