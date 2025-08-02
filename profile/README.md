## CoHDI Project: Vision Statement
The objective is to foster a community-driven, standards-based open ecosystem for next-generation architectures and frameworks built on Composable Hardware Disaggregated Infrastructure ([CoHDI](https://github.com/CoHDI/.github/blob/main/README.md), pronounced "Cody"), also known as Composable Disaggregated Infrastructure.  
CoHDI enables data center operators to realize the benefits of cost efficiency, high availability, and sustainability through a disaggregated computing system.
However, a gap still exists between Kubernetes and CoHDI, making it challenging to achieve more dynamic composability within the Kubernetes cloud-native environment.
The DDS project and Composable Resource Operator project aim to bridge this gap by collaborating with Dynamic Resource Allocation, sig-node, sig-autoscaling and sig-scheduling projects.

## How it works
The CoHDI system consists of a hardware-disaggregated resource pool and the Composable Manager (CoHDI Manager) software. Within the resource pool, all components are interconnected via PCIe or CXL switches. The CoHDI Manager orchestrates these switches to dynamically compose bare-metal hardware servers through software-defined configurations. It provides a Composable Resource API, which can be accessed by either the Composable Resource Operator or Kubernetes API.

![image](https://github.com/user-attachments/assets/d9d35ebd-c695-4ff6-b78a-19fcb718925d)

How CoHDI works:  
![how cohdi works]( )


GPU Hot-Add Demonstration: A pod request triggers an increase in the number of GPUs attached to a node, from 1 to 2:  
![demo_hotadd](https://raw.githubusercontent.com/CoHDI/.github/main/profile/demo_hotadd.gif)

GPU Hot-Remove Demonstration: Pod deletion triggers a decrease in the number of GPUs attached to a node, from 2 to 1:  
![demo_hodremove](https://raw.githubusercontent.com/CoHDI/.github/main/profile/demo_hotremove.gif)

[Composable DRA Driver](https://github.com/CoHDI/composable-dra-driver)

[Dynamic Device Scaler](https://github.com/CoHDI/dynamic-device-scaler)

[Composable Resource Operator](https://github.com/InfraDDS/composable-resource-operator)

[Policies](https://github.com/InfraDDS/Policies)
