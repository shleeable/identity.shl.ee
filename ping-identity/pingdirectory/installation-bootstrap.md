# Installation Bootstrap

## Install Java \(Amazon Corretto 11 on Amazon Linux 2\)

```text
sudo yum install java-11-amazon-corretto -y
export JAVA_HOME="/usr/lib/jvm/java-11-amazon-corretto.x86_64/"
export PATH=$JAVA_HOME/bin:$PATH
```

## Install userland dependencies \(Amazon Linux 2\)

```text
sudo yum install sysstat gdb dstat -y
```

## Linux Configuration

```text
#Confirm the vm.swappiness is 0.
echo "vm.swappiness = 0" > /etc/sysctl.conf
```



