# simple-geolocation
Doing geolocation without installing Geoclue; and switch the timezone accordingly.

This produces a text file (`$HOME/.local/share/coords`) which you can then `cat` and use in other scripts.

## required dependencies
+ curl
+ jq
+ tzselect

## optional dependency
systemd (although you could use a cronjob if you like)

## install and usage
```
mv get_location <your executables path>
chmod +x get_location
```
### optionally
Edit get_location.timer to the time interval you want, and then
```
mv get_location.{service,timer} $HOME/.config/systemd/user/
systemctl --user enable get_location.service get_location.timer 
systemctl --user start get_location.service get_location.timer 
```
*or* make a cron job


