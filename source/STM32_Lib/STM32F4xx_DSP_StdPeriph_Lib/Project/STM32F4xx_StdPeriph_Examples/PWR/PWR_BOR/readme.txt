/**
  @page PWR_BOR PWR Brown Out Reset (BOR) example
  
  @verbatim
  ******************** (C) COPYRIGHT 2013 STMicroelectronics *******************
  * @file    PWR/PWR_BOR/readme.txt 
  * @author  MCD Application Team
  * @version V1.5.0
  * @date    06-March-2015
  * @brief   Description of the PWR Brown Out Reset (BOR) example.
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

@par Example Description

This example shows how to configure the programmable BOR thresholds using the 
FLASH option bytes.

By maintaining the Key push-button pressed at Reset, the new BOR level will be 
programmed. To modify the BOR threshold, select the voltage range using the 
appropriate line "#define BOR_LEVEL OB_BOR_XXXX" in main.c file.

LED1 is toggling to indicate that the reset is released and the system is in RUN
mode otherwise the BOR is maintaining the reset.


@par Directory contents

  - PWR/PWR_BOR/system_stm32f4xx.c   STM32F4xx system clock configuration file
  - PWR/PWR_BOR/stm32f4xx_conf.h     Library Configuration file
  - PWR/PWR_BOR/stm32f4xx_it.c       Interrupt handlers
  - PWR/PWR_BOR/stm32f4xx_it.h       Interrupt handlers header file
  - PWR/PWR_BOR/main.c               Main program
  - PWR/PWR_BOR/main.h               Main program header file


@par Hardware and Software environment

  - This example runs on STM32F405xx/407xx, STM32F415xx/417xx, STM32F427xx/437xx and 
    STM32F429xx/439xx devices.
    
  - This example has been tested with STMicroelectronics STM324xG-EVAL (STM32F40xx/
    STM32F41xx Devices), STM32437I-EVAL (STM32F427xx/STM32F437xx Devices) and 
    STM324x9I-EVAL RevB (STM32F429xx/STM32F439xx Devices) evaluation boards and 
    can be easily tailored to any other supported device and development board.

  - STM324xG-EVAL/STM32437I-EVAL Set-up
    - Use LED1 connected to PG.06 pin
    - Use the Key push-button connected to pin PG15 (EXTI Line15)

  - STM324x9I-EVAL RevB Set-up
    - Use LED1 connected to PG.06 pin
    - Use the KEY push-button connected to pin PC13 (EXTI Line13)


@par How to use it ?
                                     
In order to make the program work, you must do the following:
 - Copy all source files from this example folder to the template folder under
   Project\STM32F4xx_StdPeriph_Templates
 - Open your preferred toolchain 
 - Select the project workspace related to the used device 
   - If "STM32F40_41xxx" is selected as default project Add the following files in the project source list:
     - Utilities\STM32_EVAL\STM3240_41_G_EVAL\stm324xg_eval.c
     
   - If "STM32F427_437xx" is selected as default project Add the following files in the project source list:
     - Utilities\STM32_EVAL\STM324x7I_EVAL\stm324x7i_eval.c
     
   - If "STM32F429_439xx" is selected as default project Add the following files in the project source list:
     - Utilities\STM32_EVAL\STM324x9I_EVAL\stm324x9i_eval.c
            
 - Rebuild all files and load your image into target memory
 - Run the example

 * <h3><center>&copy; COPYRIGHT STMicroelectronics</center></h3>
 */