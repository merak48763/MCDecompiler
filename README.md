# MCDecompiler

Decompiler for versions since 26.1-snapshot-1

## Setup

### Step 1: Configure Repositories

- Fork this repository ("Action Repo").
- Create a **PRIVATE** repository to store decompiled code ("Store Repo").

### Step 2: Configure Secrets

- Setup deploy key.
  - See tutorial [here](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/managing-deploy-keys#set-up-deploy-keys).
  - Public key belongs to the Store Repo.
  - Private key should be pasted into a [secret](https://docs.github.com/en/actions/how-tos/write-workflows/choose-what-workflows-do/use-secrets) called `DEPLOY_PRIVATE_KEY` in Action Repo.
- Setup store repository name.
  - Paste the name of Store Repo (it should look like `owner/repository_name`) into a secret called `REPOSITORY` in Action Repo.
- Setup Discord webhook.
  - Paste the [webhook URL](https://support.discord.com/hc/en-us/articles/228383668-Intro-to-Webhooks) into a secret called `DISCORD_WEBHOOK_URL` in Action Repo.
    - Note: Do NOT append `/github` to the end of the URL! That endpoint is not for custom notifications.
  - If you don't need Discord notification, delete the two `Send Discord notification` steps in `.github/workflows/decompile.yml` instead.

## How to...

> *we serve food here, sir*

### Decompile History Versions At Once

The current workaround is to disable "Check Updates" workflow and manually trigger "Decompile Minecraft" workflow.

### Manage Branching Versions

Examples are April Fool versions and [Hotfix 1.16.5](https://minecraft.wiki/w/Java_Edition_1.16.5_Release_Candidate_1).  
Not implemented.

## Credits

- The actions are adapted from actions [posted](https://discord.com/channels/154777837382008833/157097006500806656/1450571787577331753) in Minecraft Commands by [Hardel](https://github.com/Hardel-DW).
- The two-repo structure is inspired by [Nickid2018/GitMCDecomp](https://github.com/Nickid2018/GitMCDecomp).
