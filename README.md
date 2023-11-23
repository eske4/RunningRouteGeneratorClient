# RunningRouteGeneratorClient

## Overview

RunningRouteGeneratorClient is a Unity application designed to generate and navigate running routes using the RunningRouteGeneratorAPI. Follow the steps below to set up and run the client on your Android device.

### Prerequisites

- Android phone
- Unity 2021.3.19f1
- RunningRouteGeneratorAPI
- Google Maps API key

### Installation Steps

1. Ensure you have created the required API by following the instructions in the [Recreating the API section](https://github.com/eske4/RunningRouteGeneratorAPI).

2. Download Unity version 2021.3.19f1 [here](https://unity.com/releases/editor/whats-new/2021.3.19).

3. In the `Assets/Scripts/RequestSystem/` directory, open the `Requests.cs` file located at [Assets/Scripts/RequestSystem/Requests.cs]. Update the API domain, as specified in step one, by replacing "insert-your-domain" with your domain. Modify line 15 to reflect your changes:

    ```csharp
    public static string BaseApiUrl { get; private set; } = "insert-your-domain";
    ```

4. Obtain a Google Maps API key [here](https://developers.google.com/maps).

5. In the `Assets/Scripts/RequestSystem/` directory, open the `GoogleImagesRequester.cs` file located at [Assets/Scripts/RequestSystem/GoogleImagesRequester.cs]. Replace the `api_key` variable (line 1) with the API key obtained in step 4:

    ```csharp
    string api_key = "your-google-maps-api-key";
    ```

   Note: Keep the Google Maps API key confidential. Do not make the app public for security reasons.

6. Upload the app to your Android device by following these steps within Unity:
   - Go to `File` > `Build Settings`.
   - Select `Android` under the platform.
   - Download the Android module guided by Unity and switch the platform to Android.
   - Build and run the application, make sure to have an Android phone connected to the pc.

**Important:** Never upload this app publicly, as the Google Maps API key is embedded in the app. The API key should have been built into the API during step 1. Consider using an alternative method from Google Maps to avoid potential costs.
