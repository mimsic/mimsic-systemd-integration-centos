# mimsic-systemd-integration-centos

To run the centos docker container:
Note: arz1120 is docker hub account. You may create your own docker hub account.
docker build --rm -t arz1120/centos-systemd:1 .
docker docker run -dit --name centos-container --privileged=true -v /sys/fs/cgroup:/sys/fs/cgroup:ro -p 80:80 arz1120/centos-systemd:1

To update the centos and install docker service in the centos docker container, run the following commands:
yum update -y
yum install -y yum-utils
yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
yum install docker-ce docker-ce-cli containerd.io docker-compose-plugin
systemctl start docker
