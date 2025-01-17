<!-- 프로필 사진 -->
![image](https://github.com/user-attachments/assets/1c580072-7caf-484f-a55c-da4899cc22c2)

<!-- 프로젝트 소개 -->
<div markdown="1">

![Slide 16_9 - 39](https://github.com/user-attachments/assets/c85e9558-0332-441e-87b0-65b115d12b4c)

</div>
<div markdown="1">

[![👉 앵무말 시연영상 바로가기](https://img.shields.io/badge/Parrotalk-Demo_video_바로가기-green?style=for-the-badge)](https://youtu.be/gmF1yILZO4E)

</div>
<div markdown="1">

**앵무말**은 전화 통화에 어려움을 겪는 것을 일컫는 **'콜포비아' 극복을 위한 AI 기반 통화 보조 서비스**입니다.<br>
이 서비스는 음성 통화를 텍스트로, 텍스트를 AI 음성 기술로 변환하여 사용자와 상대방 간의 의사소통을 더욱 편리하고 효과적으로 만들어 줍니다.<br>
특히, 통화에 불안감을 느끼거나, 목소리에 자신감이 없거나, 말실수를 걱정하는 사용자에게 적합한 솔루션입니다.

</div>

<!-- 팀원 및 역할 -->
## 팀원 및 역할

<div align="center">

| <img src="https://github.com/user-attachments/assets/dc4eb80e-edf4-41a2-abda-b1175dcf6206" width="120"/> | <img src="https://avatars.githubusercontent.com/u/33799946?v=4" width="120"/> | <img src="https://avatars.githubusercontent.com/u/104445068?v=4"  width="120"/> | <img src="https://github.com/user-attachments/assets/92ead9d9-1c00-4de8-8e31-b22ce2234935" width="120"/> | <img src="https://emojipedia-us.s3.amazonaws.com/source/skype/289/laptop_1f4bb.png" width="120"/> | <img src="https://avatars.githubusercontent.com/u/61226778?v=4" width="120"/> |
|------------------------------------------------------|--------------------------------------------------|--------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|
| [Roki.Kim(김경록)](https://github.com/KimGyeongLock)                                            | [Austin.Choi(최윤서)](https://github.com/Austin-Choi)                                           | [Cellina.Jeong(정은채)](https://github.com/Goldchae)                                           | [Jay.Hwang(황지원)](https://github.com/JiwonHwang84)                                                                                                                                               | [Sofia.Park(박수현)](https://github.com/suugit)                                                                                                                                               | [Jimmy.Kim(김승엽)](https://github.com/yeopyeop-82)                                           |
| Full-Stack                                              | Full-Stack                                       | AI                                       | AI                                                                                                                                           | Cloud                                                                                                                                              | Cloud                                       |
</div>

<!-- 목차 -->
## 목차
* [📞 주요 기능](#function)
* [⚒️ 기술스택](#stack)
* [🔎 기술 사용 근거](#detail)
* [💸 서버 아키텍처](#architecture)
* [🗂️ ERD](#erd)
* [📈 성능 개선 & 리팩토링](#improve)
* [🖥️ 테스트 & 모니터링](#test)

<!-- 기능 소개 -->
<a id="function"></a>
## 📞 주요 기능

### 1. 1대1 통화
- **Voice to Voice** : Socket.io, WebRTC, 자체 구축 STUN과 TURN 서버를 활용해 사용자간 1대1 음성통화가 가능합니다.
- **Voice to Chat** : Voice to Voice에서 확장하여 Chat 유저는 WebRTC의 DataChannel를 사용하여 연결합니다.<br>
  또한, Chat 사용자는 TTS를 사용해 Voice 사용자에게 자신이 입력한 Chat 메시지를 음성으로 출력하여 전달합니다.<br>
  Voice 사용자의 말은 Amazon Transcribe를 활용한 스트리밍 STT로 실시간으로 Chat 사용자에게 Chat 메시지로 출력됩니다.
- **Chat to Chat** : WebRTC의 DataChannel를 활용하여 일반 1대1 채팅으로 연결합니다.

### 2. 할 말 추천
- Voice to Chat 시나리오에서 Chat 사용자는 대화 맥락에 맞는 예상되는 추천 문구를 총 3가지를 선택 가능합니다.
- 추천은 채팅 입력창 위 3개의 버튼으로 출력되며, 버튼을 클릭해 바로 입력할 수 있습니다.
- 추천은 추천이 필요한 상황인지 AI가 판단한 상황에서만 출력됩니다.

### 3. 통화 Todo 정리
- 통화 종료 후, 통화 내용을 요약한 리스트가 출력되고 그 중 원하는 항목만 골라 저장하고<br>
  마이페이지의 통화 목록에서 상대방이 누구였는지, 통화 일시는 언제였는지와 함께 확인할 수 있습니다.

</div>

<!-- 기술 스택 -->
<a id="stack"></a>
## ⚒️ 기술스택
<details>
<summary> 본문 확인 (👈 Click) </summary>
<div markdown="1">

### 📞 텍스트 통화
<img src="https://img.shields.io/badge/WebRTC-333333?style=for-the-badge&logo=WebRTC&logoColor=white">
<img src="https://img.shields.io/badge/socket.io-010101?style=for-the-badge&logo=socket.io&logoColor=white">
<img src="https://img.shields.io/badge/spring-6DB33F?style=for-the-badge&logo=spring&logoColor=white">
<img src="https://img.shields.io/badge/react.js-61DAFB?style=for-the-badge&logo=react&logoColor=black">
<img src="https://img.shields.io/badge/express.js-000000?style=for-the-badge&logo=express&logoColor=white">

<br>

### 🎤 STT / TTS
<img src="https://img.shields.io/badge/Amazon Transcribe-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white">
<img src="https://img.shields.io/badge/Amazon Polly-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white">

<br>

### 🤖 AI
<img src="https://img.shields.io/badge/OpenAI-412991?style=for-the-badge&logo=openai&logoColor=white">
<img src="https://img.shields.io/badge/NVIDIA CUDA-76B900?style=for-the-badge&logo=nvidia&logoColor=white">
<img src="https://img.shields.io/badge/LangChain-333333?style=for-the-badge&logo=langchain&logoColor=white">
<img src="https://img.shields.io/badge/Google Cloud Speech to Text-4285F4?style=for-the-badge&logo=googlecloud&logoColor=white">
<img src="https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white">

<br>

### 🔄 CI/CD
<img src="https://img.shields.io/badge/Jenkins-D24939?style=for-the-badge&logo=jenkins&logoColor=white">
<img src="https://img.shields.io/badge/Argo CD-EF7B4D?style=for-the-badge&logo=argo&logoColor=white">

<br>

### 🔍 모니터링
<img src="https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white">
<img src="https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white">

<br>

### ⚙️ 인프라
<img src="https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white">
<img src="https://img.shields.io/badge/Terraform-623CE4?style=for-the-badge&logo=terraform&logoColor=white">
<img src="https://img.shields.io/badge/Ansible-EE0000?style=for-the-badge&logo=ansible&logoColor=white">
<img src="https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white">
<img src="https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white">
<img src="https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white">

</div>
</details>

<!-- 기술 사용 근거 -->
<a id="detail"></a>
## 🔎 기술 사용 근거
<details>
<summary> 본문 확인 (👈 Click) </summary>
<div markdown="1">

### 1. 사용자간 웹 상 통화 구현 방법
- **HLS** : 미디어 스트리밍에 있어서 점유율이 가장 높습니다.<br>
  But, latency가 3초로 실시간 전송이 필요한 우리 서비스에는 미흡하다고 판단했습니다.
- **Twillio** : 웹상 통화 API로 간단한 사용 방법과 실시간 전송, 일반 스마트폰과 웹 사용자와의 통화를 지원했습니다.<br>
  But, 사용자마다 임시 번호를 구입해야하거나 미리 대량의 번호를 사 두고 돌아가며 지급해야하는 운영의 복잡성이 올라갑니다.<br>
- **WebRTC** : latency가 매우 낮고 실시간 전송을 보장하며 데이터 전송에서 서버를 거치지 않아 네트워크 사용량이 적습니다.<br>
  But, 학습곡선이 높을 수 있고 NAT 환경에서의 연결을 위해 TURN 서버 구축이 필수이며 서버 비용이 높을 수 있습니다.<br>
  
-> 서비스의 기술 요구사항에 따라 **WebRTC** 가 가장 적합하여 채택했습니다.

---

### 2. WebRTC 토폴로지 선택
- **MCU** : 중앙에 미디어 서버를 두고 통신하는 방식으로 미디어 서버 구현 난이도와 클라우드 비용 문제가 상충하여 채택하지 않았습니다.
- **Mesh** : 클라이언트 간 미디어를 직접 전송하는 방식으로 1대1일때 품질이 우수하고 대기시간이 짧아 채택했습니다.
- **SFU** : 대규모 다자간 통신으로 확장성이 있고, SFU 역시 미디어 서버를 사용하지만 <br>
  MCU와 달리 서버에서 인코딩/디코딩을 하지 않아 추후 지속적인 서비스를 위해 고려하고 있습니다.

-> 1대1 통화를 우선으로 하니 **Mesh**로 구성했습니다.

---

### 3. STT 기술 선택
- **Google STT** : 실시간 스트리밍을 제공하고 다양한 언어를 지원하지만 화자 분리 기능이 존재하지 않았습니다.
- **OpenAI Whisper** : 무료지만 실시간 스트리밍을 제공하지 않아 Batch 처리를 해야 하므로 지연도가 높아집니다.
- **Amazon Transcribe** : 실시간 스트리밍을 제공하고 추후 다자간 통신을 위한 화자 분리가 가능합니다.<br>
  공식 문서가 잘 되어 있었고, 이미 사용하고 있는 Amazon의 다른 서비스와 함께 관리 및 운영이 수월했습니다.

-> Speech-to-Text 기술은 **Amazon Transcribe**를 활용했습니다.

</div>
</details>

<!-- 서버 아키텍처 -->
<a id="architecture"></a>
## 💸 서버 아키텍처
<details>
<summary> 본문 확인 (👈 Click) </summary>
<div markdown="1">

![Slide 16_9 - 46](https://github.com/user-attachments/assets/219ee32d-c574-4c3f-adcb-3c12fae6bb8c)

## Infrastructure & Application Management

### 1. Parrotalk-CD Repository
- **Terraform**: AWS 인프라 구성 (VPC, EKS, RDS)
- **Ansible**: Kubernetes 클러스터, ArgoCD 설치
- **Kubespray**: K8s 클러스터 자동 설치

### 2. Parrotalk-Manifests Repository
- **매니페스트 관리**: K8s 리소스 정의 매니페스트 관리
- **자동 배포**: ArgoCD를 통한 자동 배포
- **설정 관리**: 마이크로서비스 및 인프라 설정 포함

### 배포 프로세스
1. CD Repository로 인프라 구성 및 ArgoCD 설치
2. ArgoCD가 Manifests Repository와 연동되어 전체 시스템 자동 구성
3. 이후 모든 변경사항은 Git을 통해 자동 배포

</div>
</details>

<!-- ERD -->
<a id="erd"></a>
## 🗂️ ERD
<details>
<summary> 본문 확인 (👈 Click) </summary>
<div markdown="1">

<img width="894" alt="image" src="https://github.com/user-attachments/assets/d5927ff8-d47c-4a4d-92d7-d885766a1b51" />

[앵무말ERD](https://www.erdcloud.com/d/hwDMXcG93hZDtQ57J)


### **1. Users 테이블**
- **역할:** 사용자 정보를 저장합니다.
- **주요 필드:**
  - `user_id`: 사용자 고유 식별자 (Primary Key)
  - `nickname`: 사용자의 닉네임
  - `email`: 사용자 이메일
  - `provider`: 소셜 로그인 방식 (e.g., KAKAO, GOOGLE)
  - `profile_image`: 사용자 프로필 이미지
  - `created_at`, `updated_at`: 데이터 생성 및 수정 시간

---

### **2. Talks 테이블**
- **역할:** 대화 관련 정보를 저장합니다.
- **주요 필드:**
  - `talk_id`: 대화 고유 식별자 (Primary Key)
  - `status`: 대화 상태 (`ACTIVE`, `INACTIVE`, `CLOSED`)
  - `created_at`: 대화 생성 시간
  - `closed_at`: 대화 종료 시간
  - `room_name`: 대화방 이름
  - `sender_id`: 발신자 ID
  - `receiver_id`: 수신자 ID

---

### **3. Todos 테이블**
- **역할:** 대화 방에서 생성된 투두(To-Do) 항목을 저장합니다.
- **주요 필드:**
  - `todo_id`: 투두 고유 식별자 (Primary Key)
  - `title`: 투두 제목

---

### **4. RoomUser_Detail 테이블**
- **역할:** 마이페이지에서 유저별 투두(To-Do)를 관리하며, 사용자, 대화, 투두 간의 관계를 연결합니다.
- **주요 필드:**
  - `user_id`: 사용자 ID (Foreign Key)
  - `todo_id`: 투두 ID (Foreign Key)
  - `talk_id`: 대화 ID (Foreign Key)
  - `todo_status`: 투두의 상태를 나타내는 필드
- **관계:**
  - Users, Todos, Talks 테이블과 모두 연관. RoomUser_Detail은 다대다 관계를 구현하는 연결 테이블 역할을 합니다.

---

### **테이블 간 관계 요약**
- **Users ↔ RoomUser_Detail:** 사용자와 마이페이지 상세 정보는 1:N 관계입니다.
- **Talks ↔ RoomUser_Detail:** 대화와 마이페이지 상세 정보는 1:N 관계입니다.
- **Todos ↔ RoomUser_Detail:** 투두와 마이페이지 상세 정보는 1:N 관계입니다.

---

### 유의할 점
**RoomUser_Detail 테이블의 데이터 증가 문제**<br>
RoomUser_Detail 테이블은 대화가 시작될 때 유저 수(2명)와 투두의 갯수만큼 데이터가 생성됩니다.<br>
예를 들어, 대화 하나에 두 명의 유저와 10개의 투두 항목이 있다면, 이 대화로 인해 RoomUser_Detail 테이블에는 2 x 10 = 20개의 데이터가 추가됩니다.<br>
여러 대화와 투두가 반복적으로 추가되면 데이터가 기하급수적으로 증가하여 성능 및 저장 공간에 문제가 발생할 수 있습니다.<br>

**최적화 전략 구상**
* **인덱싱 추가** → 빠른 쿼리 개선.
* **캐싱 도입** → 자주 조회되는 데이터를 캐시에 저장.
* **데이터 수명 관리** → 오래된 데이터를 주기적으로 삭제.
* **비즈니스 로직 개선** → 중복 데이터 최소화.

</div>
</details>

<!-- 성능 개선 & 리팩토링 -->
<a id="improve"></a>
## 📈 성능 개선 & 리팩토링
<details>
<summary> 본문 확인 (👈 Click) </summary>
<div markdown="1">

성능 개선 & 리팩토링 내용입니다.

</div>
</details>

<!-- 테스트 & 모니터링 -->
<a id="test"></a>
## 🖥️ 테스트 & 모니터링
<details>
<summary> 본문 확인 (👈 Click) </summary>
<div markdown="1">

테스트 & 모니터링 내용입니다.

</div>
</details>
