# AppUtilities  - A collection of some useful utilities in our applications

# Use Case

1. If you want to perform some operations related to dates , strings you can use this library
2. This library has following utils as of now

   ```javascript
   1.BitmapUtils - will have some functionalities or wide range of useful methods related to BITMAP are there in this
   2.CommonUtils - will have most common useful methods covered in this
   3.DateTimeUtils - is the class which contains methods related to Date operations
   4.PopupUtils - contains different types of message showing options to the users
   5.FragmentUtils - contains fragment related functionalities and methods
   6.ServiceUtils - related to service start ,stop running status 
   7.StringUtils - will have methods related to string & it's opertaions
   8.ValidationUtils - some useful validations will be there in this
   9.FileExtensionUtils - some useful utilis related to files
   10.FileExtensionUtils - file related methods
   11.ImageExtensionUtils - image files related methods
   12.UnitTypeUtility - unit type conversion methods
   13.ViewUtils - related to views
   ```
# How it works?

In our Activity/Fragment we can use any of the above classes.

For example

# BitmapUtils

Convert drawable into Bitmap.

```kotlin
   drawableToBitmap(drawable: Drawable) // convert drawable to bitmap and will return it
```
To get Mutable Bitmap.

```kotlin
   getMutableBitMap(bitmap: Bitmap) // convert bitmap to mutable bitmap and will return it
```

To get base64 string from Bitmap.

```kotlin
   getBase64FromBitmap(bitmap: Bitmap) // it will convert bitmap to base64 string and return 
```

To rotate the given Bitmap.

```kotlin
   rotateBitmap(
        mContext: Context,
        mBit: Bitmap,
        imagePath: String?
    ) // it will rotate the given bitmap and return it
```

To resize the Image.

```kotlin
   getResizeImage(
        mContext: Context,
        scalingLogic: ScalingUtilities.ScalingLogic, // Either crop or fit
        rotationNeeded: Boolean, // need to roatate or not
        mCurrentPhotoPath: String,
        width: Int, // required width
        height: Int // required height
    ) // it will rotate the given image and return the bitmap 
```

# CommonUtils

To show the keyboard.To check whether my service is running or not.

```kotlin
   ServiceAndJobSchedulerUtils.isMyServiceRunning(
        activity: AppCompatActivity,
        serviceClass: Class<*>
    ) //  This will check the service is running or not and return true or false based on service status
```
To start required service.

```kotlin
   ServiceAndJobSchedulerUtils.startRequiredService(
        activity: AppCompatActivity,
        serviceClass: Class<*>
    ) 
```

```kotlin
   AppCompatActivity.showKeyboard()
```

To hide the keyboard.

```kotlin
   AppCompatActivity.hideKeyboard()
```
To show the keyboard for a view.

```kotlin
   AppCompatActivity.showKeyboard(view: View)
```

To hide the keyboard of a view.

```kotlin
   AppCompatActivity.hideKeyboard(view: View?)
```

To get the status bar height.To check whether my service is running or not.

```kotlin
   ServiceAndJobSchedulerUtils.isMyServiceRunning(
        activity: AppCompatActivity,
        serviceClass: Class<*>
    ) //  This will check the service is running or not and return true or false based on service status
```
To start required service.

```kotlin
   ServiceAndJobSchedulerUtils.startRequiredService(
        activity: AppCompatActivity,
        serviceClass: Class<*>
    ) 
```

```kotlin
   AppCompatActivity.getStatusBarHeight() // This will return the height of the status bar
```

To convert dp into pixel.

```kotlin
   Context.convertDpToPixel(
    sizeInDp: Int
   ) // This will convert dp value in to pixel and return it
```

To get device name.

```kotlin
   getDeviceName() // This will return device name as HTC One (M8)
```


To navigate user to playstore to check whether we have any update or not.

```kotlin
   AppCompatActivity.navigateToPlayStore()
```

To share string or text using Intent.

```kotlin
   CommonUtils.shareTextIntent(
        context: Context,
        shareText: String? // A string to share
    )
```

To check network is available or not.

```kotlin
   Context.isNetworkAvailable() // Retun true if network is available or else return false
```

To trim the text in AppCompatEditText.

```kotlin
   AppCompatEditText?.getTrimText()
```

To open application settings.

```kotlin
   AppCompatActivity.openApplicationSettings()
```

To set light status bar.

```kotlin
   AppCompatActivity.setLightStatusBar(view: View, @ColorRes color: Int)
```

To set status bar color.

```kotlin
   AppCompatActivity.setStatusBarColor(@ColorRes color: Int)
```

# DateTimeUtils

To get current date time in required format. 

```kotlin
   getCurrentDateTime(
        requiredDateFormat: String?
    ) // This will return current date time string in the required date format 
```

