# VS Code 

This role installs VS Code, imports settings and installs extensions.

## Settings and Extensions

If you want to use your own settings, you can replace the `settings.json` file inside the files folder with your own.
`files/extentions.txt` contains a plugin per line. Each plugin will be installed into vs code.

Since VS Code works differently on WSL, no extionsions will be install, when the `on_wsl` is set to true.

## Configuration options

| Option    | Type   | Default | Description |
|-----------|--------|---------|-------------|
|           |        |         |             |