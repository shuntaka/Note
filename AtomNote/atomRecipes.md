# Set up Atom
## atom config
---
### disable welcome page on start up
[how-to-get-rid-of-atoms-welcome-screen](https://stackoverflow.com/questions/41342121/how-to-get-rid-of-atoms-welcome-screen)


## setup for proxy
---
### configure apm to use proxy
[Windows にて Atom の proxy 設定ハマリポイント](http://qiita.com/dskst/items/6153915b658433b02cd3)
[ATOMエディタのproxy設定](http://qiita.com/tsukamoto/items/cef0f2d7e2b33a26a9e5)
-   create ~/.atom/.apmrc
```sh
touch ~/.atom/.apmrc
```

-   edit .apmrc.
    -   make sure to set **http** proxy for the **https** proxy setting
    -   make sure to include the credential

```sh
https-proxy = http://tanaka.taro@tanaka.co.jp:hogepassword@proxy.tanaka.co.jp:20066
```

-   confirm the apm proxy setting
```sh
apm config get https-proxy
```

# manage packsges
## star command
---
### star already installed packages
```sh
apm star --installed
```

### stars command
-   istall stared pakcages
```sh
apm stars --install
```

# Search
---
### narrow

-   [[pAtomのnarrowパッケージが素晴らしくって単語検索から編集、置換までスムーズにできるようになった話]](http://qiita.com/KemoKemo/items/86c2868d98d8e58740be)

# Replace
---
### multi cursor for find all
[find-and-replace](https://github.com/atom/find-and-replace/pull/290
)
-   simply execute find-all


# Programming Language Support
## javascript
---
### language support
-   language-javascript by Atom
-   language-javascript-jsx by Subtle Gradient of Facebook

---
### snippets

-   [turbo-javascript](https://atom.io/packages/turbo-javascript)
-   [es6-javascript](https://atom.io/packages/es6-javascript)

## CSS
---
### language support

####


## markdown
---
### language support


---
### preview



# keymap.cson
```js
# Your keymap
#
# Atom keymaps work similarly to style sheets. Just as style sheets use
# selectors to apply styles to elements, Atom keymaps use selectors to associate
# keystrokes with events in specific contexts. Unlike style sheets however,
# each selector can only be declared once.
#
# You can create a new keybinding in this file by typing "key" and then hitting
# tab.
#
# Here's an example taken from Atom's built-in keymap:
#
# 'atom-text-editor':
#   'enter': 'editor:newline'
#
# 'atom-workspace':
#   'ctrl-shift-p': 'core:move-up'
#   'ctrl-p': 'core:move-down'
#
# You can find more information about keymaps in these guides:
# * https://atom.io/docs/latest/using-atom-basic-customization#customizing-key-bindings
# * https://atom.io/docs/latest/behind-atom-keymaps-in-depth
#
# If you're having trouble with your keybindings not working, try the
# Keybinding Resolver: `Cmd+.` on OS X and `Ctrl+.` on other platforms. See the
# Debugging Guide for more information:
# * https://atom.io/docs/latest/hacking-atom-debugging#check-the-keybindings;
#
# This file uses CoffeeScript Object Notation (CSON).
# If you are unfamiliar with CSON, you can read more about it in the
# Atom Flight Manual:
# https://atom.io/docs/latest/using-atom-basic-customization#cson

# ==============================
# specificity (0, 0, 1)
# ==============================
'body':
  'ctrl-h': 'core:backspace'
  'cmd-v': 'core:page-up'
  'ctrl-x ctrl-x': 'command-palette:toggle'
  'ctrl-p': 'core:move-up'
  'ctrl-n': 'core:move-down'
  'ctrl-m': 'core:confirm'
  'ctrl-x [': 'core:move-to-top'
  'ctrl-x ]': 'core:move-to-bottom'

'atom-workspace':
  'ctrl-0': 'nuclide-file-tree:toggle-focus'
  'ctrl-alt-0': 'nuclide-file-tree:toggle'
  'ctrl-x ctrl-f': 'advanced-open-file:toggle'

'atom-text-editor':
  'cmd-f': 'editor:move-to-end-of-word'
  'cmd-b': 'editor:move-to-beginning-of-word'
  'ctrl-a': 'editor:move-to-beginning-of-line'
  'cmd-space': 'bookmarks:toggle-bookmark' # for mac
  'cmd-[': 'bookmarks:jump-to-previous-bookmark' # for mac
  'cmd-]': 'bookmarks:jump-to-next-bookmark' # for mac
  'alt-space': 'bookmarks:toggle-bookmark' # for win
  'alt-[': 'bookmarks:jump-to-previous-bookmark' # for win
  'alt-]': 'bookmarks:jump-to-next-bookmark'
  'ctrl-s': 'narrow:scan'
  'ctrl-alt-s': 'narrow:search'
  'ctrl-cmd-s': 'narrow:search' #for mac
  'ctrl-;': 'nuclide-quick-open:find-anything-via-omni-search'

# ==============================
# specificity (0, 0, 2)
# ==============================
'atom-workspace atom-text-editor':
  'ctrl-t': 'window:focus-next-pane'
  'ctrl-m': 'editor:newline'
  'ctrl-/': 'core:undo'
  'ctrl-cmd-/': 'core:redo' #for mac
  'ctrl-alt-/': 'core:redo' #for win
  'ctrl-i': 'autocomplete-plus:activate'
  'ctrl-o': 'easy-motion-redux:letter'
  'ctrl-cmd-o': 'easy-motion-redux:letter-select' # for mac
  'ctrl-alt-o': 'easy-motion-redux:letter-select' # for win
  'ctrl-x ctrl-x': 'command-palette:toggle'
  'alt-m': 'project-find:show'

# ==============================
# specificity (0, 1, 0)
# ==============================
'.platform-darwin':
  'ctrl-\'': 'project-manager:list-projects'

'.nuclide-file-tree':
  'ctrl-x ctrl-f': 'nuclide-file-tree:add-file'
  'ctrl-g': 'nuclide-file-tree:clear-filter'
  'ctrl-p': 'core:move-up'
  'ctrl-n': 'core:move-down'
  'ctrl-m': 'nuclide-file-tree:open-selected-entry'
  'ctrl-f': 'nuclide-file-tree:expand-directory'
  'ctrl-b': 'nuclide-file-tree:collapse-directory'
  'ctrl-alt-f': 'nuclide-file-tree:recursive-expand-directory'
  'ctrl-alt-b': 'nuclide-file-tree:recursive-collapse-directory'

# ==============================
# specificity (0, 1, 1)
# ==============================
'atom-text-editor[mini]':
  'ctrl-m': 'core:confirm'

'atom-text-editor:not([mini])':
  'alt-y': 'clipboard-plus:toggle'
  'ctrl-j': 'snippets:available'


# mac
'.platform-darwin atom-workspace':
  'ctrl-cmd-;': 'fuzzy-finder:toggle-file-finder'
  'ctrl-;': 'nuclide-quick-open:find-anything-via-omni-search'
  'ctrl-x ctrl-r': 'nuclide-recent-files-provider:toggle-provider'
  'cmd-p': 'last-cursor-position:previous'
  'cmd-n': 'last-cursor-position:next'
  'cmd-i': 'goto-last-edit:back'
  'cmd-j': 'goto-last-edit:forward'
  'ctrl-\\': 'platformio-ide-terminal:toggle'

# win
'.platform-win32 atom-workspace':
  'ctrl-alt-;': 'fuzzy-finder:toggle-file-finder'
  'ctrl-;': 'nuclide-quick-open:find-anything-via-omni-search'
  'ctrl-x ctrl-r': 'nuclide-recent-files-provider:toggle-provider'
  'alt-p': 'last-cursor-position:previous'
  'alt-n': 'last-cursor-position:next'
  'alt-i': 'goto-last-edit:back'
  'alt-j': 'goto-last-edit:forward'
  'ctrl-t': 'window:focus-next-pane'

# ==============================
# specificity (0, 1, 2)
# ==============================
'body atom-text-editor.autocomplete-active':
  'ctrl-p': 'core:move-up'
  'ctrl-n': 'core:move-down'
  'ctrl-m':  'autocomplete-plus:confirm'

'atom-workspace atom-text-editor.autocomplete-active':
  'tab': 'snippets:next-tab-stop'
  'shift-tab': 'snippets:previous-tab-stop'

# for mac
'.platform-darwin atom-workspace atom-text-editor':
  'cmd-w': 'atomic-emacs:copy-region-as-kill'

# ==============================
# specificity (0, 2, 1)
# ==============================
'.select-list atom-text-editor[mini]':
  'ctrl-m': 'core:confirm'
  'ctrl-p': 'core:move-up'
  'ctrl-n': 'core:move-down'

# ==============================
# specificity (0, 3, 1)
# ==============================
# for narrow ui
'atom-text-editor.narrow.narrow-editor[data-grammar="source narrow"]':
  'ctrl-p': 'core:move-up'
  'ctrl-n': 'core:move-down'
  'ctrl-m': 'core:confirm'
  'ctrl-c ctrl-e': 'narrow-ui:start-insert'
  'ctrl-x ctrl-s': 'narrow-ui:update-real-file'

# ==============================
# specificity (0, 3, 2)
# ==============================
# '.platform-win32 atom-workspace, .platform-linux atom-workspace atom-text-editor:not([mini])':
#   'ctrl-;': 'nuclide-quick-open:find-anything-via-omni-search'
```
