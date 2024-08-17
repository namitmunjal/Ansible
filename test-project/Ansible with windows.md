## To connect to a Windows machine using Ansible we need to do the following.

- Windows machine should be pingable.
- install pywinrm and kerberos on the ansible master using below command
> pip install pywinrm requests-kerberos

- ConfigureRemotingForWindows.ps1 run this script on the windows machine. This will enable winrm, https, ssl certificate and other services required for the connectivity.
- prepare the host file with windowns ip and parameters to connect to it.
- test via running the ping module
> ansible win -i hosts -m win_ping

### Installing ansible windows modules
- we can install ansible.windows modules using below command.
> ansible-galaxy collection install ansible.windows

### Connecting to a windows machine in a domain
- the machine should be part of a domain
- we need to use NTLM or Kerberos method to authenticate with the windows machine.
- install development tools

> sudo yum groupinstall "Development Tools"

> sudo yum install krb5-server krb5-libs

> sudo yum install gcc python3-devel krb5-devel -y

> sudo yum install krb5-workstatio

> pip install kerberos



