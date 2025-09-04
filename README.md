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
    - [Variables](#Variables)
        - [Event Construct Console](#event-construct-console)
        - [Clear Console](#clear-console)
        - [Set Console Input Text](#set-console-input-text)
        - [Get Console Font Size](#get-console-font-size)
        - [Get Input Value From Index](#get-input-value-from-index)
        - [Get Input Message](#get-input-message)

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
Make sure the your console widget is located inside the Content folder. If it's not in the Content folder, it won't appear in the **Select Widget** menu.<br/>
However, it will still work if you manually enter your widget's path and name (in the format path/to/widget/WidgetName) into the **Console Widget Path** field.

https://github.com/user-attachments/assets/c4f985ca-7b3d-466b-937c-5b3e33dbbf75

- ## Console Interface

![ConsoleInterface](https://github.com/user-attachments/assets/8593e175-29f7-45a8-8995-9290c3baa858)

- # Variables
![Variables](https://github.com/user-attachments/assets/d1b427e6-e184-4ea0-8631-a786e7e0e5c0)
1) ## Event Construct Console
![EventConstructConsole](https://github.com/user-attachments/assets/52bfd5b3-815b-4a5e-9312-46c14a354bcb)<br/>
You can't use the Event Construct node inside the Custom Debug Console widget. Instead, you need to use the **Event Construct Console** node.

2) ## Clear Console
![ClearConsole](https://github.com/user-attachments/assets/ffa14697-822c-4910-a08a-ebc4cfb3de0e)<br/>
Clears the console.

3) ## Set Console Input Text
![SetConsoleInputText](https://github.com/user-attachments/assets/675a801b-b79c-46b5-987d-500d09946835)<br/>
Sets the console input text.

4) ## Get Console Font Size
![GetConsoleFontSize](https://github.com/user-attachments/assets/bf089161-28d7-4dc1-a3b9-2345219362eb)<br/>
Returns the font size value set in the **Console Interface**. Accessible from all Blueprints.

5) ## Get Input Value From Index
![GetInputValueFromIndex](https://github.com/user-attachments/assets/94166217-1d2b-4564-9823-4bcd2666802b)<br/>
This node gets the value from a specific line of the input.

6) ## Get Input Message
![GetInputMessage](https://github.com/user-attachments/assets/cd1d7fff-d131-4ae1-bdb4-a153b0049ede)<br/>
This node removes the command at the very start of the input (index 0) and returns the rest of the sentence. In the example above you can see the difference between this and **Input Committed**.

7) ## Print Console
![PrintConsole](https://github.com/user-attachments/assets/72503d6a-e4d4-4e8d-8ae8-ef4fc3798f77)<br/>
Print Console adds all entered messages to the console. Accessible from all Blueprints.
- **Text Type**: There are three color options: Default, Warning, and Error. These colors can be changed through the **Console Interface**.
- **Tooltip Text**: The text entered here will be displayed when the mouse hovers over the message.
- **Key**: If any word other than `None` is entered here, the message will switch to refresh mode. This mode can be stopped using the **Stop Print Console** node. Below are two different usage examples.<br/>
:warning: Warning: This feature only works with nodes such as **Event Tick** or **Set Timer by Event** etc. Also, the Key value is <ins>unique</ins> — if two different Print Console nodes share the same key, it will cause a conflict.
- **Print to Log**: The entered message is also printed to Unreal Engine’s own console.

![PrintConsoleExample1](https://github.com/user-attachments/assets/07cba1fc-2cfc-420d-a04c-eb8c4a40a602)<br/>
![PrintConsoleExample2](https://github.com/user-attachments/assets/fc95db16-4fa7-4c59-855d-f55310f658fa)

8) ## Broadcast Console
![BroadcastConsole](https://github.com/user-attachments/assets/11d90e14-d70c-4913-9378-3ead727757a3)<br/>
Broadcast Console sends the entered message to everyone in the session. Accessible from all Blueprints.<br/>
It has 2 modes:
- **Only The Host Can Broadcast**: Only the host (server) can send messages to everyone.
- **Everyone Can Broadcast**: Anyone can send messages to everyone. Works like a simple chat system.

9) ## Function List
![FunctionList](https://github.com/user-attachments/assets/2c3b8ae5-99ec-4969-a868-d90df01ef7a4)<br/>
Function List stores all functions added to the console along with their parameters and descriptions.<br/>
You can use it like in the example below — it will print all of your functions to the console.<br/>
![FunctionListExample](https://github.com/user-attachments/assets/09392cc6-0eb4-49d8-8445-eaba4b7ea7dc)

10) ## Add Child To Console Log
![AddChildToConsoleLog](https://github.com/user-attachments/assets/b6017bf0-41cd-4433-bec4-8842c408021a)<br/>
This node allows you to add a User Widget into the console. (<ins>Experimental</ins>)<br/>
- You can use an image to create a table, but remember: the console automatically adds spacing between all messages. Because of this, you should first build your table inside the User Widget, then add that table to the console.<br/>

:warning: Warning: Interactive objects (like buttons) inside the User Widget will not work, and some widget features may not display correctly.<br/>
:information_source: For the curious: When a User Widget is added to the console, it is converted from User Widget → Slate Widget. Because of this, not all features carry over correctly, and interactive objects won’t work.
