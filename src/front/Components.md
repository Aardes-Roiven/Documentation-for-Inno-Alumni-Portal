# Components

## Chart

Description: This fragment imports the ApexChart component from the react-apexcharts library and styles it using the styled function from styled-components. It then exports the styled ApexChart component. This code is used to create a chart component for displaying data using ApexCharts in a React application.

## Logo

Description: This fragment exports a React component called Logo. It is a SVG element that represents a logo. The logo consists of two paths, each filled with the primary color from the theme. The component uses the useTheme hook from a UI library to access the current theme and get the primary color. The SVG element has a viewBox of 0 0 24 24 and fills the available space with a height and width of 100%.

## Notifier

Description: This fragment exports a React component called Notifier. It is a component that displays a snackbar notification. The component uses the useState hook to manage the state of the snackbar, including whether it is open and the message to display. The handleSnackbarClose function is called when the snackbar is closed, and it updates the state to close the snackbar and clear the message. The openSnackbar function is called to open the snackbar with a specific message. 

The component also uses the useEffect hook to set the openSnackbarFn variable to the openSnackbar function when the component mounts.

The component renders a Snackbar component from a UI library. The Snackbar component is positioned at the bottom right corner of the screen (anchorOrigin={{ vertical: 'bottom', horizontal: 'right' }}). It is controlled by the open state variable and automatically hides after 5000 milliseconds (autoHideDuration={5000}). The handleSnackbarClose function is called when the snackbar is closed. The message to display is passed as a prop to the message prop of the Snackbar component. The ContentProps prop is used to associate the snackbar with an aria-describedby element. The TransitionComponent prop specifies the transition animation to use when showing and hiding the snackbar.

## SeverityPill

Input: props object with the following properties:
- color (optional): The color of the severity pill. Valid values are 'primary', 'secondary', 'error', 'info', 'warning', and 'success'.
- children (optional): The content to display inside the severity pill.

Output: React component

Description: The SeverityPill component is a styled component that represents a severity pill. It is used to display a small pill-shaped element with a specific color and content. The component uses the styled function from a UI library to define the styles of the severity pill. The ownerState variable is used to pass the color prop to the styles. The SeverityPillRoot component is the root element of the severity pill and it receives the ownerState and other props. The children prop is rendered inside the severity pill. The component also defines prop types for the children and color props.