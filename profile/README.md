## CoHDI Project: Vision Statement
The objective is to cultivate a community-driven, standards-based ecosystem for next-generation architectures built on Composable Hardware in Disaggregated Infrastructure ([CoHDI](https://github.com/CoHDI/.github/blob/main/README.md), pronounced "Cody").
While Composable Disaggregated Infrastructure enables data center operators to unlock significant cost efficiency, high availability, and sustainability, a critical gap remains between Kubernetes and disaggregated hardware. This gap hinders the realization of truly dynamic composability within cloud-native environments. The CoHDI software suite—consisting of the Composable-DRA-Driver, Dynamic-Device-Scaler, and Composable Resource Operator—is designed to bridge this divide by integrating directly with Kubernetes' Dynamic Resource Allocation (DRA) and collaborating with the sig-node, sig-autoscaling, and sig-scheduling.

## How it works
The CoHDI system consists of a hardware-disaggregated resource pool and the Composable Manager (CoHDI Manager) software. Within the resource pool, all components are interconnected via PCIe or CXL switches. The CoHDI Manager orchestrates these switches to dynamically compose bare-metal hardware servers through software-defined configurations. It provides a Composable Resource API, which can be accessed by either the Composable Resource Operator or Kubernetes API.

<img width="880" height="516" alt="CoHDI-CoHDI-OSS drawio" src="https://github.com/user-attachments/assets/d8e3a3e9-b239-4dba-8450-c7d967b0684b" />

### K8s Internal Operation

![How Dynamic Device Scaler Works](https://github.com/CoHDI/dynamic-device-scaler/blob/main/doc/dds1.png)

- When we use current DRA, it checks and lists all attached devices in worker nodes to Resource slice. (1)
- We introduce new kind of resource slice for free devices (e.g. GPU) in resource pool. Composable-dra-driver checks the free devices in resource pool and lists them in the resource slice. (1)
- Now we assume user creates a new Pod requesting a non-existing GPU in worker nodes. (2)
- When scheduler tries to schedule the Pod and finds the GPU in Resource Slice for resource pool is available, scheduler waits to schedule the Pod. (3-1, 3-2, 4)
- After that , when Dynamic-device-scaler detects this situation, it requests to attach GPU through composabile-resource- operator custom resource. (5-1, 5-2)
- Composable-resource-operator requests attachment of GPU to rest API of CDI system. (6-1)
- Then Composable Hardware Dissagregated Infrastructure Manager controls PCI switch and attach a GPU to a worker node. (6-2)
- Once GPU is attached, vendor DRA plugin adds the GPU to Resource slice. (1)
- Finally the Pod is scheduled using attached GPU.

For more detailed information on each component, please refer to its respective repository in the CoHDI project.

See also [KEP-5007](https://github.com/kubernetes/enhancements/tree/master/keps/sig-scheduling/5007-device-attach-before-pod-scheduled).

#### How CoHDI works:

![how cohdi works](https://github.com/CoHDI/.github/blob/main/profile/how_cohdi_works.gif) 

#### GPU Hot-Add Demonstration: A pod request triggers an increase in the number of GPUs attached to a node, from 1 to 2:  
![demo_hotadd](https://raw.githubusercontent.com/CoHDI/.github/main/profile/demo_hotadd.gif)

### GPU Hot-Remove Demonstration: Pod deletion triggers a decrease in the number of GPUs attached to a node, from 2 to 1:  
![demo_hodremove](https://raw.githubusercontent.com/CoHDI/.github/main/profile/demo_hotremove.gif)

### Related Information
These are enhancement description for K8s scheduler.

For alpha release: [KEP-5007](https://github.com/KobayashiD27/enhancements/blob/174e2db180affcd647992b880dcb57b0d57b806a/keps/sig-scheduling/5007-device-attach-before-pod-scheduled/)

For beta release: [KEP-5007](https://github.com/kubernetes/enhancements/blob/a781dc2df7d413bc53e180ade416c7f38fa6e948/keps/sig-scheduling/5007-device-attach-before-pod-scheduled/)

## Adopters

[CoHDI Adopters](https://github.com/CoHDI/.github/blob/main/ADOPTERS.md)

## Slack Channel

[CoHDI Slack Channel](https://app.slack.com/client/T08PSQ7BQ/C09FPSSG690)

## CoHDI Repositories

[Composable DRA Driver](https://github.com/CoHDI/composable-dra-driver)

[Dynamic Device Scaler](https://github.com/CoHDI/dynamic-device-scaler)

[Composable Resource Operator](https://github.com/CoHDI/composable-resource-operator)

[.github](https://github.com/CoHDI/.github)
