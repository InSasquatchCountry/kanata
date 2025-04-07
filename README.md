# ARTSEY.IO Duel Wield Pistols w/Colemak-Layer for macOS 15.4 Sequoia

## [What does this do?](https://github.com/jtroo/kanata)

"This is a cross-platform software keyboard remapper for Linux, macOS and Windows. A short summary of the features:

multiple layers of key functionality

advanced key behaviour customization (e.g. tap-hold, macros, unicode)"

#### Why?

I wanted a way to try both the left and right hand versions of the artsey.io chorded keyboard without having to build one from scratch. I think having a wireless bluetooth wearable keeboard will be a standard for me here shortley and this well help me prepair for the various use cases where I want to send a command to my machine without having to run back to the onboard keeb. 

#### How?

Once running, my configs start up in duel-artsey by default and switch to the Colemak (in my case) layout by typing n+m and then back to artsey with esc+space.

___

## Per kanata instructions
First install Karabiner driver for macOS 11 and newer:

[V5 Karabiner VirtualHiDDevice Driver](https://github.com/pqrs-org/Karabiner-DriverKit-VirtualHIDDevice/blob/main/dist/Karabiner-DriverKit-VirtualHIDDevice-5.0.0.pkg)


#### To activate:

```sudo /Applications/.Karabiner-VirtualHIDDevice-Manager.app/Contents/MacOS/Karabiner-VirtualHIDDevice-Manager activate``` 

#### Then run the daemon:

You should run this in the background somehow or leave the terminal window where you run this command open.

```sudo '/Library/Application Support/org.pqrs/Karabiner-DriverKit-VirtualHIDDevice/Applications/Karabiner-VirtualHIDDevice-Daemon.app/Contents/MacOS/Karabiner-VirtualHIDDevice-Daemon'```

#### Then run kanata with sudo:

```sudo ~/bin/kanata/kanata_macos_cmd_allowed_arm64 -c ~/.config/kanata/artseyio_duel_colemak.kbd```

or

#### Run with a function:

```bash
kanata(){
	sudo /Applications/.Karabiner-VirtualHIDDevice-Manager.app/Contents/MacOS/Karabiner-VirtualHIDDevice-Manager activate && sudo '/Library/Application Support/org.pqrs/Karabiner-DriverKit-VirtualHIDDevice/Applications/Karabiner-VirtualHIDDevice-Daemon.app/Contents/MacOS/Karabiner-VirtualHIDDevice-Daemon' & sudo ~/bin/kanata/kanata_macos_cmd_allowed_arm64 -c ~/.config/kanata/artseyio_duel_colemak.kbd
}
```

I add this to my .zshrc to do all this with one command in one terminal window (which I keep minimized in the dock)
