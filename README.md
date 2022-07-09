# protonmail-for-linux
An unofficial ProtonMail client for GNU/Linux.

# How to compile from source
- ## For Debian GNU/Linux and derivates
    1. Install the package using the command below.  
        ```
        sudo apt install npm
        ```

    2. Within the repository folder, run the command:
        ```
        npm run make
        ```
        > If you prefer, you can use the command `npm run package`, to build the program into a folder instead.

    3. Install the `deb` package with `sudo dpkg -i <package-name>.deb`.

- ## For Arch Linux
    1. Within the folder `archlinux` run the following command:
        ```
        makepkg -cisr
        ```
