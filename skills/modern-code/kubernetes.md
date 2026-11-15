# Kubernetes

- **Covers:** 1.21 to 1.37
- **Declared version:** the cluster version the repository pins, such as an RKE2 or Talos
  version or kubeadm's `kubernetesVersion`. Otherwise the server version from
  `kubectl version`. Ask when neither is available.
- **Release notes:** `https://git.k8s.io/kubernetes/CHANGELOG/CHANGELOG-1.N.md`
- **Format:** none. Validate with the project's own task when it has one, otherwise
  `kubectl apply --dry-run=server --validate=strict -f FILE`.
- **Modernize:** `https://kubernetes.io/docs/reference/using-api/deprecation-guide/`, and
  the `Warning` headers the API server returns for deprecated APIs

| Since | Prefer |
| --- | --- |
| 1.21 | `batch/v1` CronJob, `policy/v1` PodDisruptionBudget, `discovery.k8s.io/v1` EndpointSlice over `v1` Endpoints |
| 1.22 | projected `serviceAccountToken` volume, TokenRequest API |
| 1.23 | `autoscaling/v2` HPA, Job `ttlSecondsAfterFinished` |
| 1.24 | `storage.k8s.io/v1` CSIStorageCapacity, `node-role.kubernetes.io/control-plane` |
| 1.25 | `pod-security.kubernetes.io/` namespace labels, NetworkPolicy `endPort`, `kubectl debug --target`, `registry.k8s.io`, CSI drivers |
| 1.27 | `grpc` probes, CronJob `timeZone`, `kubectl.kubernetes.io/default-container` |
| 1.29 | `flowcontrol.apiserver.k8s.io/v1`, `ReadWriteOncePod`, KMS v2 |
| 1.30 | ValidatingAdmissionPolicy |
| 1.31 | `securityContext.appArmorProfile`, `--cloud-provider=external` |
| 1.32 | StatefulSet `persistentVolumeClaimRetentionPolicy` |
| 1.33 | sidecars in `initContainers` with `restartPolicy: Always`, PVC `dataSourceRef`, kube-proxy `nftables`, `service.kubernetes.io/topology-mode: Auto` |
| 1.34 | `--authentication-config`, kubelet cgroup driver from the CRI |
| 1.35 | Pod `resize` subresource, `trafficDistribution: PreferSameZone` |
| 1.36 | MutatingAdmissionPolicy, RBAC on `nodes/pods`, `nodes/healthz`, `nodes/configz` |
| 1.37 | `metrics.k8s.io/v1`, `storagemigration.k8s.io/v1`, `podCertificate` volume, HPA `behavior.scaleUp.tolerance` |

Ingress is frozen but not deprecated, so no warning reports it. The Kubernetes docs
recommend Gateway API (`gateway.networking.k8s.io/v1`) instead, and the ingress-nginx
controller gets no releases or security fixes after March 2026.