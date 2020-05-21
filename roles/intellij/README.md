# IntelliJ 

This role installs IntelliJ and creates a bin link to the executable.

## IntelliJ settings

Since IntelliJ does not provide a CLI to install plugins etc. 
No settings/plugin configuration will be made.

## Configuration options

| Option           | Type       | Default  | Description                                                        |
|------------------|------------|----------|--------------------------------------------------------------------|
| intellij_version | String     | 2020.1.1 | The IntelliJ Version you want to Install.                          |
| intellij_edition | 'U' or 'C' | 'U'      | Set to 'U' for Ultimate edition. Set to 'C' for Community edition. |