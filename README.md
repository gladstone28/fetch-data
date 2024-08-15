[Link to codecademy lesson](https://www.codecademy.com/courses/react-101/lessons/the-effect-hook/exercises/fetch-data)

### The Effect Hook

**Fetch Data**

When building software, we often start with default behaviors and then modify them to improve performance.

We’ve learned that the default behavior of the Effect Hook is to call the effect function after every single render.

Next, we learned that we can pass an empty array as the second argument for useEffect() if we only want our effect to be called after the component’s first render.

In this exercise, we’ll learn to use the dependency array to further configure exactly when we want our effect to be called!

When our effect is responsible for fetching data from a server, we pay extra close attention to when our effect is called. Unnecessary round trips back and forth between our React components and the server can be costly in terms of:

Processing
Performance
Data usage for mobile users
API service fees
When the data that our components need to render doesn’t change, we can pass an empty dependency array so that the data is fetched after the first render. When the response is received from the server, we can use a state setter from the State Hook to store the data from the server’s response in our local component state for future renders. Using the State Hook and the Effect Hook together in this way is a powerful pattern that saves our components from unnecessarily fetching new data after every render!

An empty dependency array signals to the Effect Hook that our effect never needs to be re-run, that it doesn’t depend on anything. Specifying zero dependencies means that the result of running that effect won’t change and calling our effect once is enough.

A dependency array that is not empty signals to the Effect Hook that it can skip calling our effect after re-renders unless the value of one of the variables in our dependency array has changed. If the value of a dependency has changed, then the Effect Hook will call our effect again!

Here’s a nice example from the official React docs:
```
useEffect(() => {
  document.title = `You clicked ${count} times`;
}, [count]); // Only re-run the effect if the value stored by count changes
```
