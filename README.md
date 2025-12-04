ceph的部署
hostnamectl set-hostname ceph01
cat /etc/hosts <<EOF
>192.168.5.20 ceph01
>EOF
yum install -y wget vim chrony
systemctl enable chronyd --now
chronyc -sources

ceph.repo
vim ceph.repo 
[ceph]
name=ceph x86_64
baseurl=https://repo.huaweicloud.com/ceph/rpm-pacific/el8/x86_64
enable=1
gpgcheck=0

[ceph-naorth]
name=ceph noarch
baseurl=https://repo.huaweicloud.com/ceph/rpm-pacific/el8/noarch
enable=1
gpgcheck=0

[ceph-source]
name=ceph SRPMS
baseurl=https://repo.huaweicloud.com/ceph/rpm-pacific/el8/SRPMS
enable=1
gpgcheck=0


kubernetes的部署
