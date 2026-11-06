# Beyond Home changes

Beyond Home OS is Home Assistant Operating System with the changes below, made by Global Support Limited trading as
Beyond (gobeyond.nz). Everything else is Home Assistant's, under the same Apache 2.0 licence (`LICENSE`).
Beyond Home is not made or endorsed by the Open Home Foundation or Nabu Casa.

Each change is one commit, put back on top of every Home Assistant OS release.

1. **The name people read.** `HAOS_NAME` in `buildroot-external/meta` is "Beyond Home OS". `HAOS_ID` stays `haos`,
   because the Supervisor finds the OS by it.
2. **The box's name on the network** is `beyond-home` (`beyond-home.local`), in every board's defconfig.
3. **Our app store from the first boot.** `create-data-partition.sh` writes the Supervisor's `store.json` with
   github.com/YeahBuddyNZ/Beyond-Home; the Supervisor adds its built-in stores beside it.
4. **Beyond Home installed on the first boot.** `beyond-home-setup.service` waits for the Supervisor, installs the
   Beyond Home app, puts it in the sidebar and starts it, then marks `/mnt/data/beyond/setup-done` and never runs again.

Not yet changed: updates still come from Home Assistant, so updating the OS from Settings puts plain Home Assistant OS
back. Only try these builds on a spare box until our own updates exist.
