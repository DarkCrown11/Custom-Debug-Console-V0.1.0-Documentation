# Custom-Debug-Console-V0.1.0-Documentation
Unreal Engine Custom Debug Console Plugin V0.1.0 Documentation

![image](https://github.com/user-attachments/assets/de989d0f-4afa-4206-b0f4-2d87f49cc86e)

## Contents
- [About](#about)
- [Warning](#warning-anchor-point)
- [Features](#features)
- [Setup](#Setup)
- [How To Use](#how-to-use)
    - [Console Widget](#console-widget)
        - [How To Create Command](#how-to-create-command)
    - [Console Interface](#console-interface)
    - [Nodes](#nodes)
        - [Event Construct Console](#event-construct-console)
        - [Clear Console](#clear-console)
        - [Set Console Input Text](#set-console-input-text)
        - [Get Console Font Size](#get-console-font-size)
        - [Get Input Value From Index](#get-input-value-from-index)
        - [Get Input Message](#get-input-message)
        - [Print Console](#print-console)
        - [Broadcast Console](#broadcast-console)
        - [Get Function List](#get-function-list)
        - [Add Child To Console Log](#add-child-to-console-log)
    - [Examples](#examples)

## About
A console that you can customize and add commands from the blueprint

## :warning:Warning <a name="warning-anchor-point"></a>
- Please remember, this plugin is <ins>Beta</ins>! You may encounter bugs, please report them on [Discord](https://discord.gg/zQNzDdxnTr).<br/>
Also if you have a questions you can ask the discord or social media accounts @akcrowngames.<br/>
If you have a picture or video, It may take me less time to fix this.
- This plugin is not compatible with only C++ projects. It is managed with blueprint.
- This console is designed for host-based listen server multiplayer or singleplayer game modes.
Compatibility with dedicated servers has not been tested, and I believe it will not work properly there.
- Since I don’t know much about console security, there may be risks to your game files. Because of this, I recommend not using it in dedicated server based multiplayer games and removing the plugin from your game once it reaches the shipping stage.<br/>
(This is just a suggestion. I'm not sure if the console poses a security risk yet.)
- Your Custom Debug Console Save file location `Your Project File->Config->CustomDebugConsoleSave`.

Supported Platforms:
- Windows

## Features
- You can customize your console look from interface.
- You can create a function in a custom debug console widget and run it from the console (Simply creating a function means you are creating a command).
- You can categorize commands and add a different prefix for each category.
- Multiplayer compatible.

## Setup
- After purchasing the plugin from the [FAB](https://www.fab.com/listings/c3f0a7e2-ffdd-484c-86e6-4a38934d7d06) and installing it on the engine, you can enable
the plugin in `Edit->Plugins->Console->Custom Debug Console` and restart the engine.
- After that you need to create 2 blueprints 1.GameMode 2.PlayerController and inside the your PlayerController blueprint you need to add Custom Debug Console PC Component.<br/>
Then click `Custom Debug Console PC->Widget Class-> Select Custom Debug Console`. Now go to world settings and select your GameMode and PlayerController.
- Final step now you need to go `Window->Custom Debug Console->Save` click the Save button. Congratulations, you have completed the setup.

https://github.com/user-attachments/assets/8eb58ec4-545e-45c7-a0ec-2e4b52ff8fbd

# How To Use

- ## Console Widget
After opening the unreal engine, you can find the widget in the **Content Drawer**. There is two way to find.<br/> 
First way `Content Drawer->Click Gear Icon->Enable Engine Content And Plugin Content->Engine->Plugins->Custom Debug Console Content->Custom Debug Console`.<br/>
Second way  `Click All->Search Custom Debug Console`. This way you can find the custom debug console widget.<br/> 

https://github.com/user-attachments/assets/7f255ff7-271f-4e52-821b-2440f367780a

If you want you can create your console widget .
> :warning: **The console widget you create yourself will not include any built-in functions.**<br/>

Go `Content Folder->Right Click->User Interface->Widget Blueprint->Search And Select CustomDebugConsoleParentWidget`<br/>
:warning: this is important after create your console widget you need to go `Your PlayerController->Click CustomDebugConsolePC->Widget Class->Select Your Console Widget`.<br/>
Then go `Window->Custom Debug Console->Save` click the Save button.

https://github.com/user-attachments/assets/e3bbeee3-1dd4-4f8e-8bce-21df16ae008d

- ## How To Create Command
Functions you create inside the **Custom Debug Console Widget** are added to the console as commands.<br/>
:warning: Before you start, keep these in mind:<br/>
- Function names cannot contain spaces.
- You cannot use the symbols `~` or `¿` in the function category name, function name, parameter name, or description.
- When you add, delete, or rename a function, you must go to the **Console Interface** and click **Save**.

![AllWariables](https://github.com/user-attachments/assets/8b971352-3607-4204-93e6-a031c8dddef8)<br/>
The image above shows all variable types that a function can use.<br/>
To create a command:
1) First, create a function inside the **Custom Debug Console Widget**.
2) Add this function to a category.
3) Go to the **Console Interface** and carefully enter the exact name of the category you added your function to in the **Category Name** field under **Function Categories**, then click **Save**.
4) If you also add a value in the Prefix field, this prefix will be added to the beginning of all function names in that category.

The variables you add under Inputs in the function’s Details panel will automatically become the function’s parameters, and the text you write in the Description field will automatically appear as the function’s description.

https://github.com/user-attachments/assets/a662f66c-8a92-440f-85c1-4de99afdaebf

- ## Console Interface
![ConsoleInterface](https://github.com/user-attachments/assets/473aaaa0-417f-48fe-9b95-4afd833fe21e)<br/>
You can customize the console however you like by adjusting the settings. Here are some important ones to know:<br/>
1) **Console Widget Path**: Enter the path of a User Widget that has the **Custom Debug Console Parent Widget** here.
If the widget is in the Content folder, it will appear when you click **Select Widget**.
If it’s elsewhere, you can manually enter the widget path and name in this format: path/to/widget/WidgetName.
2) **Console Key**: Set which key opens and closes the console. Numbers cannot be used. If the chosen key has another function in the editor, the previous function will be disabled.
3) **Function Categories**: When adding functions to the console inside the Custom Debug Console Widget, enter the categories in Category Name, paying attention to uppercase and lowercase letters.
If you add a prefix, it will be added to the beginning of all function names in that category.<br/>
:warning: You cannot use the symbols `~` or `¿` in this field.
4) **Multiplayer Server-Client Separation**: This only works in PIE (Play In Editor) mode. When you add a message with the **Print Console** node, it will prepend “server” if it’s the host or “client” if it’s the client.
5) **Warnings**: The console has automatic warning messages. You can change them or translate them to your language.
- `{ParamName}` shows which parameter caused the error.
- `{UserValue}` shows the value entered by the user.<br/>

Include these placeholders in your custom messages to keep the functionality.

- # Nodes
![Variables](https://github.com/user-attachments/assets/13b7598f-840e-4866-8553-58a3ae5da4c7)
1) ## Event Construct Console
![EventConstructConsole](https://github.com/user-attachments/assets/52bfd5b3-815b-4a5e-9312-46c14a354bcb)<br/>
You can't use the Event Construct node inside the Custom Debug Console widget. Instead, you need to use the **Event Construct Console** node.

2) ## Clear Console
![ClearConsole](https://github.com/user-attachments/assets/ffa14697-822c-4910-a08a-ebc4cfb3de0e)<br/>
Clears the console.

3) ## Set Console Input Text
![SetConsoleInputText](https://github.com/user-attachments/assets/a16f1898-af77-47b6-a03b-2bcdebc2df7f)<br/>
Sets the console input text. Accessible from all Blueprints.

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

9) ## Get Function List
![GetFunctionList](https://github.com/user-attachments/assets/c3ac3e00-3012-463e-97cb-564ab1ecaede)<br/>
Function List stores all functions added to the console along with their parameters and descriptions.<br/>
You can use it like in the example below — it will print all of your functions to the console.<br/>
![FunctionListExample](https://github.com/user-attachments/assets/024aa811-5613-4ce6-a582-7a77a11ac92c)

10) ## Add Child To Console Log
![AddChildToConsoleLog](https://github.com/user-attachments/assets/b6017bf0-41cd-4433-bec4-8842c408021a)<br/>
This node allows you to add a User Widget into the console. (<ins>Experimental</ins>)<br/>
- You can use an image to create a table, but remember: the console automatically adds spacing between all messages. Because of this, you should first build your table inside the User Widget, then add that table to the console.<br/>

:warning: Warning: Some user widget features may not display correctly.<br/>
:information_source: For the curious: When a User Widget is added to the console, it is converted from User Widget → Slate Widget. Because of this, not all features carry over correctly.

# Examples
- ## Function List And Add Child To Console Log
[![Watch the video](https://img.youtube.com/vi/LguLhET2mH8/hqdefault.jpg)](https://www.youtube.com/embed/LguLhET2mH8)

https://github.com/user-attachments/assets/e4661b57-1f91-4c65-8d17-6263f3bb8f59
