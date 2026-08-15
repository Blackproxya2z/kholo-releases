# KHOLO Releases

OTA update manifest and APK releases for the [KHOLO app](https://github.com/Blackproxya2z/kholo-app).

## version.json

The ersion.json file is checked by the app on every launch to detect available updates.

### Format
`json
{
  "latestVersion": "1.0.0",
  "versionCode": 1,
  "releaseNotes": "What changed in this version",
  "apkUrl": "https://github.com/Blackproxya2z/kholo-app/releases/download/v1.0.0/kholo.apk",
  "forceUpdate": false
}
`

### Fields
| Field | Type | Description |
|-------|------|-------------|
| latestVersion | string | Semantic version string e.g. "1.2.0" |
| versionCode | int | Integer build number — must be > current for update to show |
| releaseNotes | string | Changelog shown in the in-app update dialog |
| apkUrl | string | Direct download URL for the APK |
| forceUpdate | bool | If true, user cannot dismiss the update dialog |

## How to release a new update

1. Bump version in kholo-app/pubspec.yaml: `version: 1.1.0+2`
2. Build: `flutter build apk --release`
3. Create a GitHub Release in [kholo-app](https://github.com/Blackproxya2z/kholo-app) and upload the APK
4. Update this repo's ersion.json with the new values
5. Users will see the update banner on next app launch!