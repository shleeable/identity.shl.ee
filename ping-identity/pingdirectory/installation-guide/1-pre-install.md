# 1\) Pre-install

## Install Java \(Amazon Corretto 11 on Amazon Linux 2\)

```text
sudo yum install java-11-amazon-corretto -y

sudo tee -a /etc/profile.d/jdk_home.sh << END
#!/bin/sh
export JAVA_HOME="/usr/lib/jvm/java-11-amazon-corretto.x86_64"
END

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
echo "vm.swappiness = 0" > /etc/sysctl.conf
```

## Create group and user

```text
groupadd --gid 9999 identity 
useradd --uid 9031 --gid identity --shell /bin/false ping
```

## Extract PingDirectory zip to /opt/ping/pingdirectory

Excluding Windows & unrequired files.

```text
unzip /tmp/PingDirectory-8.2.0.3.zip -d /tmp/ \
        -x *.bat \
        -x *.dll \
        -x *.exe \
        -x */start-ds \
        -x */stop-ds \
        -x */uninstall \
        -x */webapps/* \
        -x */resource/*.zip \
        -x */_script-util.sh \
        -x */lib/wrapper.jar \
    && find /tmp/PingDirectory/docs -type f \
        ! -iname "unboundid.css" \
        ! -path "/tmp/PingDirectory/docs/images/*" \
        ! -path "/tmp/PingDirectory/docs/rest-api-specs/*" \
        -delete \
    && mv /tmp/PingDirectory /opt/ping/pingdirectory
```



