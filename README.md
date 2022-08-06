# fusion-plugin-template
This is a template for writing a Roblox Studio plugin managed with Rojo, powered by Fusion. It is complete with Foreman, Selene, StyLua, and build scripts for exporting your plugin to Roblox Studio. There's only a few things we need to do to get started.

## Create and clone repository
Click on the "Use this template" button or [right here](https://github.com/hero-ku/fusion-plugin-template/generate) to create a new repo from this template. After setting up your repository, clone it to your computer with `git clone https://github.com/hero-ku/fusion-plugin-template.git`.

## Install tooling and packages
Navigate to the newly created folder and you should see your project. To make sure everything required is installed, run `foreman install` in a terminal in the project directory. If you do not have foreman, you can install it [here](https://github.com/roblox/foreman#installation).

Next, run `wally install` in a terminal again in the project directory. You should see a `Packages` folder generated as well as `wally.lock` file.

## Install extensions
If you're using VSCode, you should get a popup to install the recommended extensions for this project. If not, the extensions you'll need to install are:

- [Rojo - Roblox Studio Sync](https://marketplace.visualstudio.com/items?itemName=evaera.vscode-rojo)
- [Roblox LSP](https://marketplace.visualstudio.com/items?itemName=Nightrains.robloxlsp)
- [Selene](https://marketplace.visualstudio.com/items?itemName=Kampfkarren.selene-vscode)
- [StyLua](https://marketplace.visualstudio.com/items?itemName=JohnnyMorganz.stylua)

I also recommend:

- [Roblox API Explorer](https://marketplace.visualstudio.com/items?itemName=evaera.roblox-api-explorer)

## Configuring the build script
Lastly, we need to configure the script which builds the plugin in our Roblox Studio plugins folder. This will be different depending on if you're using Mac or Windows. Theoretically the Mac script should work for Linux if you configure the `plugins_path` variable.

Windows:

All you need to do here is write the name of your plugin after the `plugin_name` variable. If you're using the default path for your plugins, you don't need to touch anything else. However, if you've configured an alternate path for your Studio plugins, you need to change `plugins_path` to reflect that.
```batch
set plugin_name=MyPlugin
set plugins_path=%LOCALAPPDATA%\Roblox\Plugins
```

Mac (CURRENTLY UNTESTED):

On Mac, you need to write the name of your plugin inside the string in the `plugin_name` variable. If you've configured an alternate path for your Studio plugins, just change the value of`plugins_path` to the correct directory.
```bash
plugin_name="MyPlugin"
plugins_path="~/Documents/ROBLOX/Plugins"
```

## Write your plugin
You're good to go! Run `watch.bat` or `watch.sh` depending on your corresponding operating system and begin writing your plugin. If you reload your plugins in Studio, your plugin should be there and updated with your latest code.