# Set UP

## GitHub on local machine

To set up your local machine for GitHub, you need to follow these steps:

1. Install Git: You can download and install Git on your computer from the official website <https://git-scm.com/>.
2. Create a GitHub account: You can create a GitHub account by visiting the website <https://github.com/>.
3. Configure Git: After installation, you need to configure Git with your GitHub account by running the following commands in your terminal or command prompt:

```
git config --global user.name "Your Name"
git config --global user.email "youremail@example.com"
```

4. Generate SSH Key: To securely authenticate with GitHub, you need to generate an SSH key. This key will be used to encrypt your data so that only you can access it. Run the following command in your terminal or command prompt:

```
ssh-keygen -t rsa -b 4096 -C "youremail@example.com"
```

5. Add the SSH Key to GitHub: You need to add the SSH key to your GitHub account. You can do this by visiting the Settings page of your GitHub account, clicking on the "SSH and GPG keys" section, and then clicking on the "New SSH key" button.
6. Test the Connection: Finally, you can test the connection between your local machine and GitHub by running the following command:

```
ssh -T git@github.com
```

## Jupyter on local machine

1. Install Python: Jupyter runs on top of Python, so you need to have Python installed on your machine. You can download and install the latest version of Python from the official website <https://www.python.org/>.
2. Install Jupyter: After installing Python, you can install Jupyter by running the following command in your terminal or command prompt:

```
pip install jupyter
```

3. Launch Jupyter: Once Jupyter is installed, you can launch it by running the following command in your terminal or command prompt:

```
jupyter notebook
```

This will start the Jupyter server and open a new web browser window, showing the Jupyter dashboard. From here, you can create new notebooks, open existing notebooks, and interact with your data using Jupyter's powerful interactive environment.

4. Install Additional Packages: Depending on your use case, you may want to install additional packages to extend the functionality of Jupyter. For example, if you plan to work with data, you may want to install packages like NumPy, Pandas, or Matplotlib. You can install these packages by running the following command in your terminal or command prompt:

```
pip install numpy pandas matplotlib
```

These are the basic steps to set up Jupyter on your local machine. With Jupyter, you can easily create, edit, and share interactive documents that combine code, text, mathematics, and visualizations.
