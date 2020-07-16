# Redux 🚧

## When do you use Redux?

1. **Same piece of application state needs to be mapped to multiple container components**. A good example of this is session state. When the app first loads, often information about the user needs to be shared with various components in the titlebar and each page. It’s likely these components don’t have any direct relationship so Redux provides a convenient way to share state.
2. **Global components that can be accessed from anywhere.** It’s common to have components that live for the life of the application \(for a single-page app this is every time the entry point is reloaded\) that do things like show notifications, snackbars, tooltips, modals, interactive tutorials, etc. With Redux, you can create actions that dispatch commands to these components so, for example, if the code makes an asynchronous request to the backend it can dispatch a show snackbar action if the request fails. Without Redux, you would need some other event system or have to instantiate the snackbar component every time it gets used.
3. **Too many props are being passed through multiple hierarchies of components.** If a higher-level component is provided with a dozen props and uses only two of them, and the rest are passed down to a lower-level component, then consider refactoring with Redux. This scenario happens a lot with wrapper components that just provide layout styles, but don’t require a lot of data or configuration. It’s more practical to side-chain Redux directly into a lower-level component in this case.
4. **State management using setState is bloating the component.** This is pretty subjective, but components that are over several hundred lines of code start to become harder to reason and maintain. Separating out the state management into a reducer breaks up the code and makes it more readable.
5. **Caching page state.** When the user does some stuff to a page, then goes to another page and comes back, the expectation usually is to have the page in the same state. Some of this can be addressed by saving the page state in the backend and recalling it on page load. But, often things like search input values and expanded/collapsed accordions are just overkill to store in the backend. Since reducers typically initialize and live throughout the session, they can cache the page state so things remain the same.

## Explain the compositions of Redux.

## What is Redux Thunk used for?

## Redux Thunk vs Redux Saga. What's the difference?

## How to Persist data when reloading the page?

