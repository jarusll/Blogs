# decribe-* functions: Your best friends in Emacs

## In emacs, You are either
- Invoking a function through a key press
- Invoking a function manually

Before finding which commands are bound to key or to execute manually, we need to know what commands are available in the current mode.

## How you can find all the commands in Emacs?
	- `describe-mode`
	- Keychord `C-h m`

Describe mode gives you a list of all enabled Minor modes, functions in the major mode & all their key binds.

I usually keep a window on my bottom right corner for `describe-mode`. I skim through it for the first time. If I notice myself repeating an action, I'll lookup if there's a function/keybind for that action. After using it for a while, it becomes second nature.
