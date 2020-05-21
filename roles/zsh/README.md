# ZSH

This role installs zsh with an additional theme, fonts and settings.
This configuration also includes the shell plugin manager [antibody](https://getantibody.github.io/).

## Theme

The theme used is the [powerline theme](https://github.com/romkatv/powerlevel10k) with a custom configuration.

## Fonts

The [nerd-fonts JetBrainsMono](https://github.com/ryanoasis/nerd-fonts/releases/download/v2.1.0/JetBrainsMono.zip) font will be used
for the Powerline to work properly.

This font needs to be enabled on the terminal that is used. This needs to be done manually.

## Configuration options

| Option         | Type    | Default     | Description                                                                            |
|----------------|---------|-------------|----------------------------------------------------------------------------------------|
| zsh_language   | String  | en_US.UTF-8 | The language that will be set for the shell.                                           |
| zsh_enable_svn | boolean | true        | True if the powerline theme should show a dedicated symbol for svn repository folders. |
| zsh_fonts      | boolean | true        | True if the fonts for the powerline theme should be installed.                         |