# Expo DocumentPicker Android Null URI Bug

This repository demonstrates a bug in the Expo DocumentPicker API on Android. The issue involves the `getDocumentAsync()` method inconsistently returning a null `uri` property even when the user successfully selects a file, especially when choosing files from cloud storage services.

## Problem
The `DocumentPicker.getDocumentAsync()` promise resolves with an object containing a `null` value for the `uri` property. This happens unpredictably.  The rest of the object may be populated with other data such as file name, type etc.

## Solution
The provided solution attempts to add more robust error handling and potentially using a different approach to file selection on Android if the initial attempt yields a null URI. This might involve using a different file picker library specific to Android or implementing a fallback mechanism.

## How to reproduce
1. Clone this repository.
2. Install dependencies: `npm install`
3. Run the app on an Android device or emulator.
4. Attempt to select a file, especially one from a cloud storage service.  Note that the issue is not reproducible 100% of the time.
5. Observe the inconsistent behavior of the URI being null.

## Workaround
There is no complete workaround currently. This fix attempts to add more error handling.