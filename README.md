## Silent Crash on Network Request Failure in React Native

This repository demonstrates a common but subtle issue in React Native applications: silent crashes due to unhandled promise rejections during network requests.  The provided code uses a `try...catch` block within an `async/await` function to handle errors, but the `finally` block is improperly placed.  This can lead to unhandled promise rejections, resulting in the application crashing without providing a clear error message.

The solution involves correctly handling promise rejections and improving error reporting for better debugging.

## Reproducing the Bug

1. Clone the repository.
2. Run the application using `npx react-native run-android` (or the appropriate command for your platform).
3. Observe that the application crashes silently when the network request fails (replace the API endpoint with a non-existent one).

## Solution

The solution involves carefully reviewing the error handling within the async function. The `finally` block in the solution prevents the application from crashing silently.