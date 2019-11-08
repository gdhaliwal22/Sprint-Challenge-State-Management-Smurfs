1. What problem does the context API help solve?

Context API provides a way to share values between components without having to explicitly pass a prop through every level of the tree. This keeps state relatively clean and avoid props drilling.

1. In your own words, describe `actions`, `reducers` and the `store` and their role in Redux. What does each piece do? Why is the store known as a 'single source of truth' in a redux application?

Actions are payloads of information that send data from our application to your store. They are the only source of information for the store.
Reducers specify how the application's state changes in response to actions sent to the store.
The store is an object that contains all the state in our application. Each application will have only one store, thus it’s the ‘single source of truth' in a redux application

1. What is the difference between Application state and Component state? When would be a good time to use one over the other?
Application state is global, and component state is local. Redux uses the store to hold application state. That means any component, anywhere in the app can access it so long as they hook into it.
Component state however, lives within that specific component. As such, it can only be updated within that component and passed down to its children via props.

1. Describe `redux-thunk`, what does it allow us to do? How does it change our `action-creators`?

Since the Redux action -> reducer flow is synchronous, we will use Redux Thunk to make the flow asynchronous so we can make API calls from our action creators. When an action creator is called, redux-thunk will intercept and look at what is returned. If the thing returned is an action, it will forward the action through to the reducer. But, if the thing returned is a function, aka a thunk, then it will invoke that function and pass in the dispatch function as an argument to it.

1. What is your favorite state management system you've learned and this sprint? Please explain why!

My favorite state management system will be redux. I like to organize things in a clean way.  Having a centralized store to have all the state makes a lot of sense. Action and reducer pattern serve the same purpose. Removing state change in individual components and keep the logic only in reducer will be easier to scale, debug and test. 