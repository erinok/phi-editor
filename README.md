<p align="center"><img src="res/icons/icon96.png"></p>

<h1>phi-editor</h1>
Phi is a minimal text editor designed to look pretty, run fast, and be easy
to configure and use. It's primary function is for editing code. 

Note that this is a work in progress and is very buggy! The editor is written as if it's a game,
so it will probably **eat up your battery**, as well as **run possibly quite slow** - especially
if you dont have a dedicated GPU - and probably **crash frequently**.

Do not edit your precious files with this editor!

<br>

Here's a screenshot of the editor:

<p align="center"><img src="screenshot.png"></p>

# goals
The editor must:

* run fast;
* load and edit large files with ease;
* look pretty; and finally
* be easy to use 

# building
You'll need Go with the GOPATH, GOBIN, etc. setup, as well as SDL2, SDL2\_image, and SDL2\_ttf. Here's
an example for Ubuntu:

```bash
$ sudo apt-get install libsdl2-dev libsdl2-image-dev libsdl2-ttf-dev
$ go get github.com/felixangell/phi-editor
$ cd $GOPATH/src/github.com/felixangell/phi-editor
$ go build
$ ./phi-editor
```

If you're on macOS, you can do something like this, using homebrew:

```bash
$ brew install sdl2 sdl2_image sdl2_ttf
$ go get github.com/felixangell/phi-editor
$ cd $GOPATH/src/github.com/felixangell/phi-editor
$ go build
$ ./phi-editor
```

If you're on windows, you have my condolences.

## configuration
Configuration files are stored in `$HOME/.phi-editor-editor/config.toml`. Note that 
this directory is created on first startup by the editor, as well as the configuration
files in the 'cfg/' directory are pre-loaded dependening on platform: see 'cfg/linuxconfig.go', for example.

Below is a (non-exhaustive) configuration file to give you an
idea of what the config files are like:

```toml
[editor]
tab_size = 4
hungry_backspace = true
tabs_are_spaces = true
match_braces = false
maintain_indentation = true
highlight_line = true

[render]
aliased = true
accelerated = true
throttle_cpu_usage = true
always_render = true

[theme]
background = 0x002649
foreground = 0xf2f4f6
cursor = 0xf2f4f6
cursor_invert = 0x000000

[cursor]
flash_rate = 400
reset_delay = 400
draw = true
flash = true

[commands]
[commands.save]
shortcut = "super+s"

[commands.delete_line]
shortcut = "super+d"
```

# license
[MIT License](/LICENSE)
