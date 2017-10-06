# Install Vapor Cloud Toolbox

The toolbox will be available through homebrew at a future date. For now, install it using the following CLI script.

## macOS

First make sure you have installed [Swift](https://docs.vapor.codes/2.0/getting-started/install-on-macos/)

```
brew install vapor
```

## Linux

First make sure you have installed [Swift](https://docs.vapor.codes/2.0/getting-started/install-on-ubuntu/)

```
sudo apt-get install vapor
```

If you get an error, you might need to remove the old toolbox with:

```
sudo apt-get remove vapor
```

## Windows

The toolbox unfortunately can't run native on Windows, since our toolbox is developed in Swift, and swift is for the moment not supported on Windows.

If you need to be able to use the Toolbox features on Windows, we suggest using Virtualbox, and installing a Ubuntu virtual machine, to run the toolbox.
To make this easier, you can set up so you can SSH into the machine.

You can also setup a Docker image to run the Toolbox through Docker.

### Unsupported features

If you are running the Toolbox in a Virtual machine, you can't open phpMyAdmin from the Toolbox, since we can't connect to the host machine browser. For this feature, use the Dashboard to access the database.
