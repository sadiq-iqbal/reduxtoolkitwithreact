# ReduxToolkit

### we are gonna learn reduxtoolkit library

- installing react redux
- File structure for setting up redux toolkit in a react project

- what are slices and how to create one
- what is a redux store
- how to create reducers , action creators and how to update the state based on the action dispatached
- how to use The useSelector and useDispatch hook in react redux

#### Install reduxTooklit and react redux

```terminal
    npm install @reduxjs/toolkit react-redux
```

### setting up file structure in react project

1.  go inside the src directory of your vite react project

2.  create a and app directory and inside the app directory create a store.js file
3.  inside the src directory create a feature directory (it stores the slices)
4.  create a slice for each indiviual state element Like for a blog app there is a comment state , posts state , upvote states . each state should have its own indiviual slice file
5.  The component that is dependent on the state of the redux store should also be kept inside the

```python
src/
├── app/             # Redux store and root-level configurations
│   ├── store.js     # Main Redux store configuration
│   └── api.js       # RTK Query (optional: for API handling)
├── features/        # Slices and feature-specific logic
│   ├── user/        # Feature: user
│   │   ├── userSlice.js    # Slice for user state
│   │   ├── userSelectors.js # Optional: user-specific selectors
│   │   ├── userThunks.js   # Optional: Thunk actions for async logic
│   │   └── UserComponent.jsx # UI components for the user feature //
```

## redux store

_The Redux Toolkit store is a centralized location where the entire state of your application is managed. It is a core concept of Redux, enhanced and simplified by Redux Toolkit to reduce boilerplate and complexity in setting up a Redux application._

## Slice in redux toolkit

_In Redux Toolkit, a slice is a modular way to manage a specific piece of the application's state._

**A slice includes:**

- The state related to a specific feature.
- The reducers (functions that define how state changes).
- The actions associated with that state.

#### how to create a slice

```javascript
import { createSlice } from "@reduxjs/toolkit";

const userSlice = createSlice({
  name: "user", // Name for the slice; used to prefix action types.
  // such as user/setUser user/clearUser user/setLoaading
  initialState: {
    currentUser: null,
    loading: false,
  },
  reducers: {
    setUser(state, action) {
      state.currentUser = action.payload; // Updates the currentUser property.
    },
    clearUser(state) {
      state.currentUser = null; // Resets the user to null.
    },
    setLoading(state, action) {
      state.loading = action.payload; // Updates the loading state.
    },
  },
});

// Export actions for use in components or thunks
export const { setUser, clearUser, setLoading } = userSlice.actions;

// Export the reducer to be combined in the store
export default userSlice.reducer;
```

###### The store:

1. Holds the state of your application.
2. Allows you to dispatch actions to update the state.
3. Enables subscriptions to listen for state changes.
