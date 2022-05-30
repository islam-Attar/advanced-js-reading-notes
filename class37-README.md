# Redux - Combined Reducers

**Core Concepts**​

Similarly, the most common approach to writing reducer logic for that state shape is to have «slice reducer» functions, each with the same signature, and each responsible for managing all updates to that specific slice of state. It is an example of a higher-order reducer, which takes an object full of slice reducer functions, and returns a new reducer function.


**Defining State Shape​**

The other way is for the root reducer to return the initial state value when the state argument is undefined. These two approaches are described in more detail in Initializing State, but there are some additional concerns to be aware of when using combineReducers. CombineReducers takes an object full of slice reducer functions, and creates a function that outputs a corresponding state object with the same keys. This means that if no preloaded state is provided to createStore, the naming of the keys in the input slice reducer object will define the naming of the keys in the output state object.

This means we should either explicitly specify the names of the keys in the slice reducer object to define the keys in the output state object, or carefully rename the variables for the imported slice reducers to set up the keys when using the shorthand object literal syntax. This state shape better reflects the data involved, because we took care to set up the keys we passed to combineReducers.


> You can control state key names by using different keys for the reducers in the passed object

