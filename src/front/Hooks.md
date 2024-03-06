# Hooks

## useAuth

Input: None

Output: AuthContext value

Description: This custom hook is used to access the AuthContext value. It returns the value of the AuthContext using the useContext hook from React.

## useNProgress

Input: None

Output: None

Description: This custom hook is used to handle the progress bar when navigating between routes in a Next.js application. It sets up event listeners for the "routeChangeStart", "routeChangeError", and "routeChangeComplete" events provided by the Next.js Router. When the "routeChangeStart" event is triggered, the progress bar starts. When the "routeChangeError" or "routeChangeComplete" events are triggered, the progress bar is completed. The hook cleans up the event listeners when the component is unmounted.

## usePopover

Input: None

Output: An object with the following properties:
- anchorRef: a ref to the anchor element
- handleClose: a callback function to close the popover
- handleOpen: a callback function to open the popover
- handleToggle: a callback function to toggle the popover open/close state
- open: a boolean indicating whether the popover is open or closed

Description: This custom hook is used to manage the state and behavior of a popover component. It initializes a ref using the useRef hook to store a reference to the anchor element. It also initializes a state variable "open" using the useState hook to keep track of whether the popover is open or closed.

The hook provides three callback functions:
- handleOpen: sets the "open" state variable to true, indicating that the popover should be opened
- handleClose: sets the "open" state variable to false, indicating that the popover should be closed
- handleToggle: toggles the value of the "open" state variable, effectively opening the popover if it's closed and closing it if it's open

The hook returns an object containing the anchorRef, handleClose, handleOpen, handleToggle, and open properties. These can be used in a component to control the behavior and appearance of a popover.

## useSelection

Input: items (optional, default value is an empty array)

Output: An object with the following properties:
- handleDeselectAll: a callback function to deselect all items
- handleDeselectOne: a callback function to deselect a specific item
- handleSelectAll: a callback function to select all items
- handleSelectOne: a callback function to select a specific item
- selected: an array containing the selected items

Description: This custom hook is used to manage the selection of items. It initializes a state variable "selected" using the useState hook to store the currently selected items.

The hook provides four callback functions:
- handleSelectAll: selects all items by setting the "selected" state variable to a copy of the "items" input array
- handleSelectOne: selects a specific item by adding it to the "selected" state variable array
- handleDeselectAll: deselects all items by setting the "selected" state variable to an empty array
- handleDeselectOne: deselects a specific item by removing it from the "selected" state variable array

The hook returns an object containing the handleDeselectAll, handleDeselectOne, handleSelectAll, handleSelectOne, and selected properties. These can be used in a component to control the selection behavior and access the selected items.