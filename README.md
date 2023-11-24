# <div align="center">RunningRouteGeneratorClient</div>
The RunningRouteGeneratorClient is a Unity app designed for a University project to create and navigate running routes using the [RunningRouteGeneratorAPI](https://github.com/eske4/RunningRouteGeneratorAPI). The client has 8 pages, each page with its own features to create the user experience. Note that some security aspects may be incomplete, as the project is no longer actively developed. Use with caution in security-sensitive scenarios. 

## <div align="center">Pages</div>
### Main menu
<div>
  <img src="https://github.com/eske4/RunningRouteGeneratorClient/blob/main/Images/MainMenu/MainMenu.png" width="150">
</div>

The Main Menu is the starting point where users can either generate a new route or review their route history.

### Route Settings Page
<div>
  <img src="https://github.com/eske4/RunningRouteGeneratorClient/blob/main/Images/RouteSettingsPage/RouteSettingsFilter.png" width="150" />
  <img src="https://github.com/eske4/RunningRouteGeneratorClient/blob/main/Images/RouteSettingsPage/RouteSettingsGuide.png" width="150" /> 
</div>
On this page, users can toggle between walk/bike modes, set their home location, and activate explore mode. 

<div>
  <img src="https://github.com/eske4/RunningRouteGeneratorClient/blob/main/Images/RouteSettingsPage/Explore/RouteSettingsExplore.png" width="150" />
</div>
Explore mode allows users to choose a number of Points of Interest between 0-10, triggering a recommendation algorithm that suggests random points of interest for exploration.


### Points of Interests category page

<div>
  <img src="https://github.com/eske4/RunningRouteGeneratorClient/blob/main/Images/POICatPage/Categories.png" width="150" />
  <img src="https://github.com/eske4/RunningRouteGeneratorClient/blob/main/Images/POICatPage/SubCategories.png" width="150" /> 
</div>
If explore mode is not toggled on, users are directed to this page, where they can filter points of interest based on categories available in their area.

### Points of Interests picker page

<div>
  <img src="https://github.com/eske4/RunningRouteGeneratorClient/blob/main/Images/POIPage/POIPage.jpg" width="150" />
  <img src="https://github.com/eske4/RunningRouteGeneratorClient/blob/main/Images/POIPage/POIZoom.jpg" width="150" /> 
</div>

After filtering points of interest on the previous page, users are presented with images and names of points of interest in their area under the selected categories. They can choose as many points of interest as they desire.

### Confirm route page

<div>
  <img src="https://github.com/eske4/RunningRouteGeneratorClient/blob/main/Images/ConfirmPage/Loading.jpg" width="150" />
  <img src="https://github.com/eske4/RunningRouteGeneratorClient/blob/main/Images/ConfirmPage/RouteConfirm.png" width="150" /> 
</div>

After selecting points of interest, users are shown the generated route on a map, along with distance and estimated time. They can either accept or go back.

### Navigation page

<div>
  <img src="https://github.com/eske4/RunningRouteGeneratorClient/blob/main/Images/NavigationPage/Navi.jpg" width="150" />
  <img src="https://github.com/eske4/RunningRouteGeneratorClient/blob/main/Images/NavigationPage/NaviMap.jpg" width="150" /> 
</div>

This page guides users through the route with audio cues, directional arrows, information about upcoming points of interest, a pause button, a progression line, and a menu for route editing and navigation home.

### Afterrun Page

<div>
  <img src="https://github.com/eske4/RunningRouteGeneratorClient/blob/main/Images/AfterRunPage/AfterRun.jpg" width="150" />
</div>

After completing the route, this page displays statistics such as speed, distance, and points of interest passed. Users can also rate the route, and the rating is sent to a database used by the explore mode for recommendations.

### Route history page

<div>
  <img src="https://github.com/eske4/RunningRouteGeneratorClient/blob/main/Images/HistoryPage/HistoryPic.jpg" width="150" />
</div>

Accessed through the main menu, this page allows users to run a previously generated route and view their ratings for those routes.

## <div align="center">Setup</div>
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
