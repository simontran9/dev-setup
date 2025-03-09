# setup

My Linux development setup

## Steps

1. Install [visual studio code](https://code.visualstudio.com/) and [jetbrains mono](https://www.jetbrains.com/lp/mono/), install `code` command, and set the `settings.json` config

2. Create a `.bashrc` and a `.bash_profile`

   ```sh
   touch ~/.bashrc ~/.bash_profile
   # then copy contents from here to the files
   ```

3. Update and upgrade

   ```sh
   sudo apt update
   sudo apt upgrade
   ```

4. Install core tools

   ```sh
   sudo apt install -y build-essential
   ```

5. Set up the git config, and set up an SSH key

   ```sh
   git config --global user.name "Simon Tran"
   git config --global user.email <MY EMAIL>
   git config --global init.defaultBranch main
   git config --global core.editor "code --wait"
   ```

   ```
   ssh-keygen -t ed25519 -C "<YOUR EMAIL>"
   eval "$(ssh-agent -s)"
   echo  "Host github.com
   AddKeysToAgent yes
   IdentityFile ~/.ssh/id_ed25519" > ~/.ssh/config
   ssh-add ~/.ssh/id_ed25519
   pbcopy < ~/.ssh/id_ed25519.pub
   
   # ADD THE ABOVE TO SSH AND GPG KEYS ON GITHUB

   ssh -T git@github.com
   ```

6. Install rust

   ```sh
   curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
   ```
   




