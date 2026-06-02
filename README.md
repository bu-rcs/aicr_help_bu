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
        
        ```
    - copy passphrase
    - follow steps to change passphrase (you'll enter the old passphrase here)
    - note new passphrase
    - move keys to trusted directory: mv id_ed25519_aicr id_ed25519_aicr.pub id_ed25519_aicr-cert.pub ~/.ssh/
    - delete old .passphrase file


- login
    - ssh -l USERNAME -i ~/.ssh/id_ed25519_aicr login.aicr.ai
    - enter new passphrase when prompted
