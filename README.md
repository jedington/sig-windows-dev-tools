# KubernetesOnWindows

This guide is based on [this very nice Vagrantfile](https://gist.github.com/danielepolencic/ef4ddb763fd9a18bf2f1eaaa2e337544) and this very good [guide on how install Kubernetes on Ubuntu Focal (20.04)](https://github.com/mialeevs/kubernetes_installation). I hope I can later also automaize setup of the linux vm for Kuberntes in the Vagrantfile. At the moment this is done by hand, by this guide.

Common for worker and master nodes:

bridged traffic to iptables is enabled for kube-router:
```
echo "net.bridge.bridge-nf-call-iptables=1" | sudo tee -a /etc/sysctl.conf
echo "net.bridge.bridge-nf-call-ip6tables=1" | sudo tee -a /etc/sysctl.conf
echo "net.bridge.bridge-nf-call-arptables=1" | sudo tee -a /etc/sysctl.conf
sudo sysctl -p
```
disable swap
```
swapoff -a
sudo sed -i '/swap/d' /etc/fstab
```


Here is a [guide on how to install Docker on Win Server 2019](https://www.hostafrica.co.za/blog/new-technologies/how-to-install-docker-on-linux-and-windows/#win) and another [guide on how to install Kubernetes on Win Server 2019](https://www.hostafrica.co.za/blog/new-technologies/install-kubernetes-cluster-windows-server-worker-nodes/)
