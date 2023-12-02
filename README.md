# READ ME FIRST

This is a CLONE of a fork of an MR I found for the ElanTech 04f3:0c00 fingerprint driver, which exists on my HP Pavilion x360. I DID NOT WRITE THIS, I don't even know C. I barely could install it. But, I'm uploading this repo to my GitHub as an archived, read-only repo for anyone in the future who may want to use this.

There is an open merge request for this device on the official libfprint repo which has been updated further than this repo, but I could not get it working on my laptop. It would recognize the device, but would refuse to interface with it. [The MR is here](https://gitlab.freedesktop.org/libfprint/libfprint/-/merge_requests/330)

The install instructions for this are:

```bash
sudo apt install meson ninja-build libgusb-dev libgirepository1.0-dev libnss3-dev libgudev-1.0-dev gtk-doc-tools valgrind
sudo ldconfig
git clone https://gitlab.freedesktop.org/geodic/libfprint.git
cd libfprint/
git pull
meson build
cd build
ninja
sudo ninja install
```

Followed by a reboot. When you reboot, you may as well reset the fingerprint reader in the BIOS since that'll be necessary, as well as install libpam-fprintd. Note that you can't use the fingerprint scanner with Windows Hello after using it in Ubuntu unless you reset it again.

# **Original readme below**

# libfprint

libfprint is part of the fprint project:
https://fprint.freedesktop.org/

libfprint was originally developed as part of an academic project at the
University of Manchester with the aim of hiding differences between different
consumer fingerprint scanners and providing a single uniform API to application
developers. The ultimate goal of the fprint project is to make fingerprint
scanners widely and easily usable under common Linux environments.

The academic university project runs off a codebase maintained separately
from this one, although I try to keep them as similar as possible (I'm not
hiding anything in the academic branch, it's just the open source release
contains some commits excluded from the academic project).

THE UNIVERSITY OF MANCHESTER DOES NOT ENDORSE THIS THIS SOFTWARE RELEASE AND
IS IN NO WAY RESPONSIBLE FOR THE CODE CONTAINED WITHIN, OR ANY DAMAGES CAUSED
BY USING OR DISTRIBUTING THE SOFTWARE. Development does not happen on
university computers and the project is not hosted at the university either.

For more information on libfprint, supported devices, API documentation, etc.,
see the homepage:
https://fprint.freedesktop.org/

libfprint is licensed under the GNU LGPL version 2.1. See the COPYING file
for the license text.

Section 6 of the license states that for compiled works that use this
library, such works must include libfprint copyright notices alongside the
copyright notices for the other parts of the work. We have attempted to
make this process slightly easier for you by grouping these all in one place:
the AUTHORS file.

libfprint includes code from NIST's NBIS software distribution:
http://fingerprint.nist.gov/NBIS/index.html
We include bozorth3 from the US export controlled distribution. We have
determined that it is fine to ship bozorth3 in an open source project,
see https://fprint.freedesktop.org/us-export-control.html

## Historical links

Older versions of libfprint are available at:
https://sourceforge.net/projects/fprint/files/

Historical mailing-list archives:
http://www.reactivated.net/fprint_list_archives/

Historical website:
http://web.archive.org/web/*/https://www.freedesktop.org/wiki/Software/fprint/
