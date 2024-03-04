# DS Discovery

DS Discovery Resource Collection. Click on the badge to be directed to the page.

[![Jupyter Book Badge](https://jupyterbook.org/badge.svg)]( https://daanmatch.github.io/dsdiscovery/)

## Usage

### Installing Jupyter

For help installing Jupyter, please read the document InstallJupyter. When following the steps in this document, it may be necessary to run the command lines a couple of times, and give the Terminal a few seconds to output its necessary information. Also note: the instructions in the InstallJupyter document are intended to be ran in the 'Terminal' if installing on Mac. The terminal can be found by going to Launchpad and searching Terminal.

### Building the book

If you'd like to develop and/or build the DS Discovery book, you should:

1. Clone this repository
2. Run `pip install -r requirements.txt` (it is recommended you do this within a virtual environment)
3. (Optional) Edit the books source files located in the `dsdiscovery/` directory
4. Run `jupyter-book clean dsdiscovery/` to remove any existing builds
5. Run `jupyter-book build dsdiscovery/`
6. Run `ghp-import -n -p -f _build/html`

A fully-rendered HTML version of the book will be built in `dsdiscovery/_build/html/`.

Could not import extension myst_nb (exception: cannot import name 'AttrDict' from 'markdown_it.utils' (/Users/simplypatrickg/anaconda3/lib/python3.8/site-packages/markdown_it/utils.py))

### Hosting the book

Please see the [Jupyter Book documentation](https://jupyterbook.org/publish/web.html) to discover options for deploying a book online using services such as GitHub, GitLab, or Netlify.

For GitHub and GitLab deployment specifically, the [cookiecutter-jupyter-book](https://github.com/executablebooks/cookiecutter-jupyter-book) includes templates for, and information about, optional continuous integration (CI) workflow files to help easily and automatically deploy books online with GitHub or GitLab. For example, if you chose `github` for the `include_ci` cookiecutter option, your book template was created with a GitHub actions workflow file that, once pushed to GitHub, automatically renders and pushes your book to the `gh-pages` branch of your repo and hosts it on GitHub Pages when a push or pull request is made to the main branch.

## Contributors

We welcome and recognize all contributions. You can see a list of current contributors in the [contributors tab](https://github.com/shpatrickg/ds_discovery/graphs/contributors).

## Credits

This project is created using the excellent open source [Jupyter Book project](https://jupyterbook.org/) and the [executablebooks/cookiecutter-jupyter-book template](https://github.com/executablebooks/cookiecutter-jupyter-book).
