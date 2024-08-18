# Vim in CodeHS
Follow these steps to enable vim keybinds in CodeHS:
1. Open a CodeHS sandbox (page where you see your code)
2. Right click on the mouse, then select the Inspect button. A DevTools panel will show up, open the console tab
3. Paste the following code:
```js
ace.require("ace/lib/net").loadScript("https://rawgithub.com/ajaxorg/ace-builds/master/src-min-noconflict/keybinding-vim.js",
function() {
	e = document.querySelector(".ace_editor").env.editor;
	e.setKeyboardHandler(ace.require("ace/keyboard/vim").handler);
})
```
> Note: If you see something that says pasting is disabled, enter `allow pasting` first then retry
# How it works
CodeHS uses [ace](https://ace.c9.io/) for it's code editing interface. You can edit ace settings using the console panel. The URL inside the loadScript function is a minified javscript file that defines vim keybindings for ace. The function body enables it.  
# Features
- Vim enabled throughout all files in a sandbox
# Limitations
- Once you leave the sandbox the keybindings disappear, so you have to paste it again
