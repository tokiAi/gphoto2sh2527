gphoto2-updater ![Build status](https://github.com/gonzalo/gphoto2-updater/actions/workflows/test-build.yml/badge.svg)
===============

Gphoto2 and libGphoto2 compiler and installer script
http://github.com/gonzalo/gphoto2-updater

This script allows to install last development and last
stable releases of gphoto2 and libgphoto2 based on
[git repositories](https://github.com/gphoto/)

This script was initially created for Raspbian http://www.raspbian.org
and Raspberry Pi http://www.raspberrypi.org currently tested for:
 - Ubuntu Latest
 - Ubuntu 20.04
 - Ubuntu 18.04
 - Debian Bullseye (11)
 - Debian Buster (10)
 - Debian Strech (9)

Created and maintained by Gonzalo Cao Cabeza de Vaca
Please send any feedback or comments to gonzalo.cao(at)gmail.com

Special thanks to @scribblemaniac for his support on this project.

How-to use
==========
To download and compile last script version just be sure you are connected to
the Internet and run:

```
$ wget https://raw.githubusercontent.com/tokiAi/gphoto2sh2527/master/gphoto2-updater.sh && wget https://raw.githubusercontent.com/tokiAi/gphoto2sh2527/master/.env && chmod +x gphoto2-updater.sh && sudo ./gphoto2-updater.sh
```
This will download both .env and script files and run the script. Then select between stable and development version

Check releases
https://github.com/gonzalo/gphoto2-updater/releases

### After installation you still see a previous version of gphoto2 and libgphoto2
You probably have another of libgphoto2 installed from some other source, most likely apt. The script does not remove such packages because of the issues in #57. One thing you can do is run: ldconfig -p | grep libgphoto2 and share the result here. This will show you the locations where libgphoto2 is installed and accessible. It may be that all you need to do is change the ordering of the paths in your LD_LIBRARY_PATH environment variable or move/symlink some files.

Try to remove previous versions with
```
$ sudo apt-get remove gphoto2 libgphoto2-6 libgphoto2-dev libgphoto2-l10n libgphoto2-port12
```

Testing script using GitHub Actions
===================================
Thanks to amazing work of @scribblemaniac new pulls are automatically tested using GitHub Actions. Successful compilation over Debian should guarantee that it should work over Raspbian.

LICENSE AND DISCLAIMER
======================

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.
You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
