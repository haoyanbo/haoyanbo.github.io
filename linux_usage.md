  ![image](https://github.com/user-attachments/assets/8ae4fc3a-037d-41ee-a7ab-8e0a7b6d5806)

'''
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

sudo systemctl daemon-reexec
sudo systemctl daemon-reload
sudo systemctl enable set-queues.service
'''
