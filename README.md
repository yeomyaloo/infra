# 🏗️ Infra Study — Docker에서 OpenStack까지

하루에 한 주제씩, 컨테이너 한 개에서 시작해 프라이빗 클라우드까지 점진적으로 키워가는 인프라 학습 기록입니다.

```
Docker (컨테이너 1개)  →  Kubernetes (컨테이너 오케스트레이션)  →  가상화·네트워크 기초  →  OpenStack (프라이빗 클라우드)  →  OpenStack 위에 Kubernetes
```

## 📚 로드맵

### Chapter 1. Docker — 컨테이너 하나를 제대로 다루기
| Day | 주제 | 상태 |
|---|---|---|
| 01 | [컨테이너와 Docker 첫걸음](01-docker/day01-container-basics.md) | ✅ |
| 02 | 이미지와 레이어 구조 (Union FS, 이미지 태그, 레지스트리) | ⬜ |
| 03 | Dockerfile 작성과 멀티 스테이지 빌드 | ⬜ |
| 04 | 데이터 영속성 — Volume / Bind Mount / tmpfs | ⬜ |
| 05 | Docker 네트워크 — bridge / host / none / 사용자 정의 네트워크 | ⬜ |
| 06 | Docker Compose로 멀티 컨테이너 앱 구성 (Web + DB + Cache) | ⬜ |
| 07 | 컨테이너 내부 원리 — namespace, cgroup, 그리고 보안 기초 | ⬜ |

### Chapter 2. Kubernetes — 여러 컨테이너를 자동으로 운영하기
| Day | 주제 | 상태 |
|---|---|---|
| 08 | 왜 오케스트레이션인가 & K8s 아키텍처 | ⬜ |
| 09 | 로컬 클러스터 구축 (kind / minikube) & kubectl 기초 | ⬜ |
| 10 | Pod — 가장 작은 배포 단위 | ⬜ |
| 11 | ReplicaSet & Deployment — 롤링 업데이트와 롤백 | ⬜ |
| 12 | Service — ClusterIP / NodePort / LoadBalancer | ⬜ |
| 13 | ConfigMap & Secret | ⬜ |
| 14 | 스토리지 — Volume / PV / PVC / StorageClass | ⬜ |
| 15 | Ingress로 외부 트래픽 라우팅 | ⬜ |
| 16 | Helm으로 패키지 관리 | ⬜ |
| 17 | 모니터링 — Prometheus & Grafana | ⬜ |
| 18 | 오토스케일링 (HPA) & 리소스 관리 | ⬜ |
| 19 | RBAC & 네임스페이스로 멀티테넌시 | ⬜ |
| 20 | kubeadm으로 멀티노드 클러스터 직접 구축 | ⬜ |

### Chapter 3. 가상화 & 네트워크 기초 — OpenStack을 위한 준비
| Day | 주제 | 상태 |
|---|---|---|
| 21 | 하이퍼바이저와 KVM / QEMU / libvirt | ⬜ |
| 22 | 리눅스 네트워킹 — bridge, veth, network namespace | ⬜ |
| 23 | VLAN과 VXLAN, Overlay 네트워크 | ⬜ |
| 24 | Open vSwitch 기초 | ⬜ |

### Chapter 4. OpenStack — 나만의 프라이빗 클라우드
| Day | 주제 | 상태 |
|---|---|---|
| 25 | OpenStack 개요와 아키텍처 | ⬜ |
| 26 | DevStack으로 올인원 설치 | ⬜ |
| 27 | Keystone — 인증과 프로젝트 | ⬜ |
| 28 | Glance — 이미지 서비스 | ⬜ |
| 29 | Nova — 컴퓨트(인스턴스) 서비스 | ⬜ |
| 30 | Neutron — 네트워크 서비스 | ⬜ |
| 31 | Cinder & Swift — 블록/오브젝트 스토리지 | ⬜ |
| 32 | Heat — 오케스트레이션 템플릿 | ⬜ |
| 33 | Kolla-Ansible로 멀티노드 배포 (OpenStack을 컨테이너로!) | ⬜ |

### Chapter 5. 종합 프로젝트
| Day | 주제 | 상태 |
|---|---|---|
| 34 | OpenStack VM 위에 Kubernetes 클러스터 구축 | ⬜ |
| 35 | Terraform으로 전체 인프라 코드화 (IaC) | ⬜ |

> 로드맵은 진행하면서 조정될 수 있습니다.

## 📁 폴더 구조
```
infra/
├── README.md
├── 01-docker/
│   ├── day01-container-basics.md
│   └── images/
├── 02-kubernetes/
├── 03-virtualization-network/
├── 04-openstack/
└── 05-capstone/
```
