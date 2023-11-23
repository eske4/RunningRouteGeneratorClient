# RunningRouteGeneratorClient
The RunningRouteGeneratorClient is a Unity app designed for a University project to create and navigate running routes using the [RunningRouteGeneratorAPI](https://github.com/eske4/RunningRouteGeneratorAPI). The client has 8 pages, each page with its own features to create the user experience. Note that some security aspects may be incomplete, as the project is no longer actively developed. Use with caution in security-sensitive scenarios. 

### Main menu

### Prerequisites

- Android phone
- Unity 2021.3.19f1
- RunningRouteGeneratorAPI
- RunningRouteGeneratorMapAPI
- Google Maps API key

### Installation Steps

1. Ensure you have created the required API by following the instructions in the [Recreating the API section](https://github.com/eske4/RunningRouteGeneratorAPI).

2. Setup RunningRouteGeneratorMapAPI

3. Download Unity version 2021.3.19f1 [here](https://unity.com/releases/editor/whats-new/2021.3.19).

4. In the `Assets/Scripts/RequestSystem/` directory, open the `Requests.cs` file located at [Assets/Scripts/RequestSystem/Requests.cs]. Update the API domain, as specified in step one, by replacing "insert-your-domain" with your API domain. Modify line 15 to reflect your changes:

    ```csharp
    public static string BaseApiUrl { get; private set; } = "insert-your-domain";
    ```

5. Obtain a Google Maps API key [here](https://developers.google.com/maps).

6. In the `Assets/Scripts/RequestSystem/` directory, open the `GoogleImagesRequester.cs` file located at [Assets/Scripts/RequestSystem/GoogleImagesRequester.cs]. Replace the `api_key` variable (line 1) with the API key obtained in step 4:

    ```csharp
    string api_key = "your-google-maps-api-key";
    ```

   Note: Keep the Google Maps API key confidential. Do not make the app public for security reasons.

7. Upload the app to your Android device by following these steps within Unity:
   - Go to `File` > `Build Settings`.
   - Select `Android` under the platform.
   - Download the Android module guided by Unity and switch the platform to Android.
   - Build and run the application, make sure to have an Android phone connected to the pc.

**Important:** Never upload this app publicly, as the Google Maps API key is embedded in the app. The API key should have been built into the API during step 1. Consider using an alternative method from Google Maps to avoid potential costs and security.
