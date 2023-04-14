# push declined due to email privacy restrictions error while pushing the changes to github repository  

This error is thrown , when privacy settings are enabled under `Profile>Settings>[Access]Emails`, below are the 2 settings which are selected:

1. Keep my email address private.
2. Block command line pushes that exposes my email.

To fix the `git push` issue without disabling this important privacy settings, use below steps:

1. Copy the unique email-id shown under the checkbox `Keep my email address private` which has format `<some_number>+<username>@users.noreply.github.com`.
2. In the terminal where git repo is located type below commands:

    ```None
    git config --global user.email <unique email id mentiond in step#1 above>
    git commit --amend --reset-author (if something is staged and committed)
    ```

3. `git push` the changes, now the changes must be pushed without `push declined due to email privacy restrictions` error.
