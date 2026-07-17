
<p align="center">
	<img width="640" height="480" alt="Heroes_SDK" src="https://github.com/user-attachments/assets/ccea92f8-c40a-4642-a66f-56aa279c3d10" />
</p>

# About

This is a static helper library for Sonic Heroes. 
It provides additional functionality and utilities to enhance the development for
C++ DLL Mods. 

It is designed to be easy to use and integrate into your projects, the library has multiple
headers to edit game data including:

- Global variables
- Functions which you can call, those includes game core logic, physics, controls and more
- Structs which includes player data and game objects.
- RenderWare headers which is often used in the game logic.
- FastFunctionHook a powerful library that allows you to edit game functions, calling original and more.

If you wish to use this helper library with your DLL mod, it is recommended to add it as
a submodule to your project. This way you can easily update it and keep track of changes.

# How to use

1) Make sure to have Git installed on your system. If you don't have it, you can download it from [here](https://git-scm.com/downloads).
2) Make sure your project directory (the root folder of your C++ DLL mod) has a Git repository initialized. If you haven't done this yet, you can initialize it by running the following command in your project directory:
```bash
git init
```
3) Still from your project directory, run the following command to add Heroes SDK Plus as a submodule:
```bash
git submodule add https://github.com/Sora-yx/Heroes-SDK-Plus.git
```	
4) After adding the submodule, open your project in Visual Studio, make sure you are in 32 bits mode (x86). Then in the solution explorer, right-click on your project and select "Add" -> "Existing Project...". Navigate to the Heroes SDK Plus folder and select the file `Heroes-SDK-Plus.vcxproj`.
5) Next, you have to add the static library to your project. Right-click on your project in the solution explorer and select "Properties". Look for "Configuration" and select "All Configurations". Then go to "Configuration Properties" -> "Linker" -> "Input" and add `$(SolutionDir)bin\Heroes-SDK-Plus.lib;` to the "Additional Dependencies" field.
6) Finally, we have to make your project look for the headers of Heroes SDK Plus. In the same properties window, go to "Configuration Properties" -> "C/C++" -> "General" and add `$(SolutionDir)Heroes-SDK-Plus\Heroes-SDK-Plus;` to the "Additional Include Directories" field.
7) Apply all the changes and close the properties window. 

Now you can add the different includes such as "Heroes-Util.h" and "FastFunctionHook.hpp" and so on.

