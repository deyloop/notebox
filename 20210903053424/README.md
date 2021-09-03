# Creating a Swap File in Linux

I follow the following steps to create a swap-file.

1. 
```
# Create the swap file
sudo fallocate -l 11G /swapfile
```

> I have 8GB RAM on my system, so I choose to have 11GB of swap. This is enough
> to allow me to hibernate if I want to.

2. 
```sh
# Only root should be able to read this file
sudo chmod 600 /swapfile
```

3. 
```
# Set the file as the swap area
sudo mkswap /swapfile
```

4. 
```
# Enable the swap
sudo swapon /swapfile
```

5. To make this setting permanent, add a record to `/etc/fstab`
```
# in /etc/fstab
/swapfile swap swap defaults 0 0
```

6. Verify that the changes took effect
```sh
sudo swapon --show
```

#### References
* <https://linuxize.com/post/create-a-linux-swap-file/>
