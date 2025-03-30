## Define(Reduce) queue number
  ![image](https://github.com/user-attachments/assets/8ae4fc3a-037d-41ee-a7ab-8e0a7b6d5806)

```
/etc/systemd/system/set-queues.service
[Unit]
Description=Reduce Intel X710 queues
After=network-pre.target
Before=network.target

[Service]
Type=oneshot
ExecStart=/sbin/ethtool -L enp23s0f2 combined 8
ExecStart=/sbin/ethtool -L enp23s0f3 combined 8
RemainAfterExit=true

[Install]
WantedBy=multi-user.target
```
```
sudo systemctl daemon-reexec
sudo systemctl daemon-reload
sudo systemctl enable set-queues.service
ln -s /etc/systemd/system/set-queues.service /etc/systemd/system/multi-user.target.wants/set-queues.service
```


##Build driver
```
1.
sudo apt install --reinstall linux-headers-6.8.0-52-generic
/lib/modules/6.8.0-52-generic/build/include/config/auto.conf
2.
sudo apt install gcc-12 g++-12
sudo apt install gcc-12 g++-12
3.
#if LINUX_VERSION_CODE >= KERNEL_VERSION(5,14,0)
    temp_class = class_create(CLASS_NAME);
#else
    temp_class = class_create(THIS_MODULE, CLASS_NAME);
#endif
4.
make -C /lib/modules/$(uname -r)/build M=$(PWD) modules
```
