# Pelican Plugin CookieCutter Template

This project’s purpose is to make it easy to create new Pelican plugins via a [CookieCutter][] template, as well as keeping generated plugins updated and in sync with template changes via [Cruft][].

## Requirements

**Option 1**: Install [Cruft][] via its [installation instructions](https://cruft.github.io/cruft/#installation).

**Option 2**: Install [Pipx][] and prefix the `cruft` commands below with: `pipx run [...]`

The latter option downloads and runs Cruft in a temporary environment. This is useful if you want to occasionally run Cruft but don’t need it frequently enough to install it on your computer.

## Usage

To create a new Pelican plugin in the current working directory, enter the following command in your terminal console:

    cruft create https://github.com/getpelican/cookiecutter-pelican-plugin

You will then be asked to fill in details about the new plugin. Many of the default values, shown in brackets, can be accepted by tapping the `Return` key, while other inputs such as the plugin name and authors must be explicitly entered via the respective interactive prompts. Alternatively, some values can be provided to the `cruft` invocation in JSON format, such as:

    cruft create https://github.com/getpelican/cookiecutter-pelican-plugin --extra-context '{"plugin_name": "Render Math"}'

## Continuous Deployment

The generated plugin contains a `.github/workflows/main.yml` file for continuous integration (CI) and deployment via [GitHub Actions][] and [AutoPub][] that will ensure tests pass, check code style compliance, and publish packaged distributions to PyPI when a `RELEASE.md` file is present. For the latter step to function properly, please first ask a Pelican maintainer to make the necessary “Trusted Publisher” changes in PyPI settings.


[CookieCutter]: https://github.com/cookiecutter/cookiecutter
[Cruft]: https://github.com/cruft/cruft
[Pipx]: https://github.com/pipxproject/pipx
[GitHub Actions]: https://github.com/features/actions
[AutoPub]: https://justinmayer.com/projects/autopub/
