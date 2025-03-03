# Installing and uninstalling addons

Addons are an essential part of nanoshell - they give you new commands and functions to use to improve your experience. It is very simple to both install and uninstall addons.

## Installing addons

### Method 1 - Using the Addon installer

The simplest way of installing addons is via the **Addon installer**, which is a part of the **built-in** addonManagement addon.

To install an addon, simply run the following command in your nanoshell instance:
```
addons install
```

This will list all available addons from the repository. All you have to do is write the name of the addon you'd like to install, and press enter. The addon will install automatically.

!!! tip
    In case you already know the name of the addon you wish to install, you can specify it in the command and it will be installed immediately.
    ```
    addons install addonName
    ```

Before you start using the new commands from your addon(s), you have to reload your nanoshell instance:
```
reload
```

After this, your newly installed addon(s) will be ready for use.

### Method 2 - Manually installing addons

In case you're unable to use the built-in Addon installer, you can manually install addons.

To do this, download the [official addon repository](https://github.com/wiktorkono/nanoshell-addons) as a zip file. After you've downloaded it, extract it to a folder.

In the extracted folder, you'll be able to find many directories:
```
nanoshell-addons/
  ├── Calculator
  ├── Disklist
  ├── ...
```

Each directory represents an addon in the repository. Find the one you wish to install and cut or copy that directory. Paste it to your nanoshell instance's addons folder:

```
~/addons/
    ├── newlyInstalledAddon/
```
_**~** represents the root of your nanoshell instance_

!!! warning
    While you can install any addon you find on the web using this method, **it is recommended to only install addons from the official repository** to avoid security risks.

    Installing **unknown addons** from the web can be **dangerous** as they can contain **malicious code**.

After you've copied the addon into the right place, you can delete the repository zip as well as the extracted folder.

You can now launch nanoshell and use new commands from the addon you've installed.

!!! note
    If you did this while you had a nanoshell instance running, you have to reload it before you can use the new commands:
    ```
    reload
    ```

## Uninstalling addons

### Method 1 - Using the Addon uninstaller

Just like the Addon installer, the **Addon uninstaller** is also a part of the **built-in** addonManagement addon.

To uninstall an addon, simply run the following command in your nanoshell instance:
```
addons uninstall
```

This will list all installed addons. All you have to do is write the name of the addon you'd like to uninstall, and press enter. The addon will uninstall automatically.

!!! tip
    In case you already know the name of the addon you wish to uninstall, you can specify it in the command and it will be uninstalled immediately.
    ```
    addons uninstall addonName
    ```

It is recommended to reload your nanoshell instance after uninstalling addons to avoid any unexpected issues:
```
reload
```

### Method 2 - Manually uninstalling addons

In case you're unable to use the built-in Addon uninstaller, you can manually uninstall addons.

To do this, navigate to your nanoshell instance's addons folder:

```
~/addons/
    ├── firstAddon/
    ├── secondAddon/
    ├── ...
```
_**~** represents the root of your nanoshell instance_

Find the folder that matches the name of the addon you wish to uninstall. Delete that folder. The addon will now be uninstalled.

!!! note
    If you did this while you had a nanoshell instance running, it is recommended that you reload it to avoid unexpected issues:
    ```
    reload
    ```