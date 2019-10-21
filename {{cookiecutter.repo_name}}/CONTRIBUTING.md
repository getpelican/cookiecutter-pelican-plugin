Contributing
============

Contributions are welcome and much appreciated. Every little bit helps.

To get started, follow either the **Quick Set-up** or **Detailed Set-up** instructions, and then proceed to the **Development** section further below.

Quick Set-up
------------

To set up {{ cookiecutter.plugin_name }} for local development, first install [Poetry][]:

    curl -sSL https://raw.githubusercontent.com/sdispater/poetry/master/get-poetry.py | python

Go to the [{{ cookiecutter.plugin_name }} repository][] and tap the **Fork** button at top-right. Then clone the source for your fork and add the upstream project as a Git remote:

    git clone https://github.com/YOUR_USERNAME/{{ cookiecutter.repo_name }}.git
    cd {{ cookiecutter.repo_name }}
    git remote add upstream {{ cookiecutter.repo_url }}.git

The last two steps will install the needed dependencies and set up the project:

    poetry install
    invoke setup

Your local environment should now be ready to go! See the **Development** section further below for next steps.

Detailed Set-up
---------------

To set up {{ cookiecutter.plugin_name }} for local development, first install [Poetry][]:

    curl -sSL https://raw.githubusercontent.com/sdispater/poetry/master/get-poetry.py | python

Next, install [Pre-commit][]. Here we will install [Pipx][] and use it to install Pre-commit:

    python3 -m pip install --user pipx
    python3 -m pipx ensurepath
    pipx install pre-commit

Tell Pre-commit where to store its Git hooks, such as `~/.local/share/git/templates`. This only needs to be done once per workstation, so if you have already run these commands for another project, you can skip this step:

    mkdir -p ~/.local/share/git/templates
    git config --global init.templateDir ~/.local/share/git/templates
    pre-commit init-templatedir ~/.local/share/git/templates

Go to the [{{ cookiecutter.plugin_name }} repository][] and tap the **Fork** button at top-right. Then clone the source for your fork and add the upstream project as a Git remote:

    git clone https://github.com/YOUR_USERNAME/{{ cookiecutter.repo_name }}.git
    cd {{ cookiecutter.repo_name }}
    git remote add upstream {{ cookiecutter.repo_name }}.git

**(optional)** Poetry will automatically create a virtual environment for you but will alternatively use an already-activated environment if you prefer to create and activate your virtual environments manually:

    python3 -m venv ~/virtualenvs/{{ cookiecutter.repo_name }}
    source ~/virtualenvs/{{ cookiecutter.repo_name }}/bin/activate

Install {{ cookiecutter.plugin_name }} and its dependencies via Poetry:

    poetry install

Your local environment should now be ready to go!

Development
-----------

Once {{ cookiecutter.plugin_name }} has been set up for local development, create a topic branch for your bug fix or feature:

    git checkout -b name-of-your-bugfix-or-feature

Now you can make changes to the plugin, documentation, and/or other aspects of the project. Once you’ve made your changes, ensure there are no test failures or code style violations by running the tests:

    invoke tests

Assuming linting validation and tests pass, add a `RELEASE.md` file in the root of the project that contains the release type (major, minor, patch) and a summary of the changes that will be used as the release changelog entry. For example:

    Release type: patch

    Fix browser reloading upon changes to content, settings, or theme

Commit your changes and push your topic branch:

    git add .
    git commit -m "Your detailed description of your changes"
    git push origin name-of-your-bugfix-or-feature

Finally, visit `https://github.com/YOUR_USERNAME/{{ cookiecutter.repo_name }}` and submit a pull request.


[{{ cookiecutter.plugin_name }} repository]: {{ cookiecutter.repo_url }}
[Pipx]: https://pipxproject.github.io/pipx/installation/
[Poetry]: https://poetry.eustace.io/docs/#installation
[Pre-commit]: https://pre-commit.com/
