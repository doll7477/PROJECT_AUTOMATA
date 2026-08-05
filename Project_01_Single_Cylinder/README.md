# PROJECT AUTOMATA #1: Single-Axis Safety Control

## 1. 프로젝트 개요
* **목적**: 단축 공압 편솔레노이드 실린더 이송 제어 및 비상정지/타임아웃 안전 인터록 설계
* **핵심 설계**:
  * 비상정지(E-Stop)의 물리적 B접점 배선 및 프로그램 연동.
  * State Machine 기반의 제어로직 분리 (출력 Y0는 M 비트의 상태 조합으로 구동).
  * 3초 전진 타임아웃 발생 시 에러 래치(M100) 및 실린더 강제 안전 복귀(후진).

## 2. 입출력 정의 (I/O Map)
| 디바이스 | 구분 | 명칭 | 접점 방식 | 설명 |
| :--- | :--- | :--- | :--- | :--- |
| **X0** | Input | Start PB | A접점 | 시작 버튼 (START_PB) |
| **X1** | Input | E-Stop PB | B접점 | 비상정지 버튼 (누르면 OFF) |
| **X2** | Input | Forward Sensor | A접점 | 실린더 전진 완료 감지 오토스위치 |
| **X3** | Input | Backward Sensor | A접점 | 실린더 후진 완료 감지 오토스위치 |
| **X4** | Input | Reset PB | A접점 | 에러 리셋 버튼 (RESET_PB) |
| **Y0** | Output | Cylinder Sol | - | 실린더 전진 솔레노이드 밸브 (편솔) |

## 3. 상태 머신 다이어그램 (State Machine Diagram)
```mermaid
stateDiagram-v2
    [*] --> M0_IDLE
    M0_IDLE --> M1_FORWARD : X0(Start) AND X3(후진완료)
    M1_FORWARD --> M2_DWELL : X2(전진완료)
    M1_FORWARD --> M0_IDLE : X1(E-Stop) OR M100(오류)
    M2_DWELL --> M3_RETURN : T0(1초 타이머 완료)
    M2_DWELL --> M0_IDLE : X1(E-Stop)
    M3_RETURN --> M0_IDLE : X3(후진완료) OR X1(E-Stop)