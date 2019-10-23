# electron-node-red

This is an Electron template to embed [Node-RED](https://nodered.org) with a Dashboard generated by node-red-dashboard to create a native application.

This is not intended to be a useful tool as-is, but as a base for you to create your own versions. You will need to edit the `main.js` to suit your application and update the `package.json` file to include your own required nodes and dependencies.

At the top of `main.js` are a couple of flags you can switch to turn off editing, allow loading of a different flow file (and save as), and add the worldmap to the menu. Again these are only there to show you possibilities. Have fun.

## To Use

This project uses the **electron-builder** project to help build native versions
of Node-RED applications, so please read and become familiar with their [documentation](https://www.electron.build/) as some basic 
knowledge is assumed.

As a pre-req, as well as a recent version of node.js, you will need the yarn install tool

```bash
# Clone this repository
git clone https://github.com/dceejay/electron-node-red.git
# Go into the repository
cd electron-node-red
# Install the yarn install tool globally
sudo npm i -g yarn
# Install project dependencies
yarn
```

## Building local runtime

You should then be able to run
```
yarn && yarn dist
```

to create a runtime for your local platform.
However - there may be some errors. If so they are usually fairly self explanatory, and may just require
installation of another npm or brew or apt package, then retry the command.

Runtimes are created in the `dist` directory under `electron-node-red`.

### Building for other platforms

Generally you can just add the required parameter to the command
```
yarn && yarn dist -w        // for windows
yarn && yarn dist -l        // for linux
yarn && yarn dist -m        // for mac
```

These will generally fail the first time through and you will need to install some extra library in order to make it
complete successfully.

The defaults are to build a `.msi` for Windows, a `.dmg` for Mac and both a `.deb` and `.rpm` for Linux.
These can be changed by editing the build section of the `package.json` file, see the
[electron-builder config docs](https://www.electron.build/configuration/configuration) for more info.

## Running localy

While developing and testing you can just run locally by running
```
npm start
```
from within the project folder.

---