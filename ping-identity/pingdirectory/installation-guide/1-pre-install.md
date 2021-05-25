# 1\) Pre-install

## Install Java \(Amazon Corretto 11 on Amazon Linux 2\)

```text
sudo yum install java-11-amazon-corretto -y

sudo tee -a /etc/profile.d/jdk_home.sh << END
#!/bin/sh
export JAVA_HOME="/usr/lib/jvm/java-11-amazon-corretto.x86_64"
END

source /etc/profile.d/jdk_home.sh
```

## Install Userland Dependencies \(RHEL/Centos/Amazon Linux 2\)

```text
# Install sysstat - Why?
# Install gdb - Why?
# Install dstat -  Why?
sudo yum install sysstat gdb dstat -y
```

## Linux Configuration

```text
#Confirm the vm.swappiness is 0.
#Expect errors similar to "The Linux kernel parameter vm.swappiness is set to '60' instead of '0'."

echo "vm.swappiness = 0" > /etc/sysctl.conf
```

## Create group and user

```text
groupadd --gid 9999 identity 
useradd --uid 9031 --gid identity --shell /bin/false ping
```

## Ping ENV

```text
sudo tee -a /etc/profile.d/ping_env.sh << END
#!/bin/sh
export PF_HOME="/home/ec2-user/pingfederate-10.2.2/pingfederate"
END

source /etc/profile.d/ping_env.sh
```

## Extract PingDirectory zip to /opt/ping/pingdirectory

Excluding Windows files

```text
unzip /tmp/pingdir.zip -d /tmp/ \
        -x *.bat \
        -x *.dll \
        -x *.exe
    && mv /tmp/PingDirectory /opt/ping/pingdirectory
```

## Generate safe Passwords

```text
openssl rand -hex 32

```

