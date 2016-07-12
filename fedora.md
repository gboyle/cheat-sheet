

# Fedora

### Real Time Clock, Windows vs Linux

Windows tends to keep the real time clock on local time while Linux prefers UTC.

#### Set Windows to Use UTC

    Windows Registry Editor Version 5.00

    [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\TimeZoneInformation]
    “RealTimeIsUniversal”=dword:00000001

#### Set Linux to use Local

    timedatectl set-local-rtc 1

### Keyboard

#### Disable Mouse Keys

Comment out mousekeys and accessx(full) in /usr/share/X11/xkb/compat/complete:

    default xkb_compatibility "complete" {
        include "basic"
        augment "iso9995"
        //augment "mousekeys"
        //augment "accessx(full)"
        augment "misc"
        augment "xfree86"
        augment "level5"
        augment "caps(caps_lock)"
    };

[Disable Numpad Mouse Keys on Linux+GNOME Permanently](http://www.mysolutions.it/disable-numpad-mouse-keys-linux-gnome-permanently/)

#### Fix Shift-End on Numeric Keypad

Add XkbOptions numpad:microsoft to /etc/X11/xorg.conf.d/00-keyboard.conf:

    # Read and parsed by systemd-localed. It's probably wise not to edit this file
    # manually too freely.
    Section "InputClass"
        Identifier "system-keyboard"
        MatchIsKeyboard "on"
        Option "XkbLayout" "us"
        Option "XkbOptions" "numpad:microsoft" 
    EndSection

	
[Fixing wrong Shift+Numpad (keypad) behaviour in Emacs](http://www.linux-pages.com/2013/06/fix-wrongshift-numpad-keypad-behaviour-in-emacs/)

#### Fix Windows+Arrow on Numeric Keypad

It works on the cursor pad, which I never use, but not on the numeric keypad.

### Video

#### Screen Tearing During Video Playback

24 still tears most of the time but it's better than 23 (Centos was unbearable for tearing).

#### Screen Saver Activates During Video Playback

This is purely a hack when the application can't stop the screen saver.

    # set time to blank screen (seconds)
    gsettings set org.gnome.desktop.session idle-delay 3600

    # set time after blanking to lock screen (seconds)
    gsettings set org.gnome.desktop.screensaver lock-delay 0

[Make Gnome screen lock after 1 hour, not 15 minutes?](http://superuser.com/questions/727120/make-gnome-screen-lock-after-1-hour-not-15-minutes)

#### Mouse Cursor Remains Visible During Video Playback

### Gnome

#### Minimize, Maximize, Restore Windows

Suprisingly clunky. 

* Minimize via right clicking title bar.
* Maximize via right clicking title bar or dragging the title bar to the top.
* Restore by clicking Activities and selecting window.

Installing the gnome-tweak-tool allows you to add the expected minimize/maximize buttons that are missing by default.

* dnf install gnome-tweak-tool
* under Windows, Titlebar Buttons, Maximize/Minimize ON

It still lacks a taskbar which makes managing screen real estate extremely clumsy.


#### Add Application to Activities Menu

First create a .desktop file for the application.

    ~/.local/share/applications/jee-neon.desktop (or /usr/share/applications/jee-neon.desktop)

    [Desktop Entry]
    Encoding=UTF-8
    Name=JEE Neon
    Exec=/home/username/eclipse/jee-neon/eclipse/eclipse
    Icon=/home/username/eclipse/jee-neon/eclipse/icon.xpm
    Type=Application
    
Then use Activities, Type to search, enter the name, right click the icon, choose Add to Favorites.

[How do you create a custom application launcher in Gnome Shell?](http://askubuntu.com/questions/112186/how-do-you-create-a-custom-application-launcher-in-gnome-shell)
[How to create shortcut in launcher?](https://ask.fedoraproject.org/en/question/30272/how-to-create-shortcut-in-launcher/)

#### Terminal Cut and Paste Clunky

Finding that cut and paste is inconvenient and inconsistent....

### Editors and Integrated Development Enviroments

#### Nano

#### Neovim

#### Emacs

#### Visual Studio Code

Download

[Download Visual Studio Code](https://code.visualstudio.com/Download)

Install

    # For .rpm (Fedora 22 and above)
    sudo dnf install <file>.rpm

TODO: Go/Rust plugins...

#### Codeblocks

Crashes in Fedora 24.

#### NetBeans

Can't seem to open existing maven projects in Fedora 24.  