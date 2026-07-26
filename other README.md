# modDisplayName

readMeDescription

A brief description of your mod.
It should cover the following points:

- What your mod is
- What it provides
- Any important notes for users

Anything more detailed should go in the documentation.

You should probably put a disclaimer if your mod is in early development or has known issues.
A disclaimer also applies if your mod is incompatible with other mods, or for platforms like mobile.

# Requirements/Dependencies

A list of dependencies for your mod. If there are no dependencies, you can remove this section.

# Installation

Steps to install your mod.
You can alternatively link to a separate installation guide if it is long or complex.

# Documentation

See the [documentation](LINK HERE) for detailed information.

# Changelog

See the [changelog](LINK HERE) document for a list of changes.

# Contributing

Please see the [contributing guidelines](LINK HERE) for more information.

# Forum Post

[Join the discussion on the forums](LINK HERE).

# Social Media

## Discord

[Join the Discord server](discordLink).

# License

See the [LICENSE](LICENSE) file for details.

# Variables for templating (in order of appearance in the template)

## csproj

- assemblyName: defaults to modNameId
- autoCopyMod (whether to copy the dll to the mod folder after build): defaults to false

## Main.cs

- rootNamespace: defaults to modNameId
- modNameId: required
- modDisplayName: defaults to modNameId
- author: defaults to nothing
- minimumGameVersion: defaults to 1.6.00.18
- modVersion: defaults to 1.0.0
- modDescription: defaults to nothing
- updateLink: defaults to nothing, comments the update section

## License (for those other than GPL)

- licenseType
  - options: MIT, LGPL (v3), GPL (v3), AGPL (v3), apache2.0, mozilla2.0, unlicense
- copyrightYear: defaults to the current year if not specified
- copyrightHolder: defaults to the author if not specified

## Git

- gitUsername: defaults to the authorName if not specified
- git (whether to run `git init`): defaults to true
