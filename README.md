![64px](https://user-images.githubusercontent.com/38810169/39779582-714ffdf6-532b-11e8-8976-3cca95092005.jpg)

#DEPRECATED

### Credits for the logo goes to Hafiz Ahmmed (https://github.com/hafizahmmed)

# ColorBox library

[ ![Download](https://api.bintray.com/packages/enricod/colorbox/cbl/images/download.svg?version=1.1.1) ](https://bintray.com/enricod/colorbox/cbl/1.1.1/link)
[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-ColorBox-red.svg?style=flat)](https://android-arsenal.com/details/1/6579)
[![API](https://img.shields.io/badge/API-21%2B-orange.svg?style=flat)](https://android-arsenal.com/api?level=21)


### Features

- Dynamic color preview;
- Change the color through **A**lpha, **R**ed, **G**reen, and **B**lue sliders;
- Clearable recent colors;
- Material palettes (>200 colors!);
- ColorBox preference;
- Themes (Light, Dark, Black);
- Easy to implement;



![ScreenShot](https://github.com/enricocid/ColorBox-library/blob/master/files/art.png)
------

# Sample Project

*You can download the latest sample APK from this repo here:* https://github.com/enricocid/ColorBox-library/blob/master/files/release/app-release.apk



# Gradle Dependency

### Repository

*The Gradle dependency is available via [jCenter](https://bintray.com/enricod/Enrico/ColorBox-library/view).
jCenter is the default Maven repository used by Android Studio.*

*The minimum API level supported by this library is API 21 (Lollipop).*

### Download

- If You are using gradle:3.0+ You should use '*implementation*' configuration. Add the following dependency to your project's build.gradle:

```gradle
dependencies {
    // ... other dependencies here
    implementation 'com.github.enricocid:cbl:1.1.1'
}
```

- For gradle versions < 3.0 use 'compile' configuration:

```gradle
dependencies {
    // ... other dependencies here
    compile 'com.github.enricocid:cbl:1.1.1'
}
```




# Usage

### To display the color box simply:

```java
ColorBox.showColorBox(String tag, Activity activity, int theme);
```


**tag:** it's a string used to identify the ColorBox.

**theme:** Possible values are:

![ScreenShot](https://github.com/enricocid/ColorBox-library/blob/master/files/themes.png)

- ColorBox.LIGHT;
- ColorBox.DARK;
- ColorBox.BLACK;

# Usage instructions for Preferences

![ScreenShot](https://github.com/enricocid/ColorBox-library/blob/master/files/preferences.png)

*In Your preferences XML add:*

```xml
<com.github.colorbox.ColorBoxPreference android:key="the_key_u_want" android:title="@string/your_string"/>
```

**note:** don't forget to add a (different) key and a title for every ColorBoxPreference You add in Your preferences XML.

You can set the theme of the ColorBox by adding the *setTheme* attribute. The possible values are 1 and 2. The default value is 0, corresponding to the light theme (You don't need to specify this attribute if You want to keep the light theme).

- For Dark theme (1):

```xml
<com.github.colorbox.ColorBoxPreference
app:setTheme="1"
android:key="the_key_u_want" android:title="@string/your_string"/>
```

- For Black theme (2):

```xml
<com.github.colorbox.ColorBoxPreference 
app:setTheme="2"
android:key="the_key_u_want" android:title="@string/your_string"/>
```

*In You Preference fragment (onResume) add this*

```java
@Override
    public void onResume() {
        super.onResume();

        ColorBox.registerPreferenceUpdater(Activity activity);
    }
```

# To retrieve the color:

```java
int color = ColorBox.getColor(String tag, Context context);
```





# Utilities:

### ColorBox.getComplementaryColor(int colorToInvert)

*Returns inverted color:*

![ScreenShot](https://github.com/enricocid/ColorBox-library/blob/master/files/inverted.png)





### ColorBox.getHexadecimal(int color)

*Returns the hexadecimal code from color.*





### ColorBox.isColorDark(int color)

*Determine if the color is dark or light.*




# THAT'S ALL FOLKS!



