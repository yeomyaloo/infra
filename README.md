# 🏗️ Infra Study — Docker에서 OpenStack, 그리고 AI 인프라까지

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

### Chapter 6. AI 인프라 — LLM 서버 띄우고 RAG 운영하기
| Day | 주제 | 상태 |
|---|---|---|
| 36 | [AI 인프라 개요 — LLM 서빙 스택과 GPU·VRAM 계산](06-ai-infra/day36-ai-infra-overview.md) | ✅ |
| 37 | [GPU 서버 준비 — NVIDIA 드라이버, CUDA, Container Toolkit](06-ai-infra/day37-gpu-server.md) | ✅ |
| 38 | [Ollama로 로컬 LLM 띄우기 & Open WebUI](06-ai-infra/day38-ollama.md) | ✅ |
| 39 | [vLLM으로 고성능 LLM 서빙 (OpenAI 호환 API)](06-ai-infra/day39-vllm.md) | ✅ |
| 40 | [LLM 게이트웨이 — LiteLLM으로 모델 통합·키·사용량 관리](06-ai-infra/day40-llm-gateway.md) | ✅ |
| 41 | [임베딩과 벡터 DB — Qdrant / pgvector](06-ai-infra/day41-embedding-vectordb.md) | ✅ |
| 42 | [RAG 파이프라인 직접 만들기 (청킹·검색·생성)](06-ai-infra/day42-rag-pipeline.md) | ✅ |
| 43 | [RAG 서비스 컨테이너화 & Docker Compose 통합](06-ai-infra/day43-rag-compose.md) | ✅ |
| 44 | [Kubernetes에서 GPU 쓰기 — GPU Operator, Time-slicing/MIG](06-ai-infra/day44-k8s-gpu.md) | ✅ |
| 45 | [Kubernetes에 LLM 서빙 배포 — vLLM, 모델 캐시, KServe](06-ai-infra/day45-llm-on-k8s.md) | ✅ |
| 46 | [LLM 오토스케일링 — KEDA, 큐 기반 확장, Scale-to-zero](06-ai-infra/day46-llm-autoscaling.md) | ✅ |
| 47 | [LLM 관측성 — TTFT·처리량·KV 캐시 모니터링, 트레이싱](06-ai-infra/day47-llm-observability.md) | ✅ |
| 48 | [LLM 보안·가드레일·RAG 평가](06-ai-infra/day48-llm-security-eval.md) | ✅ |
| 49 | [종합 — 홈랩 K8s에 사내 문서 RAG 챗봇 운영하기](06-ai-infra/day49-capstone-rag-chatbot.md) | ✅ |

### Chapter 7. GitOps & CI/CD — Git 하나로 배포까지 자동화하기
| Day | 주제 | 상태 |
|---|---|---|
| 50 | [CI/CD와 GitOps — Push 배포 vs Pull 배포](07-gitops/day50-cicd-vs-gitops.md) | ✅ |
| 51 | [GitHub Actions로 이미지 빌드·테스트·푸시 (GHCR, 캐시, 멀티 아키텍처)](07-gitops/day51-github-actions.md) | ✅ |
| 52 | [Kustomize로 환경별(dev/stage/prod) 매니페스트 관리](07-gitops/day52-kustomize.md) | ✅ |
| 53 | [Argo CD 설치와 첫 GitOps 배포 (Auto-sync, Self-heal)](07-gitops/day53-argocd.md) | ✅ |
| 54 | [이미지 태그 자동 갱신(Argo CD Image Updater)과 환경 승격 흐름](07-gitops/day54-image-updater-promotion.md) | ✅ |
| 55 | [GitOps 시크릿 관리 — SOPS, External Secrets](07-gitops/day55-secrets.md) | ✅ |
| 56 | [Argo Rollouts로 점진적 배포 (Canary, Blue-Green)](07-gitops/day56-argo-rollouts.md) | ✅ |
| 57 | [공급망 보안 — Trivy, cosign, Kyverno](07-gitops/day57-supply-chain-security.md) | ✅ |

### Chapter 8. SRE & 관측성 — 숫자로 약속하고 지키기
| Day | 주제 | 상태 |
|---|---|---|
| 58 | [SRE 개념 — SLI/SLO/에러 버짓, 모니터링 vs 관측성](08-sre-observability/day58-sre-slo.md) | ✅ |
| 59 | [OpenTelemetry 계측 — 트레이스·메트릭·로그](08-sre-observability/day59-opentelemetry.md) | ✅ |
| 60 | [로그 수집 — Loki + Grafana Alloy](08-sre-observability/day60-loki-alloy.md) | ✅ |
| 61 | [분산 트레이싱 — Tempo](08-sre-observability/day61-tempo.md) | ✅ |
| 62 | [알림 설계 — Alertmanager, 증상 기반 알림, 알림 피로](08-sre-observability/day62-alerting.md) | ✅ |
| 63 | [SLO 기반 Canary 분석 — Argo Rollouts + Prometheus](08-sre-observability/day63-slo-canary.md) | ✅ |
| 64 | [카오스 엔지니어링 — Chaos Mesh](08-sre-observability/day64-chaos-mesh.md) | ✅ |
| 65 | [장애 대응과 회고 — 런북, 온콜, 비난 없는 포스트모템](08-sre-observability/day65-incident-postmortem.md) | ✅ |

### Chapter 9. 보안 — 4C 레이어별로 지키기
| Day | 주제 | 상태 |
|---|---|---|
| 66 | [위협 모델링과 클라우드 네이티브 보안 4C](09-security/day66-threat-modeling-4c.md) | ✅ |
| 67 | [리눅스 호스트 하드닝 — SSH, sudo, nftables, fail2ban, Lynis/CIS](09-security/day67-host-hardening.md) | ✅ |
| 68 | [컨테이너 런타임 보안 — rootless, capabilities, seccomp, AppArmor](09-security/day68-container-runtime-security.md) | ✅ |
| 69 | [K8s 워크로드 보안 — Pod Security Admission, securityContext, kube-bench](09-security/day69-k8s-workload-security.md) | ✅ |
| 70 | [NetworkPolicy와 제로 트러스트, mTLS](09-security/day70-networkpolicy-zero-trust.md) | ✅ |
| 71 | [시크릿·인증서 — OpenBao/Vault, cert-manager](09-security/day71-vault-cert-manager.md) | ✅ |
| 72 | [런타임 위협 탐지 — Falco](09-security/day72-falco.md) | ✅ |
| 73 | [인증 통합과 감사 — Keycloak OIDC SSO, K8s 감사 로그](09-security/day73-keycloak-sso-audit.md) | ✅ |

> 로드맵은 진행하면서 조정될 수 있습니다.

## 🧪 실습 환경 기준
| 항목 | 버전 / 도구 |
|---|---|
| OS | Ubuntu 24.04 LTS (Windows는 Docker Desktop + WSL2) |
| Kubernetes | v1.34 이상 (로컬: kind `infra-lab` 클러스터, 멀티노드: kubeadm. Chapter 9 일부 실습은 최신 kind 노드 v1.37 기준) |
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
├── 05-capstone/                # Chapter 5. 종합 프로젝트 (Day 34~35)
├── 06-ai-infra/                # Chapter 6. AI 인프라 (Day 36~49)
├── 07-gitops/                  # Chapter 7. GitOps & CI/CD (Day 50~57)
├── 08-sre-observability/       # Chapter 8. SRE & 관측성 (Day 58~65)
└── 09-security/                # Chapter 9. 보안 (Day 66~73)
    └── (각 폴더) images/       # 글에 쓰인 다이어그램 (SVG)
```
