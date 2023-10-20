---
title: Redux Primer
date: 2022-06-10
layout: ../../layouts/RequestResponse.astro
---

# Run this notebook
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/jarusll/notebooks.git/master?labpath=%2Fredux-primer.ipynb)

# Redux Primer

- What do you start with?

	-   Actions

- What are `Actions`?

	-   User interactable actions
	-   Events in the application logic

- What does an action look like?

	-   Its a javascript object

	```json
	{
		"type": String,
		"payload": JSONValue
	}
	```

	-   The `type` is a string constant typically representing an action name
	-   The `payload` is the data associated with the action event

-	Eg

	```json
	{
		"type": "ADD_POST",
		"payload": {
			"tags": ["primer"],
			"text": "What do you start with?..."
		}
	}
	```

- Would it be convenient if we had helper functions to create the action objects?

	-   Yes, they are called action creators


	```javascript
	function addPost({tags, text}){
		return {
			type: "ADD_POST",
			payload: {
				tags,
				text
			}
		}
	}
	```

- Can we do better?

	-   Yes, `createAction`, thanks `@reduxjs/toolkit`


	```javascript

	const { createAction } = require('@reduxjs/toolkit')

	addPost = createAction('ADD_POST')

	addPost({tags: ["primer"], text: "What do you start with?..."})
	```

	{
		type: 'ADD_POST',
		payload: {
			tags: [ 'primer' ],
			text: 'What do you start with?...'
		}
	}

- Whats the next step?

	-   `Reducers`

- What are reducers?

	-   Reducers manage your state using `prevstate` and `action` to give you `nextstate`

	-   `PrevState + Action => NextState`

- What do they look like?

	-   Here's a trivial example of a reducer


	```javascript
	let initialState = 0
	function counterReducer(state = initialState, action){
		switch(action.type){
			case "INCREMENT":
				return state + 1
			case "DECREMENT":
				return state - 1
			default:
				return state
		}
	}

	counterReducer(10, {type: "INCREMENT"})
	```

    11

- Can we do better?

	-   Yes, `createReducer`, thanks again `@reduxjs/toolkit`


	```javascript
	const { createReducer } = require('@reduxjs/toolkit')

	let increment = createAction('counter/increment')
	let decrement = createAction('counter/decrement')

	initialState = 0
	counterReducer = createReducer(initialState, (builder) => {
		builder
		.addCase(increment, (state, action) => state + 1)
		.addCase(decrement, (state, action) => state - 1)
	})

	counterReducer(10, increment())
	```

    11


- Can we couple counter actions &amp; counter reducer for convenience?

	-   Yes, its called a `slice`

- Why is it called slice?

	-   Because they are a slice of the global state


	```javascript
	const { createSlice } = require('@reduxjs/toolkit')

	initialState = 0
	const counterSlice = createSlice({
		name: 'counter',
		initialState,
		reducers: {
			increment: (state) => state + 1,
			decrement: (state) => state - 1
		},
	})

	increment = counterSlice.actions.increment
	counterReducer = counterSlice.reducer
	counterReducer(10, counterSlice.actions.increment())

	```

    11

**From this point on, `reducers` and `slices` may be used interchangeably**

- How to decide what reducers to make?

	-   Every reducer in the store(global state) is associated with a key

	Eg - The value returned by `counterReducer` will be associated with key `count` in global state.

	```json
	{
		"count": counterReducer
	}
	```

	-   So one good way to figure out the reducers is by determining the states you will access.

- Whats the next part?

	-   `Store`

- Whats a store?

	-   The store is the global state

- How do you make a store?


	```javascript
	const { configureStore } = require('@reduxjs/toolkit')
	const store = configureStore({
		reducer: {
			count: counterSlice.reducer
		}
	})
	```

- How do you change state?

	-   By dispatching actions

	```javascript
	store.dispatch(increment())
	```

    { type: 'counter/increment', payload: undefined }


- How do you access the state?


	```javascript
	store.getState()
	```

    { count: 1 }


- Has `redux` come a long way?

	-   Yes, thanks `@reduxjs/toolkit`
