# my-brewfile
package list for Homebrew

## Usage
1. Install `Brewfile`

    ```sh
    $ brew install rcmdnk/file/brew-file
    ```

2. Edit `.zshrc` to use `brew-wrap` if you would like to update brewfile *automatically*.

    ```diff
    # .zshrc
    + if [ -f $(brew --prefix)/etc/brew-wrap ];then
    +   source $(brew --prefix)/etc/brew-wrap
    + fi
    ```

3. Now, you can already use `brew-file`.

    ```sh
    $ brew-file init    # Make Brewfile
    $ brew-file install    # Install according to Brewfile
    $ brew-file update    # Update Brewfile
    ```

## Note
* You can connect your GitHub repository.
    1. Set git repository on brewfile directory.

        ```sh
        $ brew-file set_repo

        Set repository,
        "non" (or empty) for local Brewfile (/Users/satake/.config/brewfile/Brewfile),
        <user>/<repo> for github repository,
        or full path for other git repository: <UserName>/<RepoName>

        ...
        
        # If repository was not found, create on GitHub.
        # And, in this process, use SSH to connect with GitHub.
        GitHub repository: <UserName>/<RepoName> doesn't exist.
        do you want to create the repository? [y/n]: y
        GitHub password:
        $ git clone git@github.com:<UserName>/<RepoName> /Users/<UserName>/.config/brewfile/<UserName>_<RepoName>
        Cloning into '/Users/<UserName>/.config/brewfile/<UserName>_<RepoName>'...

        ...
        ```

    2. Now, directory is already connected. It is pushed to GitHub *automatically* when you update brewfile.

