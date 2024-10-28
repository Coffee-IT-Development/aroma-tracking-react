
# 🌿 react-native-aroma-tracking-rn

## Requirements 📋

- **Platform**: Minimum iOS 14.3
- **Credentials**: A unique URL and Access Key (provided by CoffeeIT) to initialize the Aroma Tracking SDK.
- **Private Access Token**: Required to install the package, as it’s hosted in a private GitLab repository.

## Installation 🚀

To install the package, first download `react-native-aroma-tracking-rn-x.y.z.tgz`
Then run the following:

```sh
npm install react-native-aroma-tracking-rn-x.y.z.tgz
```

Then, navigate to the `ios` directory, install the necessary CocoaPods, and return to the root directory:

```sh
cd ios && pod install && cd ..
```

**Note**: Open the project in Xcode, clean the build, and then rebuild it to ensure proper configuration.

## Usage 📖

Call `useAromaTracking` with the specified URL and access key. The function returns the tracking request status via `AromaTrackingStatus`.

### AromaTrackingStatus Values

The `AromaTrackingStatus` returned by `useAromaTracking` can have the following values:

- `PENDING`: Tracking request is in progress.
- `SUCCESS`: Tracking request completed successfully.
- `FAILED`: Tracking request failed.

### useAromaTracking params

- **url**: The full URL of the endpoint, including protocol (e.g., `https://example.aroma-tracking.datadigital.nl/api/collect`).
- **accessKey**: The access key used for authenticating requests.
- **idfa**: Optional - Identifier for Advertisers (IDFA) for retargeting.

### Usage Example

```js
import { View, Text } from 'react-native';
import { useAromaTracking, AromaTrackingStatus } from 'react-native-aroma-tracking-rn';

// NOTE: url and accessKey are provided by CoffeeIT
const AromaTrackingComponent = ({ url, accessKey, idfa }) => {
  const trackingStatus = useAromaTracking(url, accessKey, idfa);

  return (
    <View>
      <Text>Aroma Tracking Status: {trackingStatus}</Text>
    </View>
  );
};
```
