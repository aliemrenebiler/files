# Files

Static files by [Ali Emre Nebiler](https://aliemrenebiler.com).

This repository is rendered as a simple file browser with `index.html`.

## How It Works

`index.html` loads `files.json` in the browser:

```js
fetch("files.json");
```

Then it reads the folder/file structure from that JSON and builds the visible file tree. File links are generated automatically from their parent folders, so each file only needs a `name` and `type`.

## How To Add Content

To change what appears on the page, edit `files.json`.

Use `type: "folder"` for folders:

```json
{
  "name": "folder-name",
  "type": "folder",
  "children": []
}
```

Use `type: "file"` for files:

```json
{
  "name": "file-name.png",
  "type": "file"
}
```

For example, this structure:

```json
[
  {
    "name": "project-1",
    "type": "folder",
    "children": [
      {
        "name": "images",
        "type": "folder",
        "children": [
          {
            "name": "image-1.png",
            "type": "file"
          }
        ]
      }
    ]
  }
]
```

Creates this link:

```text
project-1/images/image-1.png
```

## Notes

- Add or remove visible files by editing `files.json`.
- Keep the actual files in the same folders described by `files.json`.
- You do not need to edit `index.html` unless you want to change the page design or behavior.
