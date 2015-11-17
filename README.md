# discord-hotkey-forwarder

This is a bash script that uses `xdotool` and `xbindkeys` to provide global
push-to-talk keybind functionality for [discord-linux][].

```shell-session
./discord-hotkey-forwarder listen <global hotkey> <discord hotkey>
```

## Hotkey Identifiers

You can use `xbindkeys --key` to find the identifier for a keyboard combination.

If you want to use a mouse button, `xev` can tell you the button number.

## Example

```shell-session
$ ./discord-hotkey-forwarder listen "b:9" "grave"
sending "grave" to discord when you press "b:9"
```

`b:9` is what most people call <kbd>mouse 4</kbd>.

`grave` is the <kbd>\`</kbd> key.

## Caveats

[discord-linux][] ignores keypresses unless its window is focused, so this
script temporarily focuses it when forwarding keys. This will briefly prevent
any input to your current window from working.

When you're in a [Dota 2][dota2] game, xbindkeys won't work.

[discord-linux]: <https://github.com/XNBlank/discord-linux>
[dota2]: <https://www.dota2.com>
