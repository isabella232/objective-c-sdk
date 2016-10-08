# Objective-C SDK
[![Apache 2.0](https://img.shields.io/github/license/nebula-plugins/gradle-extra-configurations-plugin.svg)](http://www.apache.org/licenses/LICENSE-2.0)

This repository houses the Objective-C SDK for Optimizely's server-side testing product, which is currently in private beta.

## Getting Started

### Requirements
* iOS 8.0+ / tvOS 9.0+
* Foundation.framework
* [JSONModel] (https://github.com/jsonmodel/jsonmodel)

### Installing the SDK

#### Cocoapod 
1. Add the following line in the Podfile:
<pre>pod 'OptimizelySDKiOS'</pre> or <pre>pod 'OptimizelySDKTVOS'</pre>

2. Run : ``` pod install ```

Futher installation instructions for Cocoapods: https://guides.cocoapods.org/using/getting-started.html

#### Carthage
1. Create a Cartfile and add the following lines:
<pre>github "optimizely/objective-c-sdk"
github "jsonmodel/jsonmodel"</pre>

2. Run: ``` carthage update ```

3. Link the OptimizelySDKCore and JSONModel frameworks to your project. Go to your project target's **Link Binary With Libraries** and drag over the following from the _Carthage/Build_ folder:  
      * OptimizelySDKiOSSDK.framework _or_ OptimizelyTVOSSDK.framework<br/> 
      * OptimizelySDKCore.framework<br/>
      * JSONModel.framework<br/>
      
4. Ensure proper bitcode-related files and dSYMs are copied when archiving by calling a Carthage build script:
      - Add a new **Run Script** phase. 
      - In the script area include: 
        ```/usr/local/bin/carthage copy-frameworks```. 
      - Add the frameworks to the **Input Files** list:<br/>
            - ```$(SRCROOT)/Carthage/Build/iOS/OptimizelySDKiOS.framework``` or      
              ```$(SRCROOT)/Carthage/Build/iOS/OptimizelySDKTVOS.framework```<br/>
            - ```$(SRCROOT)/Carthage/Build/iOS/OptimizelySDKCore.framework```<br/>
            - ```$(SRCROOT)/Carthage/Build/iOS/JSONModel.framework```<br/>

Futher installation instructions for Carthage: https://github.com/Carthage/Carthage

#### Clone Source
Clone repo and manually add source to project to build. 

### Using the SDK

See the Optimizely server-side testing [developer documentation](http://developers.optimizely.com/server/) to learn how to set
up your first custom project and use the SDK. **Please note that you must be a member of the private server-side testing beta to create custom
projects and use this SDK.**

###Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md).

