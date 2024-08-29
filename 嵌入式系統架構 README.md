# 嵌入式系統架構 README

## 系統概述

這個系統是一個基於FreeRTOS的嵌入式應用程序，具有多層架構設計。它包括應用層、服務層、硬件抽象層（HAL）、操作系統層和驅動層。

## 主要組件

1. **應用層 (Application)**
   - Main：主程序入口
   - SmApp：狀態機應用
   - InitApp：初始化應用
   - ClkApp：時鐘應用
   - PinIoApp：GPIO應用
   - RtosApp：RTOS配置應用
   - TaskApp：任務管理應用

2. **服務層 (Service)**
   - UDS：統一診斷服務
   - FuSa：功能安全
   - Security：安全服務

3. **硬件抽象層 (HAL)**
   - ClkHal：時鐘硬件抽象
   - PinIoHal：GPIO硬件抽象

4. **操作系統層 (OS)**
   - FreeRTOS：實時操作系統

5. **驅動層 (Drivers)**
   - ClkDrv：時鐘驅動
   - PinIoDrv：GPIO驅動

6. **硬件層 (Hardware)**
   - 實際的硬件設備

## 系統啟動流程

1. Main啟動並將狀態機切換到初始化狀態
2. 初始化時鐘系統
3. 初始化GPIO
4. 配置FreeRTOS任務
5. 切換到任務狀態
6. 開始周期性（每秒）的GPIO感測

## 主要功能

- 系統初始化
- 時鐘管理
- GPIO控制
- 任務調度
- 周期性GPIO感測

## 注意事項

- 本系統基於FreeRTOS運行
- 使用分層架構以提高模塊化和可維護性
- 包含功能安全和安全服務組件，適用於需要高可靠性的應用
