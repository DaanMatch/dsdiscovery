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
