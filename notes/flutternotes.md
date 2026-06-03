## Install Flutter 
- Install Flutter extension on vs code
- CTR + P and click make new project with flutter 
- download application and set it on your environment paths

## Creating a folder 
- Make a folder called "pages" in the lib folder
- make your desired .dart file name (eg. home.dart)
- import 'package:flutter/material.dart' on the top page
- use command "stl" to create a stateless widget

# Creating a HomePage 
- Name your class in the file "HomePage"
- add to the properties debug showCheckModeBanners: false  
- Go to `main.dart` and set the value of the home property to the name of the class  `home: HomePage()`

# Concepts Learned
> Creating Fonts
> > Create a fonts folder and add the fonts inside
> > >Define the fonts inside the pubspec.yaml file
> > > >fonts:
    - family: Schyler
      fonts:
        - asset: fonts/LondrinaShadow-Regular.ttf 
          weight: 700
        - asset: fonts/RobotoMono-Italic-VariableFont_wght.tff
          weight: 500 
        - asset: fonts/RobotoMono-VariableFont_wght.tff 
          weight: 500
> > Finally use the command  `flutter pub get`  command
> > You must then define it in the main.dart file in the theme properties
> > theme: ThemeData(fontFamily: 'LondrinaShadow-Regular')
> > Then you must use title propetry in your widget to use it
> > title: Text('Hello World'), 

## Viewing the application 
- Select an emulator and run it 
- Open run the app and with F5

## Commands Used 
- Select multiple lines with: Control + Shift + D
- Select all lines with the name word to edit: Control + Shift + L
  
## CLI Used 
- `flutter create {app name}`
- `flutter pub get`

## Stateless && Stateful widgets 
- Stateless widgets can not be drawn over again while the applcation is running (immutable)
- Stateful widgets can be drawn over and over again while the application is running (mutable widgets).  

## facts 
- Android widgests are called "Material Widgets"
- IOS widgets are called "Cupertino Widgets"
# Terms 
- Widget: everything in flutter used to create something. Like an object in OOP I believe.
- Property: Widgets have properties that you can edit. (not sure if my definition is good)
- Scaffold: Provides many widgets such as Appbar, drawer, bottom navigation bar, float action button, snackbar etc. It will provide space for all your widgets to live in. 


## Errors && Bugs 

<details>
  <summary>Click to see more</summary>
  
</details>
