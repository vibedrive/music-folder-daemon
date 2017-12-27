# managed-folder

class that creates subfolders inside a given folder and 
emits a namespaced event when a change happens inside any of them.

currently handles 3 types of events: `add`, `remove`, `change`.
can be passed a map of namespace to folder name as an option. 

```js
// default subfolder map (namespace -> folder name)
{
  inbox: 'Inbox'
}
```

### usage

```js
var opts = {
  appdir: '/Users/kareniel/Vibedrive',
  subfolders: { inbox: 'Inbox' }
}

var folder = musicfolder(opts)

folder.on('inbox:add', function (filepath) {
  console.log('file added to inbox folder:', filepath)
})
```

if used from the command line you can pass opts either 

1. through cli arguments

```bash
node managed-folder --appdir /Users/kareniel/Vibedrive
```

or

2. with a config file (`/.config`)

```
appdir=/Users/kareniel/Vibedrive
```
