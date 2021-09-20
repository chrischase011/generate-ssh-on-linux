# How to generate SSH keys on Linux and connect it to github
A step-by-step instruction to generate ssh on linux

1. Open your respective virtual machine with Linux OS inside. (eg. LinuxLite, Kali)
2. After booting up the virtual machines, Open Terminal
3. Before we generate SSH key, open firefox or web browser on your linux and login your 
  Github account. If you don't have an account yet, [Register Github](https://github.com/signup) here.
4. When you are logged in, Go to settings by clicking on your profile picture dropdown in the top-right most of the website. Then click Settings and scroll down and click the SSH and GPG keys. Or, click here [SSH and GPG settings](https://github.com/settings/keys)
5. Then, let's go back to our terminal and let's install git first using this command

```console
sudo apt install git
```
6. After installing git, then let's generate our ssh key. To generate, type this command

```console
ssh-keygen -t ed25519 -C "your_email@example.com"
```
Example:
```console
ssh-keygen -t ed25519 -C "chase_umak@gmail.com"
```
### Note
Make sure that your e-mail address is the same on the e-mail address you provide on your github account

7. And make a passphrase on your ssh key and press enter and you will see like this
![image](https://user-images.githubusercontent.com/43966456/133982262-d9a4ed04-26ca-4a07-8744-dd4f8082505e.png)

8. When you're prompted to "Enter a file in which to save the key," press Enter. This accepts the default file location
```console
> Enter a file in which to save the key (/home/you/.ssh/id_ed25519): [Press enter]
```
In this case our ssh key file name is id_ed25519 and id_ed25519.pub.

### Note
- The default location of your ssh keys is at .ssh folder which is not visible if you type the ```console ls ``` command. 

9. ALright, let's go to the .ssh folder to view the name of our key. type
```console
cd .ssh
ls
```
And this will show the files on our .ssh folder including our ssh key files and you will see the .pub file. (eg. id_ed25519.pub)

10. Let's view the contents of our ssh .pub (id_ed25519.pub) by typing this command
```console
cat id_ed25519.pub
```
And it will show something like this
![image](https://user-images.githubusercontent.com/43966456/133984239-31e7ea9a-69a4-4f88-8d29-2499f1e21272.png)

And copy that key using Ctrl+Shift+C or Right click and copy.

11. After copying the key, let's go back to our github and click "New SSH" button and you will be redirect to Add New SSH Keys page and enter your ssh key title on the Title input box and paste your copied SSH key to Key text area and click Add SSH key.
![image](https://user-images.githubusercontent.com/43966456/133984907-b965c4b8-cbac-4e4e-961c-318db91c02c8.png)

12. After that, let's test if our key is successfully connected to our github account by going back to our Terminal and typing this command:
```console
ssh -T git@github.com
```

After that, you will see a confirmation like this.
![image](https://user-images.githubusercontent.com/43966456/133985646-9c3d1dad-a8e9-46ce-ac82-d37fea2daa01.png)

13. Great, we are now successfully generated SSH keys and connect it to Github.


## References
[Generate new SSH key](https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
[Add new SSH Key](https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)
[Test your SSH keys](https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh/testing-your-ssh-connection)


Prepared by: [Christopher Robin Chase](https://github.com/chrischase011)
