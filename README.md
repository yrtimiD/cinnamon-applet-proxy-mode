# cinnamon-applet-proxy-mode
[Cinnamon](https://projects.linuxmint.com/cinnamon/) applet which allows switch between system proxy modes (None, Manual, Automatic) from the panel.


## Development
Restart applet on file change
```shell
while true; do
	inotifywait -e modify proxy-mode@yrtimid/applet.js
 	dbus-send --session --dest=org.Cinnamon.LookingGlass --type=method_call /org/Cinnamon/LookingGlass org.Cinnamon.LookingGlass.ReloadExtension string:'proxy-mode@yrtimid' string:'APPLET'
done
```