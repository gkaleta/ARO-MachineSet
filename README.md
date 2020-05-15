# ARO-MachineSet
VM SKU Template

Also find your clustername and add it.

~~~sh
apiVersion: machine.openshift.io/v1beta1
kind: Machine
metadata:
  generateName: cluster-ms6lj-worker-eastus3-
  annotations:
    machine.openshift.io/instance-state: Running
  selfLink: >-
    /apis/machine.openshift.io/v1beta1/namespaces/openshift-machine-api/machines/cluster-ms6lj-worker-eastus3-f6jx4
  resourceVersion: '11629'
  name: cluster-ms6lj-worker-eastus3-f6jx4
  uid: d2b8a675-65f5-4e9c-b73b-0afedaa59dcb
  creationTimestamp: '2020-04-30T08:47:34Z'
  generation: 2
  namespace: openshift-machine-api
  ownerReferences:
    - apiVersion: machine.openshift.io/v1beta1
      blockOwnerDeletion: true
      controller: true
      kind: MachineSet
      name: cluster-ms6lj-worker-eastus3
      uid: a588f8a6-e949-40eb-b612-e0a22f385f9e
  finalizers:
    - machine.machine.openshift.io
  labels:
    machine.openshift.io/cluster-api-cluster: cluster-ms6lj
    machine.openshift.io/cluster-api-machine-role: worker
    machine.openshift.io/cluster-api-machine-type: worker
    machine.openshift.io/cluster-api-machineset: cluster-ms6lj-worker-eastus3
    ## machine.openshift.io/instance-type: Standard_D4s_v3 {REMEMBER TO CHANGE ME HERE!}
    machine.openshift.io/region: eastus
    machine.openshift.io/zone: '3'
spec:
  metadata:
    creationTimestamp: null
  providerID: >-
    ##azure:///subscriptions/{insert subid}/resourceGroups/aro-l4r80nwr/providers/Microsoft.Compute/virtualMachines/cluster-ms6lj-worker-eastus3-f6jx4
  providerSpec:
    value:
      osDisk:
        diskSizeGB: 128
        managedDisk:
          storageAccountType: Premium_LRS
        osType: Linux
      networkResourceGroup: aro-rg
      publicLoadBalancer: cluster-ms6lj
      userDataSecret:
        name: worker-user-data
      vnet: aro-vnet
      credentialsSecret:
        name: azure-cloud-credentials
        namespace: openshift-machine-api
      zone: '3'
      metadata:
        creationTimestamp: null
      publicIP: false
      resourceGroup: aro-l4r80nwr
      kind: AzureMachineProviderSpec
      location: eastus
      vmSize: Standard_D4s_v3
      image:
        offer: aro4
        publisher: azureopenshift
        resourceID: ''
        sku: aro_43
        version: 43.81.20200311
      subnet: worker-subnet
      apiVersion: azureproviderconfig.openshift.io/v1beta1
status:
  addresses:
    - address: cluster-ms6lj-worker-eastus3-f6jx4
      type: Hostname
    - address: cluster-ms6lj-worker-eastus3-f6jx4
      type: InternalDNS
    - address: >-
        cluster-ms6lj-worker-eastus3-f6jx4.tymd1hta3nee1etylrq2lfnyuc.bx.internal.cloudapp.net
      type: InternalDNS
    - address: 10.0.2.6
      type: InternalIP
  lastUpdated: '2020-04-30T08:53:06Z'
  nodeRef:
    kind: Node
    name: cluster-ms6lj-worker-eastus3-f6jx4
    uid: e6f19215-7835-491b-bed0-5a7f5131b470
  phase: Running
  providerStatus:
    conditions:
      - lastProbeTime: '2020-04-30T08:50:02Z'
        lastTransitionTime: '2020-04-30T08:47:54Z'
        message: machine successfully created
        reason: MachineCreationSucceeded
        status: 'True'
        type: MachineCreated
    metadata:
      creationTimestamp: null
    vmId: >-
      /subscriptions/{insert subID}/resourceGroups/aro-l4r80nwr/providers/Microsoft.Compute/virtualMachines/cluster-ms6lj-worker-eastus3-f6jx4
    vmState: Running

