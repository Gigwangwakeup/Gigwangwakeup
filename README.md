## 안녕하세요, 이기광입니다

RTL 프론트엔드 설계(디지털 회로 설계와 검증)를 하고 싶은 엔지니어입니다. 관심 분야는 차량용 반도체와 NPU입니다.

FPGA 연구원으로 2년 7개월 동안 전력설비 부분방전(PD) 진단 장비의 FPGA 로직을 설계하고 검증했습니다. 지금은 AI 시스템반도체 설계 교육과정에서 RISC-V CPU 설계, SystemVerilog 검증, STM32 임베디드 C와 FreeRTOS를 거쳐 MicroBlaze 기반 AXI SoC 설계를 공부하고 있습니다.

문제를 스스로 찾아 고치는 편입니다. "왜 꼭 이 값이어야 하지?"를 하나씩 물어 시스템 전체가 보이면, 거기서 개선점을 찾아 직접 구현합니다.

## 경력

**유호전기공업(주) 연구소** | FPGA 로직 설계와 검증 | 2023.11 ~ 2026.06

| 한 일 | 내용 |
|---|---|
| PD 검출 비교 간격 단축 | 실시간 비교 구조에 남아 있던 1MHz 고정 다운샘플링을 가변 구조로 바꿔, 비교 간격을 1us에서 200ns로 줄임 |
| 32채널 확장 (FPGA 2개 마스터 슬레이브) | 보드 사이 핀 12개 제약에서 12비트 원시값 대신 MCU 교정 후의 8비트 값을 넘기는 구조를 고안해 12핀 안에 클럭, 동기, 윈도우 펄스, 게이팅까지 배치 |
| FPGA 원격 업데이트 | 모듈을 분해해야 하던 JTAG 업데이트 대신 QSPI 멀티부트(STARTUPE2, ICAPE2, 골든 이미지 복귀)를 제안하고 FPGA 쪽을 구현. 랙 한 대 기준 업데이트 시간 약 20분에서 약 6분 |
| IEC 61850-9-2 이더넷 송신 | 레퍼런스에서 필요한 MAC 송신 모듈을 가져와 수정하고 Wireshark로 패킷 검증 |
| ADS5295 LVDS ADC 수신 | 외주 설계(ISERDESE2, IDELAYE2)를 분석하고 Vivado 시뮬레이션과 보드 동작으로 검증 |

## 프로젝트

| 프로젝트 | 내용 | 키워드 |
|---|---|---|
| [RV32I Multi-Cycle CPU + APB](https://github.com/Gigwangwakeup/HDL/tree/main/SystemVerilogHDL/RV32I_MultiCycle_APB) | 4인 팀. RV32I 멀티사이클 CPU와 APB 주변장치 연결. 명령어별 3, 4, 5사이클 FSM과 PREADY mux 담당 | SystemVerilog, Vivado, VCS, Verdi |
| [MicroBlaze AXI 커스텀 IP](https://github.com/Gigwangwakeup/Verilog-HDL/tree/main/basys3/AXI) | Basys3 MicroBlaze에 AXI4-Lite GPIO, UART IP를 붙이고 C 레지스터 구조체로 제어 | MicroBlaze, AXI4-Lite, Vivado IP Integrator, Vitis |
| [FreeRTOS RC카](https://github.com/Gigwangwakeup/STM32-Clang/tree/main/12.minicar) | 2인 팀. BLE 앱 조종과 초음파 자율 주행 RC카. 초음파 3개 순차 측정과 자율 주행 적용 담당 | STM32, FreeRTOS, Queue, Mutex, EXTI |
| [카드 권한 엘리베이터](https://github.com/Gigwangwakeup/STM32-Clang/tree/main/11.elevator_teamproject) | 2인 팀. 3층 카드 권한 엘리베이터와 Python 모델 검증 GUI | STM32, 2-process FSM, UART 프로토콜 |
| [STM32 스마트워치](https://github.com/Gigwangwakeup/STM32-Clang/tree/main/09.smartWatch) | 달력, 온습도, 거리, 스톱워치 모드 전환. 버튼 이벤트 큐 | STM32, 링 버퍼, 상태 머신 |
| [스텝모터 아날로그 시계](https://github.com/Gigwangwakeup/STM32-Clang/tree/main/06.%20analogClock_motor) | 스텝모터 3개로 만든 아날로그 시계, 스텝 오차 보정 | STM32, 스텝모터 |
| [UART 시계와 스톱워치](https://github.com/Gigwangwakeup/HDL/tree/main/VerilogHDL/UART_Stopwatch_Watch) | UART 명령으로 제어하는 시계와 스톱워치 | Verilog, UART FSM, Basys3 |
| [UVM 검증 실습](https://github.com/Gigwangwakeup/HDL/tree/main/SystemVerilogHDL/UVM_Verification) | Adder, Counter, RAM, FIFO UVM 테스트벤치 | UVM 기초, VCS |
| 출입 인원 카운팅 | 팀 프로젝트. 라즈베리파이 5 네 대로 교육장 출입 인원 집계, 추론 알고리즘 담당 | YOLO, NCNN, Raspberry Pi 5 |

전체 실습 기록은 아래 저장소에 있습니다.

- [HDL](https://github.com/Gigwangwakeup/HDL): Verilog RTL, SystemVerilog, UVM 검증, RISC-V CPU
- [Verilog-HDL](https://github.com/Gigwangwakeup/Verilog-HDL): MicroBlaze와 AXI 커스텀 IP
- [STM32-Clang](https://github.com/Gigwangwakeup/STM32-Clang): STM32 HAL 임베디드 C와 FreeRTOS

## 기술

| 구분 | 내용 |
|---|---|
| 언어 | Verilog, VHDL, SystemVerilog, C, Python |
| 도구 | Xilinx Vivado, Vitis, Synopsys VCS, Verdi, STM32CubeIDE |
| 보드 | Spartan-7, Artix-7 (Basys3), Zybo Z7, NUCLEO-F411RE, Raspberry Pi 5 |
| 프로세서, OS | RISC-V (RV32I), MicroBlaze, FreeRTOS |
| 인터페이스 | UART, I2C, APB, AXI4-Lite, LVDS, QSPI, Ethernet |

## 연락처

같이 이야기 나누고 싶으시면 메일 주세요.

- Email: lmop624@naver.com
<!-- 포트폴리오 사이트를 GitHub Pages에 올린 뒤 아래 줄의 주석을 풀 것 -->
<!-- - Portfolio: https://gigwangwakeup.github.io -->
