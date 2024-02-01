# kubectl-minikube
# kube ctl and minikube installation on virtual box with ubuntu image

# update the inage
sudo apt update

# follow the below link 
https://www.linuxbuzz.com/install-minikube-on-ubuntu/

# it throws the below error after kubectl installl
![Screenshot from 2024-02-01 21-10-28](https://github.com/vinaym10/kubectl-minikube/assets/142900477/c68dfbcc-ec41-4224-a938-868a38d0cbf4)
inikube v1.32.0 on Ubuntu 22.04
✨  Using the virtualbox driver based on existing profile
👍  Starting control plane node minikube in cluster minikube
🔄  Restarting existing virtualbox VM for "minikube" ...
🤦  StartHost failed, but will try again: driver start: Unable to start the VM: /usr/bin/VBoxManage startvm minikube --type headless failed:
VBoxManage: error: VT-x is not available (VERR_VMX_NO_VMX)
VBoxManage: error: Details: code NS_ERROR_FAILURE (0x80004005), component ConsoleWrap, interface IConsole

Details: 00:00:01.532117 Power up failed (vrc=VERR_VMX_NO_VMX, rc=NS_ERROR_FAILURE (0X80004005))
🔄  Restarting existing virtualbox VM for "minikube" ...
😿  Failed to start virtualbox VM. Running "minikube delete" may fix it: driver start: Unable to start the VM: /usr/bin/VBoxManage startvm minikube --type headless failed:
VBoxManage: error: VT-x is not available (VERR_VMX_NO_VMX)
VBoxManage: error: Details: code NS_ERROR_FAILURE (0x80004005), component ConsoleWrap, interface IConsole

Details: 00:00:00.820780 Power up failed (vrc=VERR_VMX_NO_VMX, rc=NS_ERROR_FAILURE (0X80004005))

❌  Exiting due to HOST_VTX_UNAVAILABLE: Failed to start host: driver start: Unable to start the VM: /usr/bin/VBoxManage startvm minikube --type headless failed:
VBoxManage: error: VT-x is not available (VERR_VMX_NO_VMX)
VBoxManage: error: Details: code NS_ERROR_FAILURE (0x80004005), component ConsoleWrap, interface IConsole


# to resolve the  above error delete the minikube
minikube delete

# again start the minikube
minikube start

# then it will installed
minikube status
kubectl get pods
kubectl get pods -o wide

# after to login to the pod
minikube ssh
curl <ip address>