To get the date string of one format from another format date string. 

```kotlin
   getDateStringFromDateString(
        dateString: String?, // Input date value
        dateFormat: String?, // Input date value format
        requiredDateFormat: String?, // Required date format
        setTimeZone: Boolean, // boolean value to set the timezone to date or not
        timeZone: String? // timezone to add the date value
    ) // This will return the date time string in the required date format from another format
```

To get the date string of one format from another format date string with locale. 

```kotlin
   getDateStringFromDateStringWithLocale(
        dateString: String?, // Input date value
        dateFormat: String?, // Input date value format
        requiredDateFormat: String?, // Required date format
        setTimeZone: Boolean, // boolean value to set the timezone to date or not
        timeZone: String? // timezone to add the date value
        locale: Locale?, // Input locale value
        requiredLocale: Locale? // Output or required date locale value
    ) // This will return the date time string in the required date format from another format
```

To get the date string. 

```kotlin
   getDateStringFromDate(
        date: Long,
        requiredDateFormat: String?
    ) // This will return date time string in the required date format 
```

To check whether two dates are belongs to same month or not. 

```kotlin
   isSameMonthDates(
        dateFormat: String?, // date format to check dates
        monthOne: String?, // value of first date to check
        monthTwo: String? // value of second date to check
    ) // This will check both dates are in same month and will return true or false
```

To check whether two dates are belongs to same year or not. 

```kotlin
   isSameYearDates(
        dateFormat: String?, // date format to check dates
        yearOne: String?, // value of first date to check
        yearTwo: String? // value of second date to check
    ) // This will check both dates are in same year and will return true or false
```

# FragmentUtils

  To Replaces existing fragment with a [Fragment], that gets instantiated from `clazz` with optional `fragmentBundle` attached.

```kotlin
    FragmentUtils.replace(
        activity: AppCompatActivity, // Hosting activity
        @IdRes frameResId: Int, // Layout id where fragment should be placed
        clazz: Class<*>, // Fragment's class that should be instantiated
        fragmentBundle: Bundle?, // This bundle gets supplied to the fragment
        addToBackStack: Boolean, // If true transaction would be added to back stack.
        tag: String? // Fragment transaction's tag
    )
```

 To Replace existing fragment with `fragment`.
     
 ```kotlin
    FragmentUtils.replace(
        activity: AppCompatActivity, // Hosting activity
        @IdRes frameResId: Int, // Layout id where fragment should be placed
        fragment: Fragment?, // Fragment instance
        addToBackStack: Boolean, // If true transaction would be added to back stack.
        tag: String? // Fragment transaction's tag
    )
 ```
 
 To Replace existing fragment with `fragment`applying animation.
     
 ```kotlin
    FragmentUtils.replaceWithAnim(
        activity: AppCompatActivity,
        @IdRes frameResId: Int,
        fragment: Fragment?,
        addToBackStack: Boolean,
        tag: String?,
        @AnimRes animIn: Int, // Animation In 
        @AnimRes animOut: Int // Animation Out
    )
 ```
 
   To Replaces existing fragment with a [Fragment], that gets instantiated from `clazz` with optional `fragmentBundle` attached.
     
 ```kotlin
    FragmentUtils.add(
        activity: AppCompatActivity, // Hosting activity
        @IdRes frameResId: Int, // Layout id where fragment should be placed
        clazz: Class<*>, // Fragment's class that should be instantiated
        fragmentBundle: Bundle?, // This bundle gets supplied to the fragment
        addToBackStack: Boolean, // If true transaction would be added to back stack.
        tag: String? // Fragment transaction's tag
    )
 ```
 
 Pops off the last fragment in the provided activity's stack.
     
 ```kotlin
    FragmentUtils.pop(activity: AppCompatActivity)
 ```
 
 Add `fragment` as a child to `rootFragment`.
     
 ```kotlin
    FragmentUtils.addChild(
        rootFragment: Fragment,
        @IdRes frameResId: Int,
        fragment: Fragment?,
        addToBackStack: Boolean,
        tag: String?
    )
 ```
 
 Replace `fragment` as a child to `rootFragment`.
     
 ```kotlin
    FragmentUtils.replaceChild(
        rootFragment: Fragment,
        @IdRes frameResId: Int,
        fragment: Fragment?,
        addToBackStack: Boolean,
        tag: String?
    )
 ```
 
 Searches for child fragment in `fragment` by provided `tag`.
     
 ```kotlin
    FragmentUtils.findChildByTag(
        fragment: Fragment,
        tag: String
    ) // It will return the fragment 
 ```
 
 Searches for fragment in [FragmentManager] by provided `tag`.
     
 ```kotlin
    FragmentUtils.findByTag(
        activity: AppCompatActivity,
        tag: String
    ) // It will return the fragment 
 ```
 
 Searches for fragment in [FragmentManager] by provided `id`.
     
 ```kotlin
    FragmentUtils.findById(
        activity: AppCompatActivity,
        @IdRes id: Int
    ) // It will return the fragment 
 ```
 
 Display the dialog, adding the fragment to the given FragmentManager.
     
 ```kotlin
    FragmentUtils.showDialog(
        activity: AppCompatActivity,
        dialogFragment: DialogFragment
    )
 ```
 
 Removes fragment with tag **`tag`** from `activity`'s fragment manager if there is such fragment.
     
 ```kotlin
    FragmentUtils.removeByTag(activity: AppCompatActivity, tag: String) //  Returns True  if fragment is removed. False otherwise.
 ```
 
 Removes fragment with id **`id`** from `activity`'s fragment manager if there is such fragment.
     
 ```kotlin
    FragmentUtils.removeById(activity: AppCompatActivity, @IdRes id: Int) //  Returns True  if fragment is removed. False otherwise.
 ```
 
 Shows the `fragment`.
     
 ```kotlin
    FragmentUtils.show(
        activity: AppCompatActivity,
        fragment: Fragment?
    )
 ```
 
 Hides the `fragment`.
     
 ```kotlin
    FragmentUtils.hide(
        activity: AppCompatActivity,
        fragment: Fragment?
    )
 ```
 
  Hides the `hide` fragment and shows the `show` fragment.
     
 ```kotlin
    FragmentUtils.hideAndShow(
        activity: AppCompatActivity,
        hide: Fragment?,
        show: Fragment?
    )
 ```
 
 Hides the `hide` fragment and shows the `show` fragment with animations.
     
 ```kotlin
    FragmentUtils.hideAndShowWithAnimation(
        activity: AppCompatActivity,
        hide: Fragment?,
        show: Fragment?,
        @AnimRes animIn: Int,
        @AnimRes animOut: Int
    )
 ```
 
