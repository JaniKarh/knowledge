# Bash one-liners to do cool stuff

## Processes

Tip: Sometimes you get yourself into weird situations/trapped signals where Ctrl-C and Ctrl-| don't work. Try Ctrl-z and kill %1.

On Linux, print out a list of the process IDs that are in the zombie state.

`ps aux | awk '{if ($8=="Z") { print $2 }}'`

## Files

List the 20 largest files or folders under the current working directory.

`du -ma | sort -nr | head -n 20`

Make month histogram of dates of files in current directory.
`ls -la --full-time |tr -s " " |cut -f6 -d " "|cut -c1-7 | sort | uniq -c`

## Networking

Scan your internal network for hosts listening on TCP port 22 (SSH).

`nmap --open -p T:22 192.168.1.0/24`

Show the TCP and UDP ports being listened on and if you're root, also show the process associated, user, etc.

`netstat -lepunt`

Show what processes are using port 80 either locally or remotely. Need to be root for unowned processes.

`lsof -i TCP:80 `

Play alarm.wav once site is back.

`while ! curl -m 10 http://www.example\.com/ ; do echo still down ; sleep 1m ; done ; play alarm.wav`

## ssh

After all the host keys and auth, you'll be on server3.

`ssh -t user1@server1 'ssh -t user2@server2 "ssh -t user3@server3"'`

## Web serving

List top 50 404's in descending order.

`awk '$9 == "404" {print $7}' access.log |sort|uniq -c|sort -rn| head -n 50`

## MySQL

restore a mysql dump with progressbar and ETA.
`pv bigdump.sql.gz | gunzip | mysql`

## Random

Print the day of the year. Can be useful with things like find.
`date +%j`

Say hello using a nice voice.
`wget -q -O- -U Mozilla "https://translate.google.com/translate_tts?q=hello&tl=en"|mpg123 -q -

Turn a Unix epoch time back into a human readable date. Feature of GNU date

`date -d @192179700`

Pretend that you're on a starship.

`play -n -c1 synth whitenoise band -n 100 20 band -n 50 20 gain +30 fade h 1 86400 1`

Write out 20 png format frames from a video starting at 3 minutes, 46 seconds.

`mplayer -vo png -ss 3:46 -frames 20 stairs.mp4`
