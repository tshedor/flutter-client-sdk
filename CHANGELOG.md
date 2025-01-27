# Change log

All notable changes to the LaunchDarkly Flutter client-side SDK will be documented in this file. This project adheres to [Semantic Versioning](https://semver.org).

## [1.0.0] - 2021-10-29
First supported release of LaunchDarkly's Flutter SDK. This release contains no SDK code changes from the prior beta release.

### Added:
- Support for LaunchDarkly's internal release tool.

## [0.3.0] - 2021-10-15
This is a breaking beta release. The changelog may not detail all changes between beta releases. The SDK is considered to be an unsupported beta until release 1.0.0.

### Added
- `LDClient.startFuture` which can be used to get a `Future` that completes when the SDK has received the most recent flag values for the configured user after starting.
- `LDClient.isInitialized` which can be used to determine whether the SDK has has received the most recent flag values after starting.
- Added the ability to configure the limit to the number of users to cache the flag values for on device. This limit can be configured with `LDConfigBuilder.maxCachedUsers`.

### Changed
- `LDConfigBuilder` setters have had the `set` prefix removed, e.g. `LDConfigBuilder.setOffline` has become `LDConfigBuilder.offline`.
- `LDClient.isOnline` has been replaced with `LDClient.isOffline` for consistency with other LaunchDarkly SDKs.

## [0.2.0] - 2021-09-24
This is a breaking beta release. The changelog may not detail all changes between beta releases. The SDK is considered to be an unsupported beta until release 1.0.0.

### Added
- Added the `alias` method to `LDClient`. This can be used to associate two user objects for analytics purposes with an alias event.
- Added the `autoAliasingOptOut` configuration option. This can be used to control the new automatic aliasing behavior of the `identify` method; by setting `autoAliasingOptOut` to `true`. `identify` will not automatically generate alias events.
- The SDK now supports the ability to control the proportion of traffic allocation to an experiment. This works in conjunction with a new platform feature now available to early access customers.

### Changed
- The SDK implementation is now null-safe.
- The minimum Flutter version has been raised to 2.0.0.
- The minimum Dart version has been raised to 2.12.0.
- The minimum supported Android API version has changed from 16 to 21.
- The underlying SDK on Android has been updated to 3.1.1 from 2.13.0. See the [Android SDK changelog](https://github.com/launchdarkly/android-client-sdk/releases) for details on improvements.
- The underlying SDK on iOS has been updated from 5.2.0 to 5.4.3. See the [iOS SDK changelog](https://github.com/launchdarkly/ios-client-sdk/releases) for details on improvements.
- The `identify` method will now automatically generate an alias event when switching from an anonymous to a known user. This event associates the two users for analytics purposes as they most likely represent a single person.

## [0.1.0] - 2020-10-29
This is the first public release of the LaunchDarkly Flutter client-side SDK. The SDK is considered to be an unsupported beta until release 1.0.0.

### Added
- Support for configuring and initializing a SDK instance.
- Flag evaluation with and without details.
- Retrieving all flag values for the current user.
- Switching users with `identify`.
- Flag change listeners and flags received listeners.
