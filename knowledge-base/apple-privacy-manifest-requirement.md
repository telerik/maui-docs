---
title: Apple Privacy Manifest 
description: Learn what changes need to be apply to your project to support the latest apple privacy policy.
type: troubleshooting
page_title: Apple’s privacy manifest policy requirements
slug: adding-apple-privacy-manifest-file-dotnet-maui-application
tags: apple, privacy, manifest, apple store, requirements, .NET MAUI
res_type: kb
---

# Apple Privacy Manifest

Apple is introducing new privacy policy for including privacy manifest files in your apps that target iOS, iPadOS, tvOS, visionOS, and watchOS platforms on the app Store. 
For more details on this policy, please review the [Privacy Manifest Files](https://developer.apple.com/documentation/bundleresources/privacy_manifest_files) article in the Apple documentation.

> As of May 1st 2024, the Apple privacy policy manifest file must be included in your apps.

## What must be included in the PrivacyInfo.xcprivacy file

The `PrivacyInfo.xcprivacy` file lists:

* The [types of data](https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_data_use_in_privacy_manifests) collected by your .NET MAUI application or any third-party SDKs.
* The reasons for using certaing [Required Reason API](https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api). 

## Add PrivacyInfo.xcprivacy file to your application

Let's review what is needed for your .NET MAUI applicatios when using Telerik .NET MAUI controls:

1. Create a `PrivacyInfo.xcprivacy` file inside the `Platforms/iOS` folder. 

2. For Telerik .NET MAUI ControlsSamples applicaton and Telerik .NET MAUI CryproTracker application we have added the following `PrivacyInfo.xcprivacy` file:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>NSPrivacyAccessedAPITypes</key>
    <array>
        <dict>
            <key>NSPrivacyAccessedAPIType</key>
            <string>NSPrivacyAccessedAPICategoryFileTimestamp</string>
            <key>NSPrivacyAccessedAPITypeReasons</key>
            <array>
                <string>C617.1</string>
            </array>
        </dict>
        <dict>
            <key>NSPrivacyAccessedAPIType</key>
            <string>NSPrivacyAccessedAPICategorySystemBootTime</string>
            <key>NSPrivacyAccessedAPITypeReasons</key>
            <array>
                <string>35F9.1</string>
            </array>
        </dict>
        <dict>
            <key>NSPrivacyAccessedAPIType</key>
            <string>NSPrivacyAccessedAPICategoryDiskSpace</string>
            <key>NSPrivacyAccessedAPITypeReasons</key>
            <array>
                <string>E174.1</string>
            </array>
        </dict>     
	    <dict>
            <key>NSPrivacyAccessedAPIType</key>
            <string>NSPrivacyAccessedAPICategoryUserDefaults</string>
            <key>NSPrivacyAccessedAPITypeReasons</key>
            <array>
                <string>CA92.1</string>
            </array>
        </dict>
    </array>
</dict>
</plist>
```

## See Also

* [Microsoft Blogs - Adding Apple Privacy Manifest Support to .NET iOS & .NET MAUI apps](https://devblogs.microsoft.com/dotnet/apple-privacy-manifest-support/)
* [Apple Documentation - Privacy Manifest Files](https://developer.apple.com/documentation/bundleresources/privacy_manifest_files)
* [Apple Documentation - Adding a Privacy Manifest File](https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/adding_a_privacy_manifest_to_your_app_or_third-party_sdk)
* [Apple Documentation - Describing Data Use in Privacy Manifest File](https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_data_use_in_privacy_manifests)
* [Apple Documentation - Describing Use of Required Reason API](https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api)