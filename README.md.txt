# asset_get_stripped

Returns if an asset name doesn't exist in the game specifically because the asset has been stripped during compile due to the "Automatically remove unused assets when compiling" feature. This function will return `true` only if the asset exists in the project file but not at runtime. This means `asset_get_stripped()` will return `false` if the asset name is simply misspelled.

The asset name should be passed to this function as a string e.g. `"obj_example"` for an object called `obj_example`.

This function will only work when running the game from the IDE. When running from an executable, this function will always return `false`. Furthermore, `asset_get_stripped()` needs access to the project .yy JSON file which means this function will not work when running on a device other than your development hardware (e.g. Android, iOS, Nintendo Switch etc.). This function further requires you to untick the "Disable file system sandbox" Game Option for the platform you're running on.

Please note that (as of IDE v2024.11.0.179 / Runtime v2024.11.0.226) room assets, script assets and particle system assets do not appear to get stripped by the compiler and this function will likely always return `false` for those assets.