# How to download Jupyter notebooks (on Mac)
```bash
# (Optional)
# First I’d recommend making a new folder like I just made a folder called “Daanmatch_Internship” in desktop, just to find files and stuff easier
# And then in terminal you can type in “cd desktop” and then “cd [your folder_name]” to navigate to the folder that you made

# Copy this line to download Homebrew
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Copy this line to upgrade Homebrew
brew update && brew upgrade

# Copy this line to download Python
brew install python3

# Now you can copy this line!
pip3 install jupyterlab

# This is how you install a Jupyter notebook, copy this line into terminal
pip install notebook

# This is how you open the notebook, copy this line into terminal!
jupyter notebook
```
'''
# Installing the libraries to be used in a Jupyter notebook
    # After following the above instructions to download Juyter notebooks on Mac, you may run into an error message when trying to import libraries into a notebook; for example,
      the error message " ModuleNotFoundError: No module named 'pandas' " may appear when running the code "import pandas as pd". This is because you must install such libraries 
      in the new Python environment you have created when you followed the instructions above. Here's how you can do that:
- Once you have opened a Jupyter notebook via the above instructions, you should have a Terminal tab open titled something like: "Jupyter-notebook Python". Make sure to keep this
Terminal tab open as you are working on that notebook, else your notebook code will not execute.
- In the Terminal, press Command T in order to open a new Terminal tab
- Now you can install whatever libraries you need in this Terminal tab via the following syntax: 
      "pip install ____"
  The blank can be filled by any library, such as pandas, seaborn, datascience, etc. 
- You will now be able to import said libraries into your notebook.
