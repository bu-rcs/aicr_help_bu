# aicr_help_bu
Intro to using AICR for BU researchers


## Setup SSH Access
- Open an SCC OnDemand Desktop: [https://scc-ondemand.bu.edu](https://scc-ondemand.bu.edu)
- When the Desktop is ready, open it and type `firefox` into the terminal.
- When Firefox opens in the remote desktop, use it to login to [https://ood.aicr.ai](https://ood.aicr.ai)
    - go to the file browser screen and choose the `aicr_keys` folder.
      - Click the box that says "Show Dotfiles" so you see a file called `.passphrase`
      - download everything in the directory `aicr_keys` to your SCC `~/Downloads` folder.
    - In the remote desktop terminal:
      - ```
        mkdir aicr
        cd aicr
        mv ~/Downloads/id_ed25519_aicr* .
        chmod 600 id_ed25519_aicr
        # print the .passphrase file
        cat .passphrase
        # highlight, choose the menu option Edit->Copy to copy this.
        # Change the passphrase, remember the new one! Paste in the old
        # one with Edit->Paste when prompted.
        ssh-keygen -p -f ~/.ssh/id_ed25519_aicr
        eval $(ssh-agent -s)
        # Add this key to your .ssh directory
        ssh-add id_ed25519_aicr
        keychain ~/.ssh/id_ed25519_aicr-cert.pub
        cd ~
        # Test login. Your USERNAME is your BU username plus "_bu",
        # i.e. username --> username_bu
        ssh -i .ssh/id_ed25519_aicr USERNAME@login.aicr.ai
        # Enter passphrase if prompted.
        # If that worked, type "exit" to log out and you can
        # remove this directory.
        cd ~
        rm -rf aicr
        ```

## Login From the SCC
- From a terminal (via OnDemand, or an Ondemand Desktop, etc):
    - `ssh -i .ssh/id_ed25519_aicr USERNAME@login.aicr.ai`
    - enter new passphrase when prompted

