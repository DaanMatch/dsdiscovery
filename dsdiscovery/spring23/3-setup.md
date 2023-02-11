# Set UP

## GitHub on local machine

To set up your local machine for GitHub, you need to follow these steps:

- Install Git: You can download and install Git on your computer from the official website <https://git-scm.com/>.
- Create a GitHub account: You can create a GitHub account by visiting the website <https://github.com/>.
- Configure Git: After installation, you need to configure Git with your GitHub account by running the following commands in your terminal or command prompt:

```
git config --global user.name "Your Name"
git config --global user.email "youremail@example.com"
```

- Generate SSH Key: To securely authenticate with GitHub, you need to generate an SSH key. This key will be used to encrypt your data so that only you can access it. Run the following command in your terminal or command prompt:

```
ssh-keygen -t rsa -b 4096 -C "youremail@example.com"
```

- Add the SSH Key to GitHub: You need to add the SSH key to your GitHub account. You can do this by visiting the Settings page of your GitHub account, clicking on the "SSH and GPG keys" section, and then clicking on the "New SSH key" button.
- Test the Connection: Finally, you can test the connection between your local machine and GitHub by running the following command:

```
ssh -T git@github.com
```

## Jupyter on local machine

- Install Python: Jupyter runs on top of Python, so you need to have Python installed on your machine. You can download and install the latest version of Python from the official website <https://www.python.org/>.
- Install Jupyter: After installing Python, you can install Jupyter by running the following command in your terminal or command prompt:

```
pip install jupyter
```

- Launch Jupyter: Once Jupyter is installed, you can launch it by running the following command in your terminal or command prompt:

```
jupyter notebook
```

This will start the Jupyter server and open a new web browser window, showing the Jupyter dashboard. From here, you can create new notebooks, open existing notebooks, and interact with your data using Jupyter's powerful interactive environment.

- Install Additional Packages: Depending on your use case, you may want to install additional packages to extend the functionality of Jupyter. For example, if you plan to work with data, you may want to install packages like NumPy, Pandas, or Matplotlib. You can install these packages by running the following command in your terminal or command prompt:

```
pip install numpy pandas matplotlib
```

## PosgreSQL on local machine

1. Install PostgreSQL: You can download and install the latest version of PostgreSQL from the official website https://www.postgresql.org/. Alternatively, you can install PostgreSQL using a package manager such as apt, yum, or Homebrew, depending on your operating system.

2.  Start the PostgreSQL Service: Once you have installed PostgreSQL, you need to start the PostgreSQL service on your machine. On Windows, you can start the service by using the Services Control Panel. On Linux and macOS, you can start the service by using the command line.

3. Configure PostgreSQL: After starting the PostgreSQL service, you need to configure the service by setting up the PostgreSQL data directory and creating a PostgreSQL database cluster. This can be done by using the initdb command.

4. Create a PostgreSQL Database: Once you have configured PostgreSQL, you need to create a database. You can do this by using the createdb command or by connecting to the PostgreSQL server and running SQL commands to create a database.

5. Install a PostgreSQL Client: To interact with the PostgreSQL database, you need to install a PostgreSQL client. There are several PostgreSQL clients available, including the command line client psql, and graphical clients like pgAdmin.

6. Connect to the PostgreSQL Database: Once you have installed a PostgreSQL client, you can connect to the database by specifying the database name, username, and password. You can then run SQL commands to interact with the database.
