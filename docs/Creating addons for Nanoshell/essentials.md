# Creating addons

This guide will walk you through the process of creating your own addon, covering all necessary details to get your addon up and running. We'll go through the structure, the JSON configuration and the Python code, to help you understand how everything works.

## Addon Structure

Each addon in nanoshell consists of a JSON configuration file and one or more Python files. The structure typically looks like this, with `~` representing the cloned nanoshell directory:

```
~/addons/
    ├── greet/
    │   ├── greet.json
    │   └── main.py
```

### Directory and File Naming

- **Directory Name**: Should be the name of your addon.
- **JSON File**: It's good practice to name the JSON file the same as the addon directory.
- **Python Files**: Can be named anything, but it’s a good practice to have a `main.py` as the entry point.

## Creating the JSON Configuration

The JSON file contains metadata and configuration information about your addon. Here is an example and a detailed breakdown of each field:

### Example JSON

```json title="greet.json"
{
    "name": "Greet",
    "author": "YourName",
    "description": "A simple addon to greet the user.",
    "addonVersion": "1.0.0",
    "triggerCmd": "greet",
    "initFoo": "greetUser",
    "platform": "all",
    "imports": [
        ["addons.greet.main", "greetUser"]
    ]
}
```

### Fields Explained

- **name**: The name of your addon. This is how it will be identified.
- **author**: Your name or the name of the addon author. This is for attribution.
- **description**: A short description of what your addon does. This helps users understand the functionality of your addon.
- **addonVersion**: The version of your addon. **It is essential that you follow semantic versioning (e.g., `1.0.0`)** - this is so your addons can be updated easily through the built-in addonManagement tools.
- **triggerCmd**: The command users will type in nanoshell to invoke your addon. This should be unique to avoid conflicts with other addons.
- **initFoo**: The main function in your addon that will be called when the `triggerCmd` is executed. This function must be defined in your Python code.
- **platform**: Specifies the platforms your addon supports. It can be one of the following: 
    - `"all"`: Works on all operating systems.
    - `"win"`: Works only on Windows.
    - `"linux"`: Works only on Linux.
    - `"darwin"`: Works only on macOS.
- **imports**: A list of lists, where each sublist specifies:
    - The module path to your Python file.
    - The function name to import.
    
    In this example, `"addons.greet.main"` refers to the `main.py` file within the `greet` directory, and `"greetUser"` is the function to import from that file.

## Writing the Python Code

The main Python file contains the logic for your addon. Here is an example of a simple addon:

```python title="main.py"
def greetUser(prompt):
    parts = prompt.split()
    if len(parts) > 1:
        name = " ".join(parts[1:])
        print(f"Hello, {name}!")
    else:
        print("Hello! Please provide your name after the 'greet' command.")
```

### Main Function

- The main function specified in the JSON (`initFoo`) must take at least one argument, typically named `prompt`.
- The `prompt` argument contains the entire user input, allowing you to parse and handle command options.

## Understanding the `prompt` Argument

The `prompt` argument is a string that contains the entire user input. For example, if the user types `greet John Doe`, the `prompt` argument will be `greet John Doe`.

You can use string manipulation to parse the command options. Here is an example:

```python title="main.py"
def greetUser(prompt):
    parts = prompt.split()
    command = parts[0]   # This will be 'greet'
    options = parts[1:]  # This will be ['John', 'Doe']
    
    print(f"Command: {command}")
    print(f"Options: {options}")

    if options:
        name = " ".join(options)
        print(f"Hello, {name}!")
    else:
        print("Hello! Please provide your name after the 'greet' command.")
```

## Testing Your Addon

1. **Place Your Addon**: Put your addon directory inside the `~/addons` directory.
2. **Run Nanoshell**: Start nanoshell by running `python run.py` or `python3 run.py` depending on your platform.
3. **Invoke Your Addon**: Type the trigger command you specified in your JSON to test your addon. For example, `greet John Doe`.

## Publishing Your Addon

1. **Prepare Files**: Ensure your JSON and Python files are correctly formatted and contain all necessary information, and that the addon is functioning like expected.
2. **Submit a Pull Request**:
   - Fork the official `nanoshell-addons` repository.
   - Add your addon directory to your fork of the repository. The directory should contain your JSON and Python files.
   - Commit your changes and push them to your fork.
   - Create a pull request (PR) from your fork to the `nanoshell-addons` repository. Provide a detailed description of your addon in the PR.
3. **Security Verification**: The nanoshell contributors will review your addon for security and functionality.
4. **Approval and Availability**: Once your addon passes the review, it will be merged into the `nanoshell-addons` repository and become available for everyone through the nanoshell addon installer.

---

This guide should provide you with all the necessary information to create, test, and publish your own addons for nanoshell. If you have any questions or need further assistance, feel free to reach out to the nanoshell community on [Discord](https://discord.com/invite/D3cnTxg8sU). Happy coding!