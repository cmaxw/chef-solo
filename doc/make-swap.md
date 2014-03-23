Make A Swap Drive
=================

Create the swap.

```bash
sudo dd if=/dev/zero of=/swap.512mb bs=1M count=512
sudo mkswap /swap.512mb
```

Edit fstab.

```bash
sudo vim /etc/fstab
```

Add the following line to fstab so the swap will exist after reboot.

```
/swap.512mb swap  swap  defaults  0 0
```

Enable.

```bash
sudo swapon -a
```

[1]: https://www.digitalocean.com/community/articles/how-to-add-swap-on-ubuntu-12-04