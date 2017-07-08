# systemd-disable-transparent-huge-pages

Disable Linux Kernel's Transparent Huge pages in order to run
[Redis](https://github.com/docker-library/redis/issues/55) and
[MongoDB](https://docs.mongodb.com/manual/tutorial/transparent-huge-pages/)
reliably. Also installs a [tuned](https://linux.die.net/man/8/tuned) profile
based on `virtual-guest` that keeps the Kernel setting disabled.

Tested on Fedora 25.

## Installation

1. Decide where you want to install things.

   ```sh
   INSTALL_DIR=/usr/local/src/systemd-disable-transparent-huge-pages
   ```

1. Clone this repository.

   ```sh
   $ git clone https://github.com/agross/systemd-disable-transparent-huge-pages.git "$INSTALL_DIR"
   Cloning into 'systemd-disable-transparent-huge-pages'...
   ```

1. Install `disable-transparent-huge-pages` systemd service unit.

   ```sh
   $ "$INSTALL_DIR/install"
   Linking and enabling /usr/local/src/systemd-disable-transparent-huge-pages/disable-transparent-huge-pages.service
   Created symlink /etc/systemd/system/disable-transparent-huge-pages.service → /usr/local/src/systemd-disable-transparent-huge-pages/disable-transparent-huge-pages.service.
   Created symlink /etc/systemd/system/basic.target.wants/disable-transparent-huge-pages.service → /usr/local/src/systemd-disable-transparent-huge-pages/disable-transparent-huge-pages.service.
   Enabling tuned profile virtual-guest-nothp
   ```
