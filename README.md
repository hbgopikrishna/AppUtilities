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
   6.ServiceAndJobSchedulerUtils - related to service start ,stop running status and job scheduler 
   7.StringUtils - will have methods related to string & it's opertaions
   8.ValidationUtils - some useful validations will be there in this
   ```
# How it works?

In our Activity/Fragment we can use any of the above classes.

For example

# BitmapUtils

Convert drawable into Bitmap.

```kotlin
   BitmapUtils.drawableToBitmap(drawable: Drawable) // convert drawable to bitmap and will return it
```
To get Mutable Bitmap.

```kotlin
   BitmapUtils.getMutableBitMap(bitmap: Bitmap) // convert bitmap to mutable bitmap and will return it
```

To get base64 string from Bitmap.

```kotlin
   BitmapUtils.getBase64FromBitmap(bitmap: Bitmap) // it will convert bitmap to base64 string and return 
```

To rotate the given Bitmap.

```kotlin
   BitmapUtils.rotateBitmap(
        mContext: Context,
        mBit: Bitmap,
        imagePath: String?
    ) // it will rotate the given bitmap and return it
```

To resize the Image.

```kotlin
   BitmapUtils.getResizeImage(
        mContext: Context,
        scalingLogic: ScalingUtilities.ScalingLogic, // Either crop or fit
        rotationNeeded: Boolean, // need to roatate or not
        mCurrentPhotoPath: String,
        width: Int, // required width
        height: Int // required height
    ) // it will rotate the given image and return the bitmap 
```

# CommonUtils

To show the keyboard.

```kotlin
   CommonUtils.showKeyboard(activity: AppCompatActivity)
```

To hide the keyboard.

```kotlin
   CommonUtils.hideKeyboard(activity: AppCompatActivity)
```
To show the keyboard for a view.

```kotlin
   CommonUtils.showKeyboard(activity: AppCompatActivity, view: View)
```

To hide the keyboard of a view.

```kotlin
   CommonUtils.hideKeyboard(activity: AppCompatActivity?, view: View?)
```

To get the status bar height.

```kotlin
   CommonUtils.getStatusBarHeight(activity: AppCompatActivity) // This will return the height of the status bar
```

To convert dp into pixel.

```kotlin
   CommonUtils.convertDpToPixel(
        sizeInDp: Int,
        context: Context
    ) // This will convert dp value in to pixel and return it
```

To get device name.

```kotlin
   CommonUtils.getDeviceName() // This will return device name as HTC One (M8)
```


To navigate user to playstore to check whether we have any update or not.

```kotlin
   CommonUtils.navigateToPlayStore(activity: AppCompatActivity)
```

To get random instant value.

```kotlin
   CommonUtils.getRandomInstantValue() // This will return int random value
```

To check permission granted or not.

```kotlin
   CommonUtils.isPermissionGranted(
   activity: AppCompatActivity?, 
   permission: String? //permission which we required to check is granted or not
   ) // This will return true or false by checking the permission status
```

To share string or text using Intent.

```kotlin
   CommonUtils.shareTextIntent(
        context: Context,
        shareText: String? // A string to share
    )
```

# DateTimeUtils

To get current date time in required format. 

```kotlin
   DateTimeUtils.getCurrentDateTime(
        requiredDateFormat: String?
    ) // This will return current date time string in the required date format 
```

To get the date string of one format from another format date string. 

```kotlin
   DateTimeUtils.getDateStringFromDateString(
        dateString: String?, // Input date value
        dateFormat: String?, // Input date value format
        requiredDateFormat: String?, // Required date format
        setTimeZone: Boolean, // boolean value to set the timezone to date or not
        timeZone: String? // timezone to add the date value
    ) // This will return the date time string in the required date format from another format
```

To get the date string of one format from another format date string with locale. 

```kotlin
   DateTimeUtils.getDateStringFromDateStringWithLocale(
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
   DateTimeUtils.getDateStringFromDate(
        date: Long,
        requiredDateFormat: String?
    ) // This will return date time string in the required date format 
```

To check whether two dates are belongs to same month or not. 

```kotlin
   DateTimeUtils.isSameMonthDates(
        dateFormat: String?, // date format to check dates
        monthOne: String?, // value of first date to check
        monthTwo: String? // value of second date to check
    ) // This will check both dates are in same month and will return true or false
```

To check whether two dates are belongs to same year or not. 

```kotlin
   DateTimeUtils.isSameYearDates(
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
   PopupUtils.showMessage(
        activity: AppCompatActivity,
        message: String?
    )
```

To show message to user using toast.

```kotlin
   PopupUtils.showToastMessage(
        context: Context?,
        message: String?
    )
```

To show message to user using snackbar 
for AppCompatEditText.

```kotlin
   PopupUtils.showSnackBar(editText: AppCompatEditText, message: String)
```

To show message to user using snackbar using CoordinatorLayout.

```kotlin
   PopupUtils.showSnackBar(layout: CoordinatorLayout, message: String)
```

To show message to user using snackbar using LinearLayout.

```kotlin
   PopupUtils.showSnackBar(layout: LinearLayout, message: String)
```


To show message to user using snackbar using RelativeLayout.

```kotlin
   PopupUtils.showSnackBar(layout: RelativeLayout, message: String)
```

To show message to user using snackbar using FrameLayout.

```kotlin
   PopupUtils.showSnackBar(layout: FrameLayout, message: String)
```

# ServiceAndJobSchedulerUtils

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

To schedule a job.

```kotlin
   ServiceAndJobSchedulerUtils.scheduleJob(
        context: Context,
        serviceClass: Class<*>
    ) 
```

# StringUtils

Here this is used to check whether the passed string is empty or non-empty or null.

```kotlin
   StringUtils.isEmpty(data: String?) // This will return true or flase based on string 
```

Here this is used to used to Capitalize the given string.

```kotlin
   StringUtils.capitalize(capString: String?) // This will captilize and return the string
```


# ValidationUtils

Here this is used to check whether the phone number is valid or not MOBILE REGEX.

```kotlin
   ValidationUtils.isValidPhoneNumber(mobileNumber: String?) // This will return true or false based on given mobile number
```

Here this is used to check whether the email is valid or not EMAIL REGEX.

```kotlin
   ValidationUtils.isValidEmail(email: String?) // This will return true or false based on given email
```

# EmojiExcludeFilter

If you want to exclude the emojis you can use this filter. Below is the usage for the same in activity or fragment


```kotlin
   YourEditTextHere.setFilters(arrayOf<InputFilter>(EmojiExcludeFilter))
```

