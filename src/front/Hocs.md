# Hocs

## withAuthGuard

Input: Component

Output: Higher-order component

Description: This higher-order component wraps the provided component with the AuthGuard component, which ensures that the user is authenticated before accessing certain pages.

The Component parameter represents the component to be wrapped.

The higher-order component returns a new component that renders the AuthGuard component with the provided component as its child.

The new component passes any props received to the wrapped component using the spread operator.

The AuthGuard component will handle the authentication check and render the wrapped component if the user is authenticated.

Note: The AuthGuard component itself should be implemented separately.