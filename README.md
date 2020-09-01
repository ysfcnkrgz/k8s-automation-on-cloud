## Creating a sample kubernetes environment with istio service mesh on AWS 
 

Microservices have become a popular architectural style for building cloud-native applications that are self-contained, independently deployable, resilient and quickly evolve. Additionally, Istio makes it easy to create a network of deployed services with load balancing, service-to-service authentication, monitoring.

---

Therefore, you may use this sample code as a starting point for your development environment. 



## TODO 
> There will be 5 approaches to install kubernetes;
- EKSCTL
- KOPS
- Kubeadm 
- Kubespray
- Kubernetes - the hard way 

> Second part will be deploying istio and creating a sample service mash.

---
```shell script
export TF_VAR_AWS_ACCESS_KEY="accesskey"
export TF_VAR_AWS_SECRET_KEY="secretkey"
export TF_VAR_AWS_REGION="eu-west-2"
export TF_VAR_trusted_ip_range="$(curl http://ifconfig.co)/32"  # Or give your trusted IP range
export TF_VAR_PATH_TO_PUBLIC_KEY="$HOME/.ssh/automation.pub"
export TF_VAR_PATH_TO_PRIVATE_KEY="$HOME/.ssh/automation"
... and so on... ( Check vars.tf )
```

> In order to ssh to nodes, you may use ssh-config as below;
```shell script
$ ./create.sh config
$ ssh master-1 -F ./config
```

 
> Test 
```shell script
$ terraform validate
$ terraform fmt -check -diff 
$ chronic test.sh
$ ansible-playbook -i inventory/inventory.static test.yaml
$ ansible-playbook -i inventory/inventory.static test.yaml
$ python ./inventory/ec2.py --list
$ ansible -m ping "eu-west-2" -i inventory/ec2.py 
And many more will be added...

```