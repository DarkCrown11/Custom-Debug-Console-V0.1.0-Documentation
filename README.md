# Custom-Debug-Console-V1.0.0-Documentation
Unreal Engine Custom Debug Console Plugin V1.0.0 Documentation

![image](https://github.com/user-attachments/assets/de989d0f-4afa-4206-b0f4-2d87f49cc86e)

## Contents
- [About](#about)
- [Warning](#warning-anchor-point)
- [Features](#features)
- [Setup](#Setup)
- [How To Use](#how-to-use)
    - [Console Widget](#console-widget)
    - [Console Interface](#console-interface)
    - [Functions](#functions)

## About
A console that you can customize and add commands from the blueprint

## :warning:Warning <a name="warning-anchor-point"></a>
- Please remember, this plugin is <ins>Experimental</ins>! You may encounter bugs, please report them to this email address "akcrowngames@gmail.com".<br/>
Also if you have a questions you can ask same email address or social media accounts @akcrowngames.
- This plugin is not compatible with only C++ projects. It is managed with blueprint.

Supported Platforms:
- Windows

## Features
- You can customize your console look from interface.
- You can create a function in a custom debug console widget and run it from the console (Simply creating a function means you are creating a command).
- You can categorize commands and add a different prefix for each category.
- Multiplayer compatible.

## Setup
After purchasing the plugin from the [FAB](https://www.fab.com/listings/c3f0a7e2-ffdd-484c-86e6-4a38934d7d06) and installing it on the engine, you can enable
the plugin in `Edit->Plugins->Installed->Custom Debug Console` and restart the engine.

https://github.com/user-attachments/assets/4e674b87-770e-48a1-b0aa-f86cae844555

After that you need to create 2 blueprints 1.GameMode 2.PlayerController and inside the your PlayerController blueprint you need to add Custom Debug Console PC Component. 
Now go to world settings and select your GameMode and PlayerController.

https://github.com/user-attachments/assets/85b24032-6425-47da-83b1-e020ec9b726d

Final step now you need to go `Window->Custom Debug Console->Save` click the Save button. Congratulations, you have completed the setup.

https://github.com/user-attachments/assets/fe681903-cf3d-45fe-aa03-715605ca27c7

# How To Use

- ## Console Widget
After opening the unreal engine, you can find the widget in the **Content Drawer**.<br/> 
`Content Drawer->Plugins->Custom Debug Console Content->Custom Debug Console` or on the left side of the content drawer click All and search Custom Debug Console.
This way you can find the custom debug console widget.<br/> 

https://github.com/user-attachments/assets/c680d97f-f5e1-414b-873d-e62995e11a39

If you want you can create your console widget .
> :warning: **The console widget you create yourself will not include any built-in functions.**<br/>

`Go Content Folder->Right Click->User Interface->Widget Blueprint->Search And Select CustomDebugConsoleParentWidget`<br/>
:warning: this is important after create your console widget you need to go `Window->Custom Debug Console->Select Your Widget->Click Save Button`.<br/>
Make sure the your console widget is located inside the Content folder. If it's not in the Content folder, it won't appear in the Select Widget menu.<br/>
However, it will still work if you manually enter your widget's path and name (in the format path/to/widget/WidgetName) into the **Console Widget Path** field.

https://github.com/user-attachments/assets/c4f985ca-7b3d-466b-937c-5b3e33dbbf75

- ## Console Interface

![ConsoleInterface](https://github.com/user-attachments/assets/8593e175-29f7-45a8-8995-9290c3baa858)

- ## Functions
