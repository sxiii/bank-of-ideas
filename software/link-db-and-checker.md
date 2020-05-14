# Linkchecker project

## Brief description
The link database with robot that regularly (ideally, 1 time every day) visit links and check that they are alive.
Database can also be published online in a similar-to-wiki or hierarchical tree view.

## Project full description
Have you ever encountered dead links in Wikipedia or other websites? 
Do you know that Wiki authors update theclink statuses **manually, by hands**?

It would be rather easy to build a catalogue website with a small robot script, that checks the validity of links and adds
statuses to them, like:
* Link available (checked on 20.10.2020)
* Link recently stopped working (was available yesterday 19.10.2020)
* Link dead (last online 01.01.2019), copies available in WebArchive
* Link dead (last online 10.05.1999), copies not found
* Status unknown (manual check required)
* Cannot check link because of CDN or boilerplate protection system (Cloudflare / Incapsula / etc.)

Links can be checked on the different levels or OSI Layers:
* Protocol level (TCP/IP request OK?) < easy to implement
* Webserver request (HTTP(S) request OK?) < medium to implement
* Actual content OK? (Trying to see if page contains real content) < hard to implement

WebArchive check can be implemented as optional add-on if needed.

This tool can also be used as a slow, but extremely light on resources disaster emergency warning system for web.

## Author
If you like, you can note me as the author of the project idea - @sxiii. 

## License
Preferably the GPLv3 or similar.

## Links
* Website: N/A
* Github: N/A
