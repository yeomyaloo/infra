# 🏗️ Infra Study — Docker에서 OpenStack까지

하루에 한 주제씩, 컨테이너 한 개에서 시작해 프라이빗 클라우드까지 점진적으로 키워가는 인프라 학습 기록입니다.

```
홈랩 서버 준비  →  Docker (컨테이너 1개)  →  Kubernetes (오케스트레이션)  →  가상화·네트워크 기초  →  OpenStack (프라이빗 클라우드)  →  OpenStack 위 Kubernetes + IaC  →  AI 인프라
```

각 글은 **목표 → 개념(그림) → 실습 → 트러블슈팅 → 핵심 정리 → 셀프 체크 퀴즈 → 다음 예고** 순서로 구성됩니다.

## 📚 로드맵

### Chapter 0. 홈랩 — 남는 노트북/PC를 서버로 (번외)
| 편 | 주제 | 상태 |
|---|---|---|
| H01 | [깡통 노트북/PC에 Ubuntu Server 설치하고 서버로 만들기](00-homelab/homelab01-ubuntu-server.md) | ✅ |
| H02 | [공유기 포트포워딩·DDNS로 외부에서 접속하기](00-homelab/homelab02-router-port-forwarding.md) | ✅ |
| H03 | [포트 안 열고 안전하게 공개하기 (Cloudflare Tunnel / Tailscale / HTTPS)](00-homelab/homelab03-safe-exposure.md) | ✅ |

### Chapter 1. Docker — 컨테이너 하나를 제대로 다루기
| Day | 주제 | 상태 |
|---|---|---|
| 01 | [컨테이너와 Docker 첫걸음](01-docker/day01-container-basics.md) | ✅ |
| 02 | [이미지와 레이어 구조 (Union FS, 이미지 태그, 레지스트리)](01-docker/day02-image-layers.md) | ✅ |
| 03 | [Dockerfile 작성과 멀티 스테이지 빌드](01-docker/day03-dockerfile.md) | ✅ |
| 04 | [데이터 영속성 — Volume / Bind Mount / tmpfs](01-docker/day04-volumes.md) | ✅ |
| 05 | [Docker 네트워크 — bridge / host / none / 사용자 정의 네트워크](01-docker/day05-network.md) | ✅ |
| 06 | [Docker Compose로 멀티 컨테이너 앱 구성 (Web + DB + Cache)](01-docker/day06-compose.md) | ✅ |
| 07 | [컨테이너 내부 원리 — namespace, cgroup, 그리고 보안 기초](01-docker/day07-container-internals.md) | ✅ |

### Chapter 2. Kubernetes — 여러 컨테이너를 자동으로 운영하기
| Day | 주제 | 상태 |
|---|---|---|
| 08 | [왜 오케스트레이션인가 & K8s 아키텍처](02-kubernetes/day08-k8s-architecture.md) | ✅ |
| 09 | [로컬 클러스터 구축 (kind / minikube) & kubectl 기초](02-kubernetes/day09-local-cluster-kubectl.md) | ✅ |
| 10 | [Pod — 가장 작은 배포 단위](02-kubernetes/day10-pod.md) | ✅ |
| 11 | [ReplicaSet & Deployment — 롤링 업데이트와 롤백](02-kubernetes/day11-deployment.md) | ✅ |
| 12 | [Service — ClusterIP / NodePort / LoadBalancer](02-kubernetes/day12-service.md) | ✅ |
| 13 | [ConfigMap & Secret](02-kubernetes/day13-configmap-secret.md) | ✅ |
| 14 | [스토리지 — Volume / PV / PVC / StorageClass](02-kubernetes/day14-storage.md) | ✅ |
| 15 | [Ingress & Gateway API로 외부 트래픽 라우팅](02-kubernetes/day15-ingress.md) | ✅ |
| 16 | [Helm으로 패키지 관리](02-kubernetes/day16-helm.md) | ✅ |
| 17 | [모니터링 — Prometheus & Grafana](02-kubernetes/day17-monitoring.md) | ✅ |
| 18 | [오토스케일링 (HPA) & 리소스 관리](02-kubernetes/day18-autoscaling.md) | ✅ |
| 19 | [RBAC & 네임스페이스로 멀티테넌시](02-kubernetes/day19-rbac-namespace.md) | ✅ |
| 20 | [kubeadm으로 멀티노드 클러스터 직접 구축](02-kubernetes/day20-kubeadm-multinode.md) | ✅ |

