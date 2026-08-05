# PROJECT AUTOMATA 🤖

> **"우리는 기능을 단순히 구현하지 않는다. 우리는 신뢰할 수 있는 시스템을 설계한다."**

본 저장소는 단순한 PLC 명령어 암기식 학습을 넘어, 실제 산업 현장에서 장비를 안정적으로 가동하고 예외 상황을 완벽하게 통제할 수 있는 **PLC 제어 및 FA(Factory Automation) 엔지니어**로 성장하기 위한 실무 설계 기록입니다.

---

## 🛠️ 핵심 학습 도구 및 제어 사양
* **PLC**: Mitsubishi MELSEC (Q / FX / L Series)
* **Software**: GX Works3
* **Programming**: Ladder Logic, State Machine, Interlock Design
* **Hardware Scope**: Sensors, Solenoid Valves, Pneumatic Cylinders

---

## 📂 프로젝트 로드맵 (Roadmap v2.0)

현업에 즉시 투입될 수 있는 실전 PLC 역량을 갖추기 위해, 작고 정교한 프로젝트를 단계별로 누적 완성해 나갑니다.

| No. | Project Name | 핵심 설계 기술 | Status | Link |
| :---: | :--- | :--- | :---: | :---: |
| **01** | **[자기유지 & 안전 정지]** | 전자기적 병렬 루프 제어, 비상정지(E-Stop) 하드웨어 B접점 안전 구조 설계 | Done | [바로가기](./Project_01_Single_Cylinder/README.md) |
| **02** | **[1축 공압 실린더 자동 왕복]** | 원점 센서 물리 인터록, 자기유지 상쇄를 이용한 자동 복귀 시퀀스 설계 | Done | [바로가기](./Project_02_Pneumatic_Sequence/README.md) |
| **03** | **[컨베이어 제어]** | 인버터 구동 제어, 모터 기동/정지 기하급수 인터록 및 타이머 제어 | Waiting | - |
| **04** | **[자동/수동 운전 모드]** | 3단 셀렉터 연동 상호 배제(Mutual Exclusion) 모드 전환 아키텍처 | Waiting | - |
| **05** | **[알람 시스템]** | 에러 래치(Error Latch) 및 작업자 수동 리셋(Reset) 안전 복귀 제어 | Waiting | - |
| **06** | **[기본 HMI 연동]** | HMI 모니터링 화면 구성, 터치 버튼 연동 수동 조작 및 상태 지시등 매핑 | Waiting | - |

---

## 📐 엔지니어링 설계 철학 (Engineering Philosophy)
1. **결정론적 상태 머신(State Machine) 지향**: 
   * 임의의 출력(Y)을 기억 장치로 오용하지 않으며, 모든 동적 제어는 상태 비트(M)의 명확한 상태 천이 조건에 의해 구동됩니다.
2. **방어적 안전 설계(Defensive Safety)**: 
   * "하드웨어와 센서는 반드시 고장 난다"는 전제하에, 케이블 단선 시 스스로 안전 상태(Safe-state)로 복귀하도록 하드웨어 B접점 설계 및 프로그램 인터록을 이중화합니다.
3. **히스토리 추적성 및 리팩토링**: 
   * 단순히 '동작만 하는 지저분한 코드'를 지양하며, 코드 리뷰와 시뮬레이션을 통해 유지보수가 용이하고 직관적인 코드로 지속 리팩토링합니다.