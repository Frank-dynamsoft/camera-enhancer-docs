---
layout: default-layout
title: Dynamsoft Camera Enhancer - License initialization
description: This is the documentation - License initialization page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, License initialization
needAutoGenerateSidebar: true
breadcrumbText: License Initialization
---

# License initialization

> NOTE
>
> The JavaScript edition doesn't require a license as of version 2.0.3.
>
> The method `initLicenseFromDLS` and `DMDLSSettingParameters` are no longer available from version 2.0.
>
> To initialize the license for 2.0 or higher versions, please use the new license item illustrated on this page.

## Get a trial key

- A 7-day public trial key is available for every new device for first use of Dynamsoft Camera Enhancer. The public trial key is the default key used in samples. You can also find the public trial key on the following parts of this page.
- If your free key is expired, please visit <a href="https://www.dynamsoft.com/customer/license/trialLicense?product=dce" target="_blank">Private Trial License Page</a> to get a 30-day trial extension.

## Get a full license

- [Contact us](https://www.dynamsoft.com/company/contact/)  to purchase a full license

## Initialize the license

The following code snippets are using the public trial key to initialize the license. You can replace the public trial key with your own license key.

**Android Code Snippet**

```java
// The string "DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9" here will grant you a public trial license good for 7 days.
// After that, please visit: https://www.dynamsoft.com/customer/license/trialLicense?product=dce to request for 30 days extension.
CameraEnhancer.initLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9", new DCELicenseVerificationListener() {
    @Override
    public void DCELicenseVerificationCallback(boolean b, Exception e) {
        if(!b && e != null){
            e.printStackTrace();
        }
    }
});
```

**Objective-C Code Snippet**

```objc
// The string "DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9" here will grant you a public trial license good for 7 days.
// After that, please visit: https://www.dynamsoft.com/customer/license/trialLicense?product=dce to request for 30 days extension.
[DynamsoftCameraEnhancer initLicense:@"DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9" verificationDelegate:self];
- (void)DCELicenseVerificationCallback:(bool)isSuccess error:(NSError *)error{
}
```

**Swift Code Snippet**

```swift
// The string "DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9" here will grant you a public trial license good for 7 days.
// After that, please visit: https://www.dynamsoft.com/customer/license/trialLicense?product=dce to request for 30 days extension.
DynamsoftCameraEnhancer.initLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9",verificationDelegate:self)
func dceLicenseVerificationCallback(_ isSuccess: Bool, error: Error?) {
}
```

## Optional Codes -- Display License Verification Message on the UI

You can add the following code to the `DCELicenseVerificationCallback` to display the error message on the UI when the license verification is failed.

**Android Code Snippet**

```java
CameraEnhancer.initLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9", new DCELicenseVerificationListener() {
    @Override
    public void DCELicenseVerificationCallback(boolean isSuccess, final Exception e) {
        if (!isSuccess) {
            e.printStackTrace();
            MainActivity.this.runOnUiThread(new Runnable() {
                @Override
                public void run() {
                    Toast ts = Toast.makeText(getBaseContext(), "error:"+((CameraEnhancerException)e).getErrorCode()+ " "+((CameraEnhancerException)e).getMessage(), Toast.LENGTH_LONG);
                    ts.show();
                }
            });
        }
    }
});
```

**Objective-C Code Snippet**

```objc
[DynamsoftCameraEnhancer initLicense:@"DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9" verificationDelegate:self];
- (void)DCELicenseVerificationCallback:(bool)isSuccess error:(NSError *)error{
    if(error != nil){
        dispatch_async(dispatch_get_main_queue(), ^{
            UIAlertController *alert = [UIAlertController alertControllerWithTitle:@"Server license verify failed" message:error.userInfo[NSUnderlyingErrorKey] preferredStyle:UIAlertControllerStyleAlert];
            [alert addAction:[UIAlertAction actionWithTitle:@"OK" style:UIAlertActionStyleDefault handler:nil]];
            [self presentViewController:alert animated:YES completion:nil];
        });
    }
}
```

**Swift Code Snippet**

```swift
DynamsoftCameraEnhancer.initLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9",verificationDelegate:self)
func dceLicenseVerificationCallback(_ isSuccess: Bool, error: Error?) {
    let err = error as NSError?
    if(error != nil){
        DispatchQueue.main.async {
            let alert = UIAlertController(title: "Server license verify failed", message: err!.userInfo[NSUnderlyingErrorKey] as? String, preferredStyle: .alert)
            alert.addAction(UIAlertAction(title: "OK", style: .default, handler: nil))
            self.present(alert, animated: true, completion: nil)
        }
    }
}
```
