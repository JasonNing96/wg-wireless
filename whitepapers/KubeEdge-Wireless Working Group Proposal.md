KubeEdge-Wireless Working Group Proposal

# KubeEdge-Wireless Working Group Proposal

Author: Jason Ning

### **Target:** 

- Our goal is to make an open platform to enable **Wireless**-Edge computing, extending native containerized application orchestration capabilities to hosts at **Wireless**-Edge, which built upon kubernetes and provides fundamental infrastructure support for **Wireless**-network, app deployment and meta-data synchronization between cloud and **Wireless**-edge.
- **Extend** KubeEdge to support **wireless mobile scenarios**.

### Intention:

- With the development of computing, powerful computing equipment could be seen as multi-agent. Therefore, the  problem of wireless interaction between multiple agents is the main scenario discussed here. 
- The relationship between different kubeedge can not be easily seen as Online or Offline,  it should be a curve that is  normally distributed.

#### Scenario：

##### 	Vehicle Network/Vessel network/UAV network:

<img src="KubeEdge-Wireless Working Group Proposal-English.assets/image-20210203172851933-1612775632507.png" alt="image-20210203172851933" style="zoom:50%;" />

**Key differences** between wireless and wire:  

- Communication mode may need to change from TCP, IP mode to multi-cast or broadcast mode.
- Network for dynamics scenarios.  

With the development of computing, powerful computing equipment could be seen as multi-agent. Therefore, the  problem of wireless interaction between multiple agents is the main scenario discussed here. 

**Description**:  In the mobile scenario, multiple vehicles support similar service, and each vehicles wireless connected with each other as a KubeEdge node. (e.g. NIO ET7 with NVIDIA Orin * 4 , which has computing power of 1016 TOPS)

- Off-line autonomy and node management: Five cars form an mesh network, which can trans information processing between each other in off-line conditions.
- Leader Selection: Choose a pod as cluster head, to do the overall management of other equipments.
- KubeEdge-wireless should monitor the whole or partly state of network, to aid in networking decisions.
- According to the Service Level Agreement, KubeEdge makes decisions on the networking mode and limits the networking scope.
- Inspired by 3GPP 36.885 standards.

##### **Air/Sea rescue Collaboration：**

<img src="E:\3.项目相关\KubeEdge-Wireless Working Group\JPG\Kube-Wireless流程图-海洋搜救.png" alt="Kube-Wireless流程图-海洋搜救" style="zoom: 67%;" />

- The environmental complexity of the sea and sky makes communication more difficult
- The lack of base station support in this scenario necessitates a change in the communication mode.
- The search area is enlarged, but the individual energy is limited, and cluster head is needed for management.
- It is necessary to study the dynamic network structure topology to cope with the constantly changing environment of airspace and sea area.



**Proposal:**

- Kubeedge has the ability to manager the complex wireless networking statue without sensing by service.
-  Blurring the boundary between cloud and edge cloud gives KubeEdge more combination ways.
- Explore the requirements for kubeEdge in wireless scenario. 

#### To-Do：

- With the change of networking mode, the traditional communication mode of KubeEdge needs to be extended.

- Topologies will constantly changing, and the scheduling of communication capabilities will become a critical issue.

  - Willing to consider the situation of poor network channel quality.
  - Actively consider the network instability caused by mobility, especial for users joint and exit suddenly.
  - Active feedback to adjust the network, active networking.
- Cloud Native capability down sinking

  - Enable the edge devices to self-organize network and partial autonomy when off-line or discontinuous network. 

  - In most cases, multiple edge devices may spontaneously network to form a small group, and the outside world can join or quit the group.



#### Architecture:

<img src="../JPG/image-20210131223645659.png" alt="image-20210131223645659" style="zoom: 67%;" />

- Provide management abilities for Edge Cluster when disconnecting from the Cloud by selecting an Edge Head; 
- Add Network profiler module to monitor and manage the Edge cluster network resources, which can provide network information for the Edge Head section;
- Edge Cluster management in the dynamic network environment by creating Edge mesh network and the Edge Head
- Support wireless mesh mode for networking, which allow kubeEdge computing nodes quickly  join and exit mesh networking in mobile scenario.

**Network topology management** 

\-    Head selection algorithm

**Computing/Networking resources profilers** 

\-    Computing resources management 

\-    Networking resources management

##### Wireless-Mesh protocol stack

-  Storage the protocols for wireless-networking, including 802.11 mesh protocol, communication source topology, computing source topology and network parameter.

#### **Areas of Focus**

   Wireless communication tech, reenforcement learning, multi-access protocol, Invoke the schema on the communication computing topology，

##### **Participating unit **：

PengCheng Lab，DLMU(Dalian Maritime University)，Shanghai University of Science and Technology，SEU(Southeast University )，SJTU(ShangHai JiaoTong university)，CUCC(China Union Communication corporation)



 