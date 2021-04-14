# 1\) Pre-install

## Install Java \(Amazon Corretto 11 on Amazon Linux 2\)

```text
sudo yum install java-11-amazon-corretto -y

sudo tee -a /etc/profile.d/jdk_home.sh << END
#!/bin/sh
export JAVA_HOME="/usr/lib/jvm/java-11-amazon-corretto.x86_64"
export PATH=${JAVA_HOME}/bin:$PATH
END

```

## Install userland dependencies \(Amazon Linux 2\)

```text
# Install sysstat - Why?
# Install gdb - Why?
# Install dstat -  Why?
sudo yum install sysstat gdb dstat -y
```

## Linux Configuration

```text
#Confirm the vm.swappiness is 0.
echo "vm.swappiness = 0" > /etc/sysctl.conf
```

## Create group and user

```text
groupadd --gid 9999 identity 
useradd --uid 9031 --gid identity --shell /bin/false ping
```

