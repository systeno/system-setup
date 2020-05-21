# LilyPond

This role installs LilyPond with additional fonts and libraries.

## Fonts

The fonts that will be installed are: 
* msttcorefonts
* Beethoven font
* All fonts in the configured backblaze repository.

The backblaze repository expects a bucket which contains `.zip` files.
These `.zip` files should each contain one or more folders that will be extracted into a
lilypond accessible fonts directory.

## Libraries

The fonts that will be installed are: 
* [opendlilylib/snippets](https://github.com/openlilylib/snippets.git)
* [pdq](https://github.com/codello/pdq.git)
* [guitar_bends](https://gitlab.com/till-personal/lilypond/guitar_bends.git)

Since LilyPond does not have a dedicated library directory or package manager, 
the installation path of these libraries can be configured.


## Configuration options

| Option                       | Type   | Default                      | Description                                                               |
|------------------------------|--------|------------------------------|---------------------------------------------------------------------------|
| lilypond_font_keyID          | String | false                        | The keyID to your backblaze repository or false to not configure          |
| lilypond_font_applicationKey | String | false                        | The applicationKey to your backblaze repository or false to not configure |
| lilypond_font_bucket         | String | false                        | The name of your backblaze bucket or false to not configure               |
| lilypond_version             | String | 2.20.0                       | The LilyPond version you want to install                                  |
| lilypond_lib_path            | String | {{ home_path }}/LilyPond/Lib | The path to your LilyPond libraries.                                      |