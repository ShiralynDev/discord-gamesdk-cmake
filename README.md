# Discord GameSDK for CMake
A better integration of Discord's Legacy SDK for CMake-based projects

## Overview
With the release of Discord GameSDK, a few integrations of bringing it to CMake
projects has been overwhelmingly painful. As a result, this was created for a better integration.

## How to Use
Clone this repository as a sub-module of your Git repository.

### Extracting GameSDK libraries
Grab Discord GameSDK [here](https://dl-game-sdk.discordapp.net/3.2.1/discord_game_sdk.zip),
extract the contents of the `lib/x86_64` folder and paste it to this project's `lib` folder.

>[!NOTE]
>The `lib` folder is not included by default, you must do it yourself.

>[!IMPORTANT]
> Contents may vary depending on your selected machine architecture.
>
> For example, if your machine is 32-bit, you may copy files from `lib/x86` instead

### Modify your project's CMakeLists
Add these lines to your project's `CMakeLists.txt`:
```cmake
add_subdirectory(discord_gamesdk_cmake)
...
...
target_link_libraries(YOUR_TARGET
	discord_gamesdk
	...
	)
```

## Structure
 - `lib` - Where the GameSDK library files reside, read [Extracting GameSDK libraries](#extracting-gamesdk-libraries) for more information.
 - `src` - Source and header files for Discord GameSDK, which makes use of the Discord GameSDK libraries.

## License
This project is licensed under the [Unlicense](LICENSE).