# PopupUtils

To show message to user using dialog.

```kotlin
   AppCompatActivity.showDialogMessage(message: String?)
```

To show message to user using toast.

```kotlin
   String.showToast(context: Context?)
```

# ServiceUtils

To check whether my service is running or not.

```kotlin
   ServiceAndJobSchedulerUtils.isMyServiceRunning(
        activity: AppCompatActivity,
        serviceClass: Class<*>
    ) //  This will check the service is running or not and return true or false based on service status
```
To start required service.

```kotlin
   ServiceAndJobSchedulerUtils.startRequiredService(
        activity: AppCompatActivity,
        serviceClass: Class<*>
    ) 
```

# StringUtils

Here this is used to check whether the passed string is empty or non-empty or null.

```kotlin
   isEmpty(data: String?) // This will return true or flase based on string 
```

Here this is used to used to Capitalize the given string.

```kotlin
   capitalize(capString: String?) // This will captilize and return the string
```


# ValidationUtils

Here this is used to check whether the phone number is valid or not using MOBILE REGEX.

```kotlin
   String.isValidPhoneNumber() // This will return true or false based on given mobile number
```

Here this is used to check whether the email is valid or not using EMAIL REGEX.

```kotlin
   String.isValidEmail() // This will return true or false based on given email
```
Here this is used to check whether the password is strong or not.

```kotlin
   String.isValidStrongPassword() // This will return true or false based on given email
```

# FileExtensionUtils

To get Root path.

```kotlin
   AppCompatActivity.getRootPath(directoryName: String, folderName: String)
```

To get Root directory.

```kotlin
   Context.getRootDirectory(directoryName: String, folderName: String)
```

To delete file.

```kotlin
   File.deleteFile()
```

# ImageExtensionUtils

To load image.

```kotlin
   ImageView.loadImage(url: String, placeHolder: Int = -1)
```

To get MimeType of file using path.

```kotlin
   String.getMimeType()
```

# UnitTypeUtility

To convert meter to foot.

```kotlin
   meterToFoot(meter: Float)
```

To convert foot to meter.

```kotlin
   footToMeter(foot: Float)
```

To convert cm to meter.

```kotlin
   cmToMeter(cm: Float)
```

To convert inches to foot.

```kotlin
   inchesToFoot(foot: Float)
```

To convert kg to lbs.

```kotlin
   kgToLbs(kg: Float)
```

To convert lbs to kg.

```kotlin
   lbsToKg(lbs: Float)
```

# ViewUtils

To set view visibility .

```kotlin
   View.setVisible(visible: Boolean)
```

To set view invisible.

```kotlin
   View.setInVisible()
```
