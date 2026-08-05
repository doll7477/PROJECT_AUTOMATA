# PROJECT AUTOMATA

> **"우리는 기능을 구현하지 않는다. 우리는 시스템을 설계한다."**

본 저장소는 단순한 PLC 명령어 학습을 넘어, 실제 산업 현장에서 신뢰받는 **Factory Automation (System Integration) Engineer**로 성장하기 위한 설계 일지 및 코드 보관소입니다. 

---

## 🛠️ 기술 스택 (Technical Stack)
* **PLC**: Mitsubishi MELSEC-Q / FX Series
* **Software**: GX Works3
* **Programming**: Ladder Logic, State Machine, Structural Text(ST)

---

## 📂 프로젝트 로드맵 (Project Roadmap)

| No. | Project Name | Description | Status | Link |
| :---: | :--- | :--- | :---: | :---: |
| **01** | [1축 실린더 및 안전 제어] | 편솔레노이드 제어 및 비상정지(E-Stop) 하드웨어 B접점 안전 구조 설계 | Done | [바로가기](./Project_01_Single_Cylinder/README.md) |
| **02** | [1축 실린더 자동 왕복] | 원점 센서 인터록 및 자동 복귀 시퀀스 설계 | Done | [바로가기](./Project_02_Pneumatic_Sequence/README.md) |
| **03** | [컨베이어 제어] | 준비 중 | Waiting | - |

---

## 📐 엔지니어링 설계 원칙
1. **State Machine 중심의 순차 제어**: 임의의 출력(Y)을 기억 장치로 쓰지 않으며, 모든 동적 제어는 상태 비트(M)의 명확한 상태 천이 조건에 의해 구동됩니다.
2. **안전 우선주의(Safety First)**: 비상정지 접점 단선 시 장비가 스스로 Safe-state로 복귀하도록 하드웨어와 소프트웨어 이중 안전 루프를 설계합니다.