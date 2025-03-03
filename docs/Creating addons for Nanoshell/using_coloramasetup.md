# Using coloramasetup

This guide will help you understand how to use the `coloramasetup.py` library in your Nanoshell addons. This library provides utilities that help your addons maintain consistency with the overall user experience.

It is highly recommended that you have read the **Creating addons** guide before continuing with this guide.

## Brief Summary
 
**Coloramasetup (`bin/coloramasetup.py`)** provides color variables, including a customizable accent color, to ensure that addons adhere to the user’s color preferences.

## Importing the Library

To use the functionalities provided by Coloramasetup, you'll need to import them into your addon scripts.

Access the color variables from `coloramasetup.py` by importing them as follows:

```python
from bin.coloramasetup import a as accentColor, r as resetColor
```

By importing these libraries, you can now use the provided variables and colors in your addon to create a more integrated and user-friendly experience.

!!! tip
    It is a good practice to only import the variables you need from the library instead of importing all of them, most of which you won't use anyway.

## Coloramasetup (`coloramasetup.py`)

The `coloramasetup.py` file, located in the `bin/` directory, provides several color variables that can be used to style text in your addons. This includes a user-configurable accent color, which ensures consistency with the user's preferences.

### Available Colors

- `white`
- `dim`
- `bright`
- `green`
- `light_green`
- `red`
- `r`: Resets the text color to the default terminal color.
- `a`: The user-configurable accent color.

### Example Usage

```python
from bin.coloramasetup import a as accentColor, r as resetColor

def addonMain(prompt):
    print(f"{accentColor}This text will be in the accent color.{resetColor} And this text will be reset to the default color.")
```

## Best Practices

- **Color Consistency**: Use the colors from `coloramasetup.py` to ensure that your addon aligns with the user’s color preferences. This will create a consistent and cohesive user experience across all addons.

## Updating and Reloading

Remember that Coloramasetup is updated only at startup or when Nanoshell is reloaded using the `reload` command. If a user changes the accent color for example, they will be prompted to reload Nanoshell to apply these changes.
