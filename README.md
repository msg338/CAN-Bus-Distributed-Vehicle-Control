#CAN-Bus Distributed Vehicle Control
![KakaoTalk_20260330_212726982_02](https://github.com/user-attachments/assets/2e0e487b-e666-4c74-94c8-20c3daa609e7)

##Overview

STM32 기반으로 CAN 통신을 활용한 분산 제어 차량 시스템을 구현한 프로젝트입니다.
각 MCU는 역할을 분리하여 센서 데이터 처리와 모터 제어를 수행하며, CAN Bus를 통해 실시간으로 데이터를 송수신합니다.

##System Architecture
MCU 1 (Sensor Node)
→ 초음파 센서(HC-SR04)로 거리 측정
→ CAN 메시지로 데이터 송신
MCU 2 (Front Control)
→ CAN 데이터 수신
→ 전방 모터 제어
MCU 3 (Rear Control)
→ CAN 데이터 수신
→ 후방 모터 제어

##Hardware Components
STM32F401RE (3개)
MCP2515 CAN 모듈
HC-SR04 초음파 센서
TB6612FNG 모터 드라이버
DC 모터

##Data Flow
초음파 센서로 거리 측정
Sensor Node에서 CAN 메시지 생성 및 송신
Control Node에서 메시지 수신
거리 값에 따라 PWM 제어로 모터 속도 조절

##Implementation
CAN 통신: MCP2515 SPI 인터페이스 기반 구현
모터 제어: PWM을 이용한 속도 제어
시스템 구조: 3노드 분산 제어 구조

##Validation
CAN 메시지 송수신 정상 동작 확인
센서 입력에 따른 모터 제어 반응 검증
노드 간 실시간 통신 안정성 확인

##Key Point
중앙 제어가 아닌 분산 구조 설계 경험
CAN 기반 실시간 통신 시스템 구현
센서 → 통신 → 제어까지 전체 시스템 통합 경험
