# CentOS Template For VMware vCenter

## CLI Commands

`````````````````````
yum -y update
yum -y install yum-utils
service rsyslog stop
service auditd stop
package-cleanup --oldkernels -y –count=1
yum clean all
logrotate -f /etc/logrotate.conf
rm -f /var/log/*-???????? /var/log/*.gz
rm -f /var/log/dmesg.old
rm -rf /var/log/anaconda
cat /dev/null > /var/log/audit/audit.log
cat /dev/null > /var/log/wtmp
cat /dev/null > /var/log/lastlog
cat /dev/null > /var/log/grubby
rm -f /etc/udev/rules.d/70*
sed -i".bak" '/UUID/d' /etc/sysconfig/network-scripts/ifcfg-ens192
rm -f /etc/ssh/*key*
rm -f ~root/.bash_history
unset HISTFILE
history -c
sys-unconfig
`````````````````````
