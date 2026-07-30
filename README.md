# 미션1: 개발 워크스테이션 구축

## 1. 프로젝트 개요
개발 환경(터미널, Docker, Git)을 직접 세팅하고 검증하는 미션

---

## 2. 실행 환경
| 항목 | 내용 |
|------|------|
| OS | macOS 15.7.7 |
| Shell | /bin/zsh |
| Docker | 28.5.2 (OrbStack) |
| Git | 2.53.0 |

---

## 3. 수행 체크리스트
- [ ] 터미널 기본 조작 및 폴더 구성
- [ ] 파일 권한 변경 실습
- [ ] Docker 설치/점검
- [ ] hello-world 실행
- [ ] ubuntu 컨테이너 진입 실습
- [ ] Dockerfile 커스텀 이미지 빌드
- [ ] 포트 매핑 접속 검증
- [ ] 바인드 마운트 반영 확인
- [ ] Docker 볼륨 영속성 검증
- [ ] Git 설정 + GitHub 연동

---

## 4. 수행 로그
(각 단계 진행하면서 여기에 추가 예정)

### 1단계: 터미널 기초

#### 기본 명령어
| 명령어 | 설명 | 실행 결과 요약 |
|--------|------|--------------|
| `pwd` | 현재 경로 출력 | `/Users/yerihan3763/Codyssey_M1` |
| `ls -al` | 상세 목록 출력 | README.md, .git 확인 |
| `mkdir practice` | 폴더 생성 | practice/ 폴더 생성 확인 |
| `touch hello.txt` | 빈 파일 생성 | 0 bytes 파일 생성 확인 |
| `cp` | 파일 복사 | hello_copy.txt 생성 확인 |
| `mv` | 이름 변경 | renamed.txt로 변경 확인 |
| `rm` | 파일 삭제 | 삭제 후 ls로 확인 |

#### 경로 실습
- 절대경로: `/Users/yerihan3763/Codyssey_M1`
- 상대경로: `cd ..` → `cd practice` → `cd ../..` 순서로 이동 확인

#### 권한 실습
| 명령어 | 변경 전 | 변경 후 |
|--------|---------|---------|
| `chmod 755 hello_copy.txt` | `-rw-r--r--` (644) | `-rwxr-xr-x` (755) |
| `chmod 644 hello_copy.txt` | `-rwxr-xr-x` (755) | `-rw-r--r--` (644) |
| `chmod 600 world.txt` | `-rw-r--r--` (644) | `-rw-------` (600) |

### 2단계: Docker 기초

#### 설치 확인
| 명령어 | 출력 요약 |
|--------|---------|
| `docker --version` | Docker version 28.5.2 |
| `docker info` | Server 섹션 정상 출력 확인 |

#### hello-world 실행
- `docker run hello-world` 실행
- Docker Hub에서 이미지 pull → 컨테이너 실행 → 메시지 출력 → 자동 종료 흐름 확인
- `docker ps -a` 로 Exited(0) 상태 확인

#### ubuntu 컨테이너 진입
- `docker run -it ubuntu /bin/bash` 로 컨테이너 진입
- 컨테이너 안에서 `cat /etc/os-release` 로 Ubuntu 환경 확인
- `exit` 후 컨테이너 Exited 상태 확인

#### attach vs exec 차이
| 항목 | attach | exec |
|------|--------|------|
| exit 후 컨테이너 | 종료됨 | 유지됨 |
| 탈출 단축키 | Ctrl+P,Q | exit |
| 용도 | 메인 프로세스 연결 | 새 프로세스 추가 |

#### 운영 명령어
- `docker ps / ps -a` : 실행 중 / 전체 컨테이너 확인
- `docker logs` : 컨테이너 로그 확인
- `docker stop → rm → rmi` : 정지 → 삭제 순서 확인

---

## 5. 트러블슈팅
(진행 중 겪은 문제 2건 이상 기록 예정)

---

## 6. 검증 방법 및 결과
(각 단계 완료 후 링크/스크린샷 추가 예정)