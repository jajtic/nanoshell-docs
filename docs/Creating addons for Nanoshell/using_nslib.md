# Using the Nanoshell Library

This guide will help you understand how to use the `nanoshell_lib.py` library in your Nanoshell addons. This library provides essential information and utilities that help your addons function better.

It is highly recommended that you have read the **Creating addons** guide before continuing with this guide.

## Brief Summary

The **Nanoshell Library (`bin/nanoshell_lib.py`)** stores key information about the Nanoshell environment, such as the current version, system platform, and the number of installed addons and scripts. 

## Importing the Library

To use the functionalities provided by the Library, you'll need to import them into your addon scripts.

Access the Nanoshell Library by simply importing the variables you need from `nanoshell_lib.py` like this:

```python
from bin.nanoshell_lib import versionStr, systemPlatform
```

By importing this library, you can now use the provided variables in your addon to create a more integrated experience.

!!! tip
    It is a good practice to only import the functions or/and variables you need from the library instead of importing all of them, most of which you won't use anyway.

## The Nanoshell Library (`nanoshell_lib.py`)

The Nanoshell Library is a collection of variables that provide crucial information about the Nanoshell environment. It is located in the `bin/` directory and can be imported into your addons to access this data.

### Available Variables

- `versionStr`: A string representing the current version of Nanoshell.
- `systemPlatform`: The platform on which Nanoshell is running (`win`, `linux`, `darwin`).
- `addonCount`: The total number of addons installed.
- `addonScriptCount`: The total number of addon scripts available.
- `linuxDistroName`: If the system is running Linux, this will be the distro name (e.g. `arch`). Otherwise, it will be `Unavailable`.

### Example Usage

To use the Nanoshell Library in your addon, import the variables you need and utilize them in your functions.

```python
from bin.nanoshell_lib import systemPlatform, versionStr

def addonMain(prompt):
    print(f"Nanoshell Version: {versionStr}")
    print(f"System Platform: {systemPlatform}")

```

``` title="Example output"
Nanoshell Version: 0.1.5
System Platform: linux
```
## Best Practices

- **Leverage Existing Data**: Instead of re-implementing functionality that the Nanoshell Library already provides, use the existing variables to simplify your code. For instance, use `systemPlatform` from the Nanoshell Library instead of writing your own platform detection code.

## Updating and Reloading

Remember that the Nanoshell Library is updated only at startup or when Nanoshell is reloaded using the `reload` command. If a user installs new addons, they will be prompted to reload Nanoshell to apply these changes.
