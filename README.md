## Requirements
None! `pybetterloader` works out of the box and only requires built-in packages. (This may be subject to change)\
\
*However...*\
In order to take full advantage, make sure you have a [Nerd Font](https://www.nerdfonts.com) installed.


## `Loader` Class

### Description
The `Loader` class provides a context manager for displaying loading animations with customizable features. It offers various loading animations and witty remarks during the loading process, making it an engaging tool for indicating progress.

---

### Initialization Parameters

- **description** (str): A string indicating the message displayed during loading. Default is "Loading...".\
  If `quips == True`, this appears in (parenthesis).
  
- **anim** (str): The type of animation to display. Options include:
  - "braille" 
  - "hourglass" *
  - "wifi" *
  - "circle" *
  - "battery" *
  - "hexagon" *
  - "cellular1" *
  - "cellular2" \*\
**Note:**
Options marked with a "*" indicate that the animations requires a [Nerd Font](https://www.nerdfonts.com) to be installed
  
- **end** (str): The message displayed upon completion of the loading process. Default is "Done!".

- **color** (tuple): RGB tuple specifying the color of the loading animation. Default is white `(255, 255, 255)`.

- **timeout** (float): The duration in seconds between each frame of the animation. Default is `0.2` seconds.

- **remark_timeout** (int): The interval in iterations between displaying witty remarks during loading. Default is `40`.

- **quips** (bool): A flag indicating whether to display witty remarks during loading. Default is `True`.

---

### Usage

```python
from pybetterloader.Loader import Loader

# Create a Loader instance with default settings
with Loader() as loader:
    # Your loading task here

# You can also create a Loader instance without using a context manager
loader = Loader()
loader.start()
# Processes here
loader.stop()

# Customizing loader settings
with Loader(description="Processing...", anim="braille", quips=False) as loader:
    # Output: ⢿ Processing...
    # Your loading task here
```
---

### Methods

- **start()**: Starts the loading animation in a separate thread.

- **stop()**: Stops the loading animation and displays the completion message.

---

### Examples

```python
from pybetterloader.Loader import Loader

# Customizing loader settings
with Loader(description="Processing", anim="wifi", color=(0, 255, 0), quips=False) as loader:
    # Your loading task here
```

## Credits

- **Author**: sudo-matcha
- **Version**: 1.0.1
- **License**: GNU GPL v3

## Support

For any issues or queries, please [open an issue](https://github.com/sudo-matcha/pybetterloader/issues). Contributions are welcome!
