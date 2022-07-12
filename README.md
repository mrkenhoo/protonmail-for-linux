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
        npm update
        ```

    3.  Next, to build the packages, run this command:
        ```
        npm run make
        ```
        > If you prefer, you can use the command `npm run package`, to build the program into a folder instead.

    4. Install the `deb` package with `sudo dpkg -i out/make/deb/x64/<package-name>.deb`.

- ## For Fedora and derivates
    1. Install the package using the command below.  
        ```
        sudo dnf install npm
        ```

    2. Within the repository folder, run the command:
        ```
        npm update
        ```

    3.  Next, to build the packages, run this command:
        ```
        npm run make
        ```
        > If you prefer, you can use the command `npm run package`, to build the program into a folder instead.

    4. Finally, install the `rpm` package with `sudo rpm -i out/make/rpm/x64/<package-name>.rpm`.

- ## For Arch Linux
    1. Within the folder `archlinux` run the following command:
        ```
        makepkg -cisr
        ```
