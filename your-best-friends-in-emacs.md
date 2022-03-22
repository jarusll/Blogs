---
title: Your best friends in Emacs
date: "2022-03-14"
---
# Your best friends in Emacs

## In emacs, You are either
- Invoking a function through a key press
- Invoking a function manually

## Describe Mode[^emacs-modes] `C-h m`
Describe mode gives you a list of all enabled Minor modes, functions in the major mode & all their key binds.

I skim through `describe-mode` the first time I am using a mode. 
The functions are generally named as `namespace-like`-`action-like`-`something-else`. 
I remember the pattern so I can type out these functions with some autocompletion engine[^completion-engine]. 
I lookup the keybind for that action as well, after using it for a couple of times it becomes second nature.

## Describe Function `C-h f`
Describe function brings up the documentation about a function by name.

I use this almost everytime to find out about a function.

## Describe Key `C-h k`
Describe key gives you the command associated with the key/chord in current mode.

I use this to find the function associated with a key/chord.

## Describe Variable `C-h v`
Describe variable brings up the documentation about a variable by name.

I rarely use this as I am not an advanced user. But its good to have for customization.

## Where is?
The `where-is` function returns you the keybind of a function. Use it when you want to know the function but not its keybind.

## Completion engine & Minibuffer goodies
I would recommend any completion engine which works out for you.

I like expanded minibuffer so I can see suggestions at a time.

I personally use `ivy` because it comes with expanded minibuffer. There are many options for completion engines but an expanded minibuffer is very nice to have.

## Keycast mode
This mode shows the keychord & the associated function on the modeline.
I like having this so I can learn emacs. Totally optional but a nice to have.

## Why best friends?
I believe that one of the biggest difference between a professional and a beginner is that the professional has gotten comfortable in an environment which is pretty hostile to them.

If you foster exploration[^xah-emacs-guide] for yourself, you can get comfortable really fast. 

Godspeed

[^xah-emacs-guide]: http://xahlee.info/emacs/index.html
[^emacs-modes]: https://www.gnu.org/software/emacs/manual/html_node/emacs/Modes.html
[^completion-engine]: https://www.reddit.com/r/emacs/comments/n40lk8/poll_whats_your_ideal_minibuffer_completion_ui