### Chapter 3. 가상화 & 네트워크 기초 — OpenStack을 위한 준비
| Day | 주제 | 상태 |
|---|---|---|
| 21 | [하이퍼바이저와 KVM / QEMU / libvirt](03-virtualization-network/day21-kvm-libvirt.md) | ✅ |
| 22 | [리눅스 네트워킹 — bridge, veth, network namespace](03-virtualization-network/day22-linux-networking.md) | ✅ |
| 23 | [VLAN과 VXLAN, Overlay 네트워크](03-virtualization-network/day23-vlan-vxlan.md) | ✅ |
| 24 | [Open vSwitch 기초](03-virtualization-network/day24-open-vswitch.md) | ✅ |

### Chapter 4. OpenStack — 나만의 프라이빗 클라우드
| Day | 주제 | 상태 |
|---|---|---|
| 25 | [OpenStack 개요와 아키텍처](04-openstack/day25-openstack-overview.md) | ✅ |
| 26 | [DevStack으로 올인원 설치](04-openstack/day26-devstack.md) | ✅ |
| 27 | [Keystone — 인증과 프로젝트](04-openstack/day27-keystone.md) | ✅ |
| 28 | [Glance — 이미지 서비스](04-openstack/day28-glance.md) | ✅ |
| 29 | [Nova — 컴퓨트(인스턴스) 서비스](04-openstack/day29-nova.md) | ✅ |
| 30 | [Neutron — 네트워크 서비스](04-openstack/day30-neutron.md) | ✅ |
| 31 | [Cinder & Swift — 블록/오브젝트 스토리지](04-openstack/day31-cinder-swift.md) | ✅ |
| 32 | [Heat — 오케스트레이션 템플릿](04-openstack/day32-heat.md) | ✅ |
| 33 | [Kolla-Ansible로 멀티노드 배포 (OpenStack을 컨테이너로!)](04-openstack/day33-kolla-ansible.md) | ✅ |

### Chapter 5. 종합 프로젝트
| Day | 주제 | 상태 |
|---|---|---|
| 34 | [OpenStack VM 위에 Kubernetes 클러스터 구축](05-capstone/day34-k8s-on-openstack.md) | ✅ |
| 35 | [Terraform으로 전체 인프라 코드화 (IaC)](05-capstone/day35-terraform.md) | ✅ |

### Chapter 6. AI 인프라 — LLM 서버 띄우고 운영하기 (다음 시즌 예정)
GPU 노드 구성, LLM 서빙 서버(vLLM / Ollama) 띄우기, RAG 파이프라인과 벡터 DB, Kubernetes 위에서 LLM 운영·모니터링

> 로드맵은 진행하면서 조정될 수 있습니다.

## 🧪 실습 환경 기준
| 항목 | 버전 / 도구 |
|---|---|
| OS | Ubuntu 24.04 LTS (Windows는 Docker Desktop + WSL2) |
| Kubernetes | v1.34 (로컬: kind `infra-lab` 클러스터, 멀티노드: kubeadm) |
| OpenStack | 2025.1 Epoxy 이후 (DevStack / Kolla-Ansible) |
| IaC | Terraform + terraform-provider-openstack (OpenTofu 호환) |

> 명령어 출력의 해시·IP·시간 등은 환경마다 다를 수 있습니다.

## 📁 폴더 구조
```
infra/
├── README.md
├── 00-homelab/                 # Chapter 0. 홈랩 (번외)
├── 01-docker/                  # Chapter 1. Docker (Day 01~07)
├── 02-kubernetes/              # Chapter 2. Kubernetes (Day 08~20)
├── 03-virtualization-network/  # Chapter 3. 가상화·네트워크 (Day 21~24)
├── 04-openstack/               # Chapter 4. OpenStack (Day 25~33)
└── 05-capstone/                # Chapter 5. 종합 프로젝트 (Day 34~35)
    └── (각 폴더) images/       # 글에 쓰인 다이어그램 (SVG)
```
