# PROJECT AUTOMATA 🤖

> **"우리는 기능을 단순히 구현하는 것이 아니라, 신뢰할 수 있는 시스템을 설계한다."**

---

## 📖 프로젝트 소개

**PROJECT AUTOMATA**는 Mitsubishi PLC와 GX Works3를 기반으로
**PLC / FA 엔지니어 취업을 목표로 진행하는 프로젝트 기반 학습 및 포트폴리오 저장소**입니다.

PLC Ladder Logic을 직접 작성하고 시뮬레이션 및 디버깅을 진행하면서
자동화 설비에 필요한 제어 로직과 문제 해결 능력을 단계적으로 익혀 나갑니다.

---

## 🎯 학습 목표

* PLC 프로그래밍 기초 및 실무 역량 습득
* Ladder Logic을 이용한 순차 제어
* State Machine 기반 제어 로직 설계
* 센서 및 액추에이터 제어
* Interlock 및 안전 제어
* Timer / Counter 활용
* HMI 및 주변 장치 연동
* Servo / Robot / Vision 등 FA 기술 확장
* 프로젝트 기반 포트폴리오 구축

---

## 🛠 개발 환경

| 구분      | 내용                                                         |
| ------- | ---------------------------------------------------------- |
| PLC     | Mitsubishi MELSEC iQ-F (FX5 Series)                        |
| CPU     | FX5U                                                       |
| 프로그램    | GX Works3                                                  |
| 프로그래밍   | Ladder Logic                                               |
| 제어 방식   | Sequence Control, State Machine                            |
| 주요 하드웨어 | Digital I/O, Sensors, Solenoid Valves, Pneumatic Cylinders |

---

# 📂 프로젝트 로드맵

각 프로젝트는 하나의 독립적인 제어 과제로 구성하며, 이전 프로젝트에서 학습한 내용을 다음 프로젝트에 단계적으로 확장합니다.

|  번호 | 프로젝트                     | 주요 학습 내용                     |    상태   |                            바로가기                           |
| :-: | ------------------------ | ---------------------------- | :-----: | :-------------------------------------------------------: |
|  01 | **단축 실린더 안전 제어**         | 자기유지, 비상정지, 타이머, 상태 제어       |   ✅ 완료  |    [Project 01](./Project_01_Single_Cylinder/README.md)   |
|  02 | **다축 공압 순차 제어**          | 순차 제어, State Machine, 센서 인터록 | 🚧 진행 중 | [Project 02](./Project_02_Multi_Axis_Pneumatic/README.md) |
|  03 | **컨베이어 제어**              | 모터 제어, 타이머, 인터록              |  📅 예정  |       [Project 03](./Project_03_Conveyor/README.md)       |
|  04 | **운전 모드 제어**             | 자동 / 수동 / 원점 모드              |  📅 예정  |    [Project 04](./Project_04_Operation_Mode/README.md)    |
|  05 | **알람 및 복귀 제어**           | Alarm Latch, Reset, 복귀 시퀀스   |  📅 예정  |    [Project 05](./Project_05_Alarm_Recovery/README.md)    |
|  06 | **기본 HMI 연동**            | GOT 모니터링, 수동 조작, 상태 표시       |  📅 예정  |       [Project 06](./Project_06_Basic_HMI/README.md)      |
|  07 | **Servo 제어**             | 위치 제어, Servo 인터페이스           |  📅 예정  |   [Project 07](./Project_07_Servo_Positioning/README.md)  |
|  08 | **Robot 연동**             | PLC ↔ Robot Handshake        |  📅 예정  |    [Project 08](./Project_08_Robot_Handshake/README.md)   |
|  09 | **Vision 연동**            | PLC ↔ Vision 통신 및 결과 처리      |  📅 예정  |   [Project 09](./Project_09_Vision_Interface/README.md)   |
|  10 | **Mini Automation Line** | PLC 기반 통합 자동화 시스템            |  📅 예정  | [Project 10](./Project_10_Mini_Automation_Line/README.md) |

> ※ 프로젝트의 세부 내용과 순서는 학습 과정에서 필요에 따라 조정될 수 있습니다.

---

# 🏗 프로젝트 진행 방식

각 프로젝트는 기본적으로 다음 순서로 진행합니다.

1. **요구사항 분석**
2. **입출력(I/O) 정의**
3. **시퀀스 및 상태(State) 설계**
4. **Ladder Logic 작성**
5. **시뮬레이션**
6. **디버깅**
7. **문서화**
8. **리팩토링**

프로젝트의 규모와 목적에 따라 일부 단계는 단순화하거나 추가할 수 있습니다.

---

# 📐 설계 원칙

### 1. 상태를 먼저 설계한다

설비가 어떤 상태에 있고, 어떤 조건에서 다음 상태로 넘어가는지를 먼저 정의한 후 Ladder Logic을 작성합니다.

동작 상태는 내부 릴레이(M)를 중심으로 관리하고, 출력(Y)은 상태와 조건의 결과로 제어합니다.

### 2. 안전을 우선한다

비상정지, 센서 상태, 인터록 및 오류 상황을 고려하여 예상하지 못한 동작을 방지하는 제어 구조를 우선합니다.

### 3. 이해하기 쉬운 프로그램을 작성한다

복잡한 논리보다 다른 엔지니어가 보고 동작을 이해하고 수정할 수 있는 명확한 프로그램을 우선합니다.

### 4. 작성보다 검증을 중요하게 생각한다

Ladder Logic 작성으로 끝내지 않고 시뮬레이션과 디버깅을 통해 정상 동작과 예외 상황을 확인합니다.

### 5. 작은 시스템부터 단계적으로 확장한다

작은 PLC 제어 과제부터 시작하여

**기초 PLC → 공압 순차 제어 → 모터/컨베이어 → 운전 모드 → 알람/복귀 → HMI → Servo → Robot → Vision**

순으로 필요한 기술 영역을 단계적으로 확장합니다.
---

# 📁 프로젝트 구조

각 프로젝트는 독립적인 폴더로 관리합니다.

```text
PROJECT AUTOMATA/
│
├─ Project_01_Single_Cylinder/
│  └─ README.md
│
├─ Project_02_Multi_Axis_Pneumatic/
│  └─ README.md
│
├─ Project_03_Conveyor/
│  └─ README.md
│
├─ Project_04_Operation_Mode/
│  └─ README.md
│
├─ ...
│
└─ README.md
```

각 프로젝트에는 가능한 범위에서 다음 자료를 포함합니다.

* 프로젝트 설명
* I/O Map
* Ladder Program
* 시뮬레이션 및 테스트 결과
* 트러블슈팅 기록

---

# 🚀 최종 목표

PROJECT AUTOMATA의 가장 큰 목표는 **PLC / FA 엔지니어 취업**입니다.

PLC 프로그래밍을 중심으로 공압 제어, 순차 제어, 인터록, 트러블슈팅 등의
기초 실무 역량을 먼저 갖추고, 이후 HMI, Servo, Robot, Vision 등의 기술을
단계적으로 학습합니다.

프로젝트를 직접 설계하고 구현하면서 신입 PLC / FA 엔지니어에게 필요한
실무 역량을 갖추고, 프로젝트 결과물을 포트폴리오로 정리하여
**PLC 및 FA 관련 직무에 지원할 수 있는 실력을 갖추는 것**을 목표로 합니다.