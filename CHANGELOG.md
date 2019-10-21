Changelog
=========

## v3.0.0-rc.1 [2019-10-18]

__Breaking Changes:__

- Changed TaskAssignment.resolutionState from String to new AssignmentState enum type
- Changed Group.groupType from String to new GroupType enum type
- Changed Folder.allowedSharedLinkAccessLevels from [String] to new [SharedLinkAccess] enum type
- Changed File.allowedInviteeRoles from [String] to new [CollaborationRole] enum type
- Network responses with 4xx or 5xx status codes are now transformed into an API Error
- CollaborationItem changed from class to enum
- CommentItem changed from class to enum
- FolderItem changed from class to enum
- WebhookItem changed from class to enum
- TaskItem changed from class to enum
- JSON decoding errors now emit expected type
- Public method names changed to a new convention in many of the "module" classes
- Redesigned error classes and error hierarchy


__New Features and Enhancements:__

- Added Xcode 11 support (SDK builds still target iOS 11.0)
- Removed AlamoFire dependency
- Added support for Device Pins
- Added SDK Configuration URL validation
- Added SDK-level constants rootFolder and currentUser for convenience
- Added support for Collaboration Whitelist endpoints
- Added support for Retention Policy endpoints
- Added support for Tasks endpoints
- Added support for Webhooks endpoints
- Added support for Groups and Group Membership endpoints
- Added support for Legal Holds endpoints
- Added support for Terms of Service endpoints
- Added support for Terms of Service User Status endpoints
- Added support for Watermarking endpoints
- Added support for Storage Policy endpoints
- Added support for Metadata Cascade Policy endpoints
- Added support for User endpoints
- Added support for Events endpoints

- Added Error Views in Sample Apps
- Improved structure and usability of Sample Apps


## v3.0.0-alpha.3 [2019-08-29]

__Breaking Changes:__

- Changed File Entry Container "entries" from optional to not optional


__New Features and Enhancements:__

- Added support for Web Links
- Added support for Trash endpoints
- Added support for Recent Items
- Added support for File Version endpoints
- Added support for Delete File endpoint
- Added support for Chunked Upload Endpoints
- Added support for upload preflight check
- Added support for downloading a representation of a file
- Added support for custom OAuth2 Callback URL
- Added KeychainTokenStore for OAuth2SampleApp


## v3.0.0-alpha.2 [2019-08-08]

__Breaking Changes:__

- Moved some constants to different namespaces:
    * `Box.rootFolder` is now `BoxSDK.Constants.rootFolder`
    * `Box.currentUser` is now `BoxSDK.Constants.currentUser`
- Updated the arguments that `client.files.updateFileInfo()` takes for consistency with the rest of the SDK
- Changed the type of the `expiresAt` arguments in `client.files.lockFile()` from `String` to `Date`
- Removed unused arguments from `client.files.unlockFile()`
- Changed the type of the `unsharedAt` and `password` arguments of `client.files.setSharedLink()` and
  `client.folders.setSharedLink()` to accept `.null` values
- Replaced the `access`, `password`, `unsharedAt`, and `canDownload` arguments of `client.folders.updateFolder()` with
  a single `sharedLink` argument to enable setting the entire shared link field to `.null` in order to remove the
  shared link
- Replaced `client.getFavoritesCollectionId()` with `client.collections.getFavoritesCollection()`
- Removed `client.collections.addItemsToCollection()` and `client.collections.deleteItemsFromCollection()`
- Changed the result type for `client.files.addFileToFavorites()`, `client.files.addFileToCollection()`,
  `client.files.removeFileFromFavorites()`, and `client.files.removeFileFromCollection()` from `Void` to `File`
- Changed the result type for `client.folders.addFolderToFavorites()`, `client.folders.addFolderToCollection()`,
  `client.folders.removeFolderFromFavorites()`, and `client.folders.removeFolderFromCollection()` from `Void` to
  `Folder`


__New Features and Enhancements:__

- Added support for [token downscoping](./docs/usage/authentication.md#token-exchange)
- Added a `KeychainTokenStore` implementation to enable persisting authentication state on the Keychain
- The SDK now automatically clears the token store after destroying a client and revoking its tokens


## v3.0.0-alpha.1 [2019-07-25]

Initial beta release :tada: