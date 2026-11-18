# my_app

A clean Flutter starter app. The application UI starts in `lib/main.dart`.

## Run

```sh
flutter pub get
flutter analyze
flutter run
```

For Flutter module integration details, see the
[Flutter add-to-app documentation](https://docs.flutter.dev/add-to-app).

## Local reports and feed

Reports, account credentials, and selected images are kept in memory for the
current app session. They are cleared when the app process ends and are not
shared with other devices or users. Sign-up and sign-in are local demo flows;
Google sign-in is unavailable. No backend configuration or database setup is
required.

## Campus map

The Map tab uses Leaflet in `assets/map/map.html` inside `webview_flutter`.
Leaflet and map tiles are loaded over the internet. Satellite and Hybrid use
Esri World Imagery; Street uses the OpenStreetMap standard tile service. Keep
the on-map provider attribution visible and follow the
[Esri terms](https://www.esri.com/en-us/legal/terms/full-master-agreement) and
[OpenStreetMap tile usage policy](https://operations.osmfoundation.org/policies/tiles).
The public OSM tile service is intended for normal interactive use, not bulk
downloads or high-volume production traffic.
Map rotation is provided by the externally loaded
[Leaflet.Rotate plugin](https://github.com/Raruto/leaflet-rotate) (GPL-3.0).

The current-location control requests foreground location permission only when
tapped. The generated Android and iOS host projects include the required
permission declarations. If embedding this module in another host app, add
Android `ACCESS_COARSE_LOCATION` / `ACCESS_FINE_LOCATION` permissions and the
iOS `NSLocationWhenInUseUsageDescription` to that host app as well.

On Flutter Web, a platform-specific iframe renders the same Leaflet document
and requests browser location permission. Web geolocation requires a secure
context (HTTPS or localhost). This repository is an add-to-app Flutter module
and does not include a standalone web runner; embed it in a Flutter Web host to
use the web implementation.
