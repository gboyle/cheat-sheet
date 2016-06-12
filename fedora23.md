

# Fedora 23

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

### Video

#### Screen Tearing During Video Playback

#### Screen Saver Activates During Video Playback

#### Mouse Cursor Remains Visible During Video Playback

### Code Editor

[Download Visual Studio Code](https://code.visualstudio.com/Download)

