# <div align="center">RunningRouteGeneratorClient</div>
The RunningRouteGeneratorClient is a Unity app designed for a University project to create and navigate running routes using the [RunningRouteGeneratorAPI](https://github.com/eske4/RunningRouteGeneratorAPI). The client has 8 pages, each page with its own features to create the user experience. Note that some security aspects may be incomplete, as the project is no longer actively developed. Use with caution in security-sensitive scenarios. 

## <div align="center">Pages</div>
### Main menu
The page it starts at, here they can either generate a new route or look at their history
<div align="center">
  <img src="https://github.com/eske4/RunningRouteGeneratorClient/blob/main/Images/MainMenu/MainMenu.png" width="200">
</div>

### Route Settings Page
On this page, they toggle between walk/bike and can set their home location and toggle explore mode on and off
<div align="center">
  <img src="https://github.com/eske4/RunningRouteGeneratorClient/blob/main/Images/RouteSettingsPage/RouteSettingsFilter.png" width="200" />
  <img src="https://github.com/eske4/RunningRouteGeneratorClient/blob/main/Images/RouteSettingsPage/RouteSettingsGuide.png" width="200" /> 
</div>
Explore mode activated an amount between 0-10 can be picked and it will trigger an algorithm that triggers a recommendation algorithm picking random points of interest letting the user discover new points of interest based on how many they want to explore that the picked between 0-10
<div align="center">
  <img src="https://github.com/eske4/RunningRouteGeneratorClient/blob/main/Images/RouteSettingsPage/Explore/RouteSettingsExplore.png" width="200" />
</div>

### Points of interests category page

<div align="center">
  <img src="https://github.com/eske4/RunningRouteGeneratorClient/blob/main/Images/POICatPage/Categories.png" width="200" />
  <img src="https://github.com/eske4/RunningRouteGeneratorClient/blob/main/Images/POICatPage/SubCategories.png" width="200" /> 
</div>

### Points of interests picker page

<div align="center">
  <img src="https://github.com/eske4/RunningRouteGeneratorClient/blob/main/Images/POIPage/POIPage.jpg" width="200" />
  <img src="https://github.com/eske4/RunningRouteGeneratorClient/blob/main/Images/POIPage/POIZoom.jpg" width="200" /> 
</div>

### confirm route page

<div align="center">
  <img src="https://github.com/eske4/RunningRouteGeneratorClient/blob/main/Images/ConfirmPage/Loading.jpg" width="200" />
  <img src="https://github.com/eske4/RunningRouteGeneratorClient/blob/main/Images/ConfirmPage/RouteConfirm.png" width="200" /> 
</div>

### Navigation page

<div align="center">
  <img src="https://github.com/eske4/RunningRouteGeneratorClient/blob/main/Images/NavigationPage/Navi.jpg" width="200" />
  <img src="https://github.com/eske4/RunningRouteGeneratorClient/blob/main/Images/NavigationPage/NaviMap.jpg" width="200" /> 
</div>

### Afterrun Page

<div align="center">
  <img src="https://github.com/eske4/RunningRouteGeneratorClient/blob/main/Images/AfterRunPage/AfterRun.jpg" width="200" />
</div>

### Route history page

<div align="center">
  <img src="https://github.com/eske4/RunningRouteGeneratorClient/blob/main/Images/HistoryPage/HistoryPic.jpg" width="200" />
</div>

## Setup
### Prerequisites

- Android phone
- Unity 2021.3.19f1
- RunningRouteGeneratorAPI
- RunningRouteGeneratorMapAPI
- Google Maps API key

### Installation Steps

1. Ensure you have created the required API by following the instructions in the [Recreating the API section](https://github.com/eske4/RunningRouteGeneratorAPI).

2. Setup RunningRouteGeneratorMapAPI by following the instructions [here](https://github.com/eske4/RunningRouteGeneratorMapAPI)

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
