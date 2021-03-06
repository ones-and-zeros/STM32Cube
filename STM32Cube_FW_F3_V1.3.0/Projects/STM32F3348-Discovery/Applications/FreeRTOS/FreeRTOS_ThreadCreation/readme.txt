/**
  @page FreeRTOS thread creation demonstration Readme file
 
  @verbatim
  ******************** (C) COPYRIGHT 2015 STMicroelectronics *******************
  * @file    FreeRTOS/FreeRTOS_ThreadCreation/readme.txt
  * @author  MCD Application Team
  * @version V1.2.0
  * @date    19-June-2015 
  * @brief   Description of the STM32F3xx CMSIS RTOS thread creation example.
  ******************************************************************************
  *
  * Licensed under MCD-ST Liberty SW License Agreement V2, (the "License");
  * You may not use this file except in compliance with the License.
  * You may obtain a copy of the License at:
  *
  *        http://www.st.com/software_license_agreement_liberty_v2
  *
  * Unless required by applicable law or agreed to in writing, software 
  * distributed under the License is distributed on an "AS IS" BASIS, 
  * WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
  * See the License for the specific language governing permissions and
  * limitations under the License.
  *
  ******************************************************************************
  @endverbatim

@par Description

This application shows how to implement a thread creation using CMSIS RTOS API. 

This example creates two threads with the same priority, which execute in 
a periodic cycle of 15 seconds. 

In the first 5 seconds, the thread 1 toggles LED5 each 200 ms and the 
thread 2 toggles LED6 each 500 ms.
In the following 5 seconds, the thread 1 suspends itself and the thread 2
continue toggling LED6.
In the last 5 seconds, the thread 2 resumes execution of thread 1 then 
suspends itself, the thread 1 toggles the LED5 each 400 ms.    

In case of error, LED5 is turned on and remains on.

@note Care must be taken when using HAL_Delay(), this function provides accurate delay (in milliseconds)
      based on variable incremented in SysTick ISR. This implies that if HAL_Delay() is called from
      a peripheral ISR process, then the SysTick interrupt must have higher priority (numerically lower)
      than the peripheral interrupt. Otherwise the caller ISR process will be blocked.
      To change the SysTick interrupt priority you have to use HAL_NVIC_SetPriority() function.
      
@note The application need to ensure that the SysTick time base is always set to 1 millisecond
      to have correct HAL operation.

@par Directory contents
    - FreeRTOS/FreeRTOS_ThreadCreation/Inc/main.h                main config file
    - FreeRTOS/FreeRTOS_ThreadCreation/Inc/stm32f3xx_hal_conf.h  HAL Configuration file
    - FreeRTOS/FreeRTOS_ThreadCreation/Inc/stm32f3xx_it.h        Header for stm32f3xx_it.c
    - FreeRTOS/FreeRTOS_ThreadCreation/Inc/FreeRTOSConfig.h      FreeRTOS Configuration file
    - FreeRTOS/FreeRTOS_ThreadCreation/Src/main.c                main program file
    - FreeRTOS/FreeRTOS_ThreadCreation/Src/stm32f3xx_it.c        STM32 Interrupt handlers

@par Hardware and Software environment

  - This example runs on STM32F3xx devices.
    
  - This example has been tested with a STMicroelectronics STM32F3348-Discovery RevB board embedding
    a STM32F334C8T6 device and can be easily tailored to any other supported device 
    and development board.

@par How to use it ?

In order to make the program work, you must do the following:
  1. Load the demonstration code in the Flash memory (see below)
  2. Please ensure that LEDs toggle like described above

  In order to load the demonstration code, you have do the following:
 - Open your preferred toolchain 
 - Rebuild all files and load your image into target memory
 - Run the example
 
 * <h3><center>&copy; COPYRIGHT STMicroelectronics</center></h3>
 */
