Bug?
Message:

Last Transition Time:  2026-10-15T03:47:54Z
        Message:               error reconciling the Cluster topology: failed to create patch helper for ProxmoxMachineTemplate proxmoxday/mycapicluster-rszmh: server side apply dry-run failed for modified object: admission webhook "validation.proxmoxmachinetemplate.infrastructure.cluster.x-k8s.io" denied the request: ProxmoxMachineTemplate.infrastructure.cluster.x-k8s.io "mycapicluster-rszmh" is invalid: spec: Forbidden: ProxmoxMachineTemplate is immutable
        Reason:                TopologyReconcileFailed
        Severity:              Error 

Alos wird ein Error geworfen

# CAPI-Contract

Aber laut release-1-4.cluster-api.sigs.k8s.io/developer/providers/webhooks 
-> Validating webhooks implemented for a InfrastructureMachineTemplate or BootstrapConfigTemplate resource are required to not block due to immutability checks when the controller for managed topology and ClusterClass does Server Side Apply dry-run requests

# Ergo 
Die message von oben darf nicht erscheinen

-> https://github.com/ionos-cloud/cluster-api-provider-proxmox/pull/735
