/**
  @page Tệp readme của project thiết bị đầu cuối IoT
 
  @verbatim
  ******************************************************************************
  * @file    End_Node/readme.txt
  * @author  esystechs.vn
  * @brief   project thiết bị IoT đầu cuối
  ******************************************************************************
  *
  * Copyright (c) 2020 esystechs.vn. All rights reserved.
  *
  *
  ******************************************************************************
   @endverbatim

@par Mô tả Project

Project này dựa trên ví dụ EndNode của www.st.com
	Đọc giá trị cảm biến: nhiệt độ, độ ẩm, áp suất,...Rồi truyền các giá trị này qua
	giao tiếp Lora về Gateway.
  ******************************************************************************



@par Directory contents 


  - End_Node/LoRaWAN/inc/bsp.h               Header for bsp.c
  - End_Node/LoRaWAN/inc/Commissioning.h     End device commissioning parameters
  - End_Node/LoRaWAN/inc/debug.h             interface to debug functionally
  - End_Node/LoRaWAN/inc/hw.h                group all hw interface
  - End_Node/LoRaWAN/inc/hw_conf.h           file to manage Cube SW family used and debug switch
  - End_Node/LoRaWAN/inc/hw_gpio.h           Header for hw_gpio.c
  - End_Node/LoRaWAN/inc/hw_msp.h               Header for driver hw msp module
  - End_Node/LoRaWAN/inc/hw_rtc.h            Header for hw_rtc.c
  - End_Node/LoRaWAN/inc/hw_spi.h            Header for hw_spi.c
  - End_Node/LoRaWAN/inc/utilities_conf.h    configuration for utilities
  - End_Node/LoRaWAN/inc/vcom.h              interface to vcom.c
  - End_Node/LoRaWAN/inc/version.h           version file
  - End_Node/Core/inc/stm32lXxx_hal_conf.h       Library Configuration file
  - End_Node/Core/inc/stm32lXxx_hw_conf.h        Header for stm32lXxx_hw_conf.c
  - End_Node/Core/inc/stm32lXxx_it.h             Header for stm32lXxx_it.c
  
  - End_Node/LoRaWAN/src/bsp.c               manages the sensors on the application
  - End_Node/LoRaWAN/src/debug.c             debug driver
  - End_Node/LoRaWAN/src/hw_gpio.c           gpio driver
  - End_Node/LoRaWAN/src/hw_rtc.c            rtc driver
  - End_Node/LoRaWAN/src/hw_spi.c            spi driver
  - End_Node/LoRaWAN/src/main.c              Main program file
  - End_Node/LoRaWAN/src/vcom.c              virtual com port interface on Terminal
  - End_Node/Core/src/stm32lXxx_hal_msp.c        stm32lXxx specific hardware HAL code
  - End_Node/Core/src/stm32lXxx_hw.c             stm32lXxx specific hardware driver code
  - End_Node/Core/src/stm32lXxx_it.c             stm32lXxx Interrupt handlers
 
@par Phần cứng và phần mềm

  - Phần cứng: B-L072Z-LRWAN1 RevC
	Kết nối như sau:

             --------------------------  V    V  --------------------------
             |         Terminal       |  |    |  |      B-L072Z-LRWAN1    |
             |                        |  |    |  |                        |
             |						  |--|    |--|                        |-->COM PORT
             |                        |          |                        |
             --------------------------          --------------------------

@par Bắt đầu phát triển? 
  - Mở project bằng STM32CubeIDE
  - Viết code đọc dữ liệu từ cảm biến(tạo riêng *.h, *.c cho công việc của mình)
  - Thêm code đọc, và truyền dữ liệu đo được lên máy tính qua cổng COM ở tệp main.c sau
  	dòng   /* USER CODE BEGIN 1 */
  - Biên dịch, nạp chương trình xuống board.
  
  
@par Chạy chương trình? 
  - Kết nối board với máy tính qua giao tiếp COM: speed = 115200, 8b, 1 stopbit, no parity, no flow control
  - Các giá trị: nhiệt độ, độ ẩm, áp suất,...sẽ được đọc và truyền liên tục lên.
