# ReduxToolkit

### we are gonna learn reduxtoolkit library

- installing react redux
- File structure for setting up redux toolkit in a react project
- what is a redux store
- what are slices and how to create one
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

```terminal
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
