# Discord GameSDK for CMake
A minimal CMake subproject that powers Discord GameSDK for everyone.

## How to use?
Clone it as a git submodule of your project, or something else.

Modify your project's `CMakeLists.txt`:
```cmake
add_subdirectory(discord_gamesdk_cmake)
... 
...
target_link_libraries(YOUR_TARGET
	discord
	...
	)
```

## Structure
 - `lib` - Where it's imported libraries reside, read [lib/README.md](lib/README.md) for more info.
 - `src` - Source and header files for Discord GameSDK, which makes use of the imported libraries.

## `discord` target
It is a wrapper for the imported `discord_game_sdk` libraries. The source and header files are compiled into what would `discord` be generated.

### Renaming the `discord` target
You might want to rename it because it's not looking fit for your project.

Simply replace these lines in the library's `CMakeLists.txt`:
- Line 6:
	- `set(DISCORD_GAMESDK_BIN_RUNTIME "${CMAKE_CURRENT_BINARY_DIR}/YOURNAME.dll" PARENT_SCOPE)`
- Line 45:
	- `set(DISCORD_GAMESDK_BIN_RUNTIME "${CMAKE_CURRENT_BINARY_DIR}/YOURNAME.so" PARENT_SCOPE)`
	- *Note: This can be optional if you're depending on Windows only*

## How to obtain the libraries?
Read [lib/README.md](lib/README.md#how-to-get-them)