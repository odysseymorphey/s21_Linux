## Installing OS

### Ubuntu version

![version](screenshots/version.png)

    Command running
---

## User create

### User create command call

![adduser](screenshots/adduser.png)

    sudo adduser work

### Passwd output

![passwd](screenshots/passwd.png)

    cat /etc/passwd output
---

## Network configuration

### Set machine name

- Using the <font color="cyan" >_hostnamectl_</font> utility and the <font color="cyan">_set-hostname_</font> command, we change the name of the server

### Set time zone

- Using the <font color ="cyan">_timedatectl_</font> utility and command <font color="cyan">_set-timezone Europe/Moscow_</font> we change system timezone to the Moscow location

### Showing network interfaces

- Using the <font color="cyan">_ifconfig_</font> command we show all network interfaces. But before using this command you will need to install <font color="cyan">_net-tools_</font> package via command <font color="cyan">_sudo apt install net-tools_</font>

- <font color ="Cyan">Loopback</font> is a communication channel with a single endpoint. Any messages sent to this channel are immediately received by the same channel. Any messages that are sent from this interface, but whose address is not Loopback Interface, are discarded. In computers, such a loopback interface address is the address <font color="cyan">127.0.0.1</font>, it is fixed and cannot be changed. On Unix-like systems, the loopback interface is called <font color="cyan">lo</font> or <font color="cyan">lo0</font>

### Showing DHCP

- Using command <font color="cyan">_sudo dhclient -v_</font> we show DHCP logs information
![dhcp info](screenshots/dhcp_info.png)

- Using command <font color="cyan">_less /var/lib/dhcp/dhclient.leases_</font> we show information from <font color="cyan">dhclient</font>
![dhclient](screenshots/dhclient.png)

### Getting external and internal IP

- External IP gets via command <font color="cyan">_curl https://ipinfo.io/ip</font>_
![external-ip](screenshots/external-ip.png)

- Internal IP gets via command <font color="cyan">_nslookup localhost_</font>
![internal-ip](screenshots/internal-ip.png)

### Configuring static adresses

- From <font color="cyan">.yaml</font> file we can congigure static network settings
![static-settings](screenshots/static_settings.png)

- After changing <font color="cyan">.yaml</font> file needs apply this config via command <font color="cyan">_sudo netplan apply_</font>

- IP config after apply settings:
![after-cfg](screenshots/after-cfg.png)

### Pinging

- Ping 1.1.1.1 
![ping 1.1.1.1](screenshots/ping%201.1.1.1.png)

- Ping ya.ru
![ping ya.ru](screenshots/ping%20ya.ru.png)

## Update OS

- For update information of installed packages needs run command <font color="cyan">_sudo apt update_</font>

- For install updated packages needs run command <font color="cyan">_sudo apt upgrade_</font>

- If you installed all updated packages run command <font color="cyan">_apt list --upgradable_</font> for check upgradable objects. If all packages are upgraded, you will see this message
![update](screenshots/update.png)

## Using the sudo command

- <font color="cyan">_sudo_</font> is a command-line program that allows trusted users to execute commands as root or another user

- For got the sudo permissions you will run command <font color="cyan">_usermod -aG sudo %username%_</font>
- Changing hostname as new sudo user
![sudo](screenshots/sudo.png)

## Installing and configuring timezone

- Current time
![cur-time](screenshots/cur_time.png)

- Enabling synchronization via command <font color="cyan">_sudo timedatectl set-ntp on_</font>
![ntp-on](screenshots/ntp-on.png)

## Installing and using text editors

    sudo apt install neovim
    sudo apt install nano
    sudo apt install mcedit

![test-vim](screenshots/test_vim.png)
> For exit with and save changes used hotkey comman :wq

![test-nano](screenshots/test_nano.png)
> For save changes use command ^O and command ^X for exit

![test-mcedit](screenshots/test-mcedit.png)
> For save changes use a hotkey F2 and hotkey F10 for exit

![test-vim2](screenshots/test-vim2.png)
> For exit without changes use command :q!

![test-nano2](screenshots/test-nano2.png)
> For exit without changes use command ^X + n

![test-mcedit2](screenshots/test_mcedit2.png)
> For exit without changes use a hotkey Fn + F10 and choose "No"

![search_vim](screenshots/search_vim.png)
> Vim seacrh result

![search-vim2](screenshots/search-vim2.png)
> Vim word replace

![serach-nano](screenshots/search-nano.png)
> Nano search result

![search-nano2](screenshots/search_nano2.png)
![search-nano3](screenshots/search-nano3.png)
> Nano replace result

![search-mcedit](screenshots/search_mcedit.png)
> Mcedit search result

![search-mcedit2](screenshots/search_mcedit2.png)
![search-mcedit3](screenshots/search_mcedit3.png)
> Mcedit replace result

## Installing and setup SSHD

- To install SSH using command <font color="cyan">_sudo apt-get install openssh-server_</font>
- To enable ssh on boot using command <font color="cyan">_sudo systemctl enable ssh_</font>

- To change ssh port using command <font color="cyan">_sudo vim /etc/ssh/sshd_config_</font>
![ssh-port](screenshots/ssh-port.png)

- <font color="cyan">_ps -aux | grep sshd_</font>
- `a` this option causes ps to list all processes with a terminal (tty), or to list all processes when used together with the x option.
- `u` Display user-oriented format.
- `x` this option causes ps to list all processes owned by you (same EUID as ps), or to list all processes when used together with the a option.
![ssh-ps](screenshots/ssh-ps.png)

- <font color="cyan">_netstat -tan output_</font>
![net-stat](screenshots/netstat.png)
- `t` (`--tcp`) tcp protocol output
- `a` (`--all`) Show both listening and non-listening sockets 
- `n` (`--numeric`) Show numerical addresses instead of trying to determine symbolic host, port or user names Proto - the protocol (tcp, udp, raw) used by the socket.

## Installing and using top/htop utilities

### Top

- The `top` utility provides a dynamic real-time view of a running system.
![top](screenshots/top.png)
    <font color="red">`uptime`</font>
    <font color="orange">`number of authorized user`</font>
    <font color="yellow">`total system load`</font>\
    <font color="lime">`total number of proccess`</font>
    <font color="magenta">`total cpu usage`</font>
    <font color="green">`memory usage`</font>

![cpu](screenshots/cpu.png)
    <font color="red">`process sorted by cpu usage`</font>

![mem](screenshots/mem.png)
    <font color="green">`process sorted by memory usage`</font>

### Htop

- PID
![htop-pid](screenshots/htop_pid.png)
- %CPU
![htop-cpu](screenshots/htop_cpu.png)
- %MEM
![htop-mem](screenshots/htop_mem.png)
- TIME
![htop-time](screenshots/htop_time.png)
- SSHD
![htop-sshd](screenshots/htop_sshd.png)
- SYSLOG
![htop-log](screenshots/htop_log.png)

- For output hostname, clock and uptime needs add this ouputs in settings
![htop-settings](screenshots/htop_settings.png)
![htop_hcu](screenshots/htop_hcu.png)

## Using fdisk utility

![fdisk](screenshots/fdisk.png)
    <font color="red">`disk name`</font>
    <font color="orange">`disk size`</font>
    <font color="yellow">`count of sectors`</font>

- To show swap info use command <font color="cyan">_free -h_</font>
![swap](screenshots/swap.png)

## Using df command

- Measurement unit is KB
![df](screenshots/df.png)
    <font color="red">`partintion size`</font>
    <font color="orange">`space used`</font>
    <font color="yellow">`space free`</font>
    <font color="lime">`percentage used`</font>

![df-Th](screenshots/df-Th.png)
<font color="">`partition type`</font>
<font color="red">`partintion size`</font>
<font color="orange">`space used`</font>
<font color="yellow">`space free`</font>
<font color="lime">`percentage used`</font>

## Using du utility

- `h` using for humanreadable output
- `d` for contol depth output
![du](screenshots/du.png)
![du-home](screenshots/du_home.png)
![du-var](screenshots/du_var.png)
![du-var-log](screenshots/du_var_log.png)
![du-var-all](screenshots/du_var_all.png)

## Using ncdu utility

![ncdu-install](screenshots/ncdu_install.png)
![ncdu-home](screenshots/ncdu_install.png)
![ncdu-var](screenshots/ncdu-var.png)
![ncdu-var-home](screenshots/ncdu_var_home.png)

## Working with system logs

- dmesg
![dmesg](screenshots/dmesg.png)

- syslog
![syslog](screenshots/syslog.png)

- auth.log
![auth-log](screenshots/auth_log.png)
<font color="lime">`last login`</font>

- To restart ssh service uses command <font color="cyan">_sudo systemctl restart ssh.service_</font>

![ssh-restart](screenshots/ssh_restart.png)

## Using the CRON job scheduler

- <font color="cyan">_vim crontab -e_</font>
![cron](screenshots/cron.png)
![cron-log](screenshots/cron_log.png)