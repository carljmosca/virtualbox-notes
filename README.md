# virtualbox-notes
Notes for using VirtualBox
### Running VMs with “NAT Network” network setting can address VPN issue with VMs.  The “natdnsproxy1” setting allows the NAT engine to act as a DNS proxy so that VMs are not interrupted when the host DNS changes (i.e. on/off VPN).
```
VBoxManage modifyvm "VM name" --natdnsproxy1 on
```
Use port forwarding (to access VMs from host)
The individual VMs can access one another as needed on the NAT network

### Running Kubernetes on a VM via VirtualBox may require some settings adjustments depending on hardware.  Consider the following:
1. If running on a computer with a solid state drive, try turning on the “Solid-state Drive” option on the hard drive settings.  Some users have reported that this helps some operations.
1. Try using the “Use Host I/O Cache” setting on the hard drive controller.  Depending on needs, this option may help or hinder overall performance of both the host and VM.  In at least one case, it eliminated etcd errors as described here.
