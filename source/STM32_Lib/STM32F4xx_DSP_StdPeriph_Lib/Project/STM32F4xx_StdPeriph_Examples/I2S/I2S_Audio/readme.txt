/**
  @page I2S_Audio  I2S Audio features example
  
  @verbatim
  ******************** (C) COPYRIGHT 2013 STMicroelectronics *******************
  * @file    I2S/I2S_Audio/readme.txt 
  * @author  MCD Application Team
  * @version V1.5.0
  * @date    06-March-2015
  * @brief   Description of the I2S Audio features example.
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

This example shows how to implement I2S audio features. It allows to play an 
audio file through the I2S peripheral and using the external codec implemented 
on the STM324xG_EVAL/STM324x7I_EVAL board.

In this example the I2S input clock, provided by a dedicated PLL (PLLI2S),  is
configured to have an audio sampling frequency at 48 KHz with Master clock enabled.

This example uses an audio codec driver which consists of three independent layers:
 - Codec Hardware layer: which controls and communicates with the audio codec 
   (CS43L22) implemented on the evaluation board.
 - MAL (Media Access Layer): which controls and interfaces with storage media 
   storing or providing the audio file/stream.
 - The high layer: which implements overall control and interfacing API allowing
   to perform basic audio operations (Init, Play, Pause, Resume, Stop, Volume 
   control and audio file pointer management)
  
In this example the audio file is stored in the internal flash memory (Stereo, 
16-bit, 48 KHz). The analog output device is automatically detected (Speaker or 
Headphone) when the Headphone is plugged/unplugged in/from the audio jack of the 
evaluation board. The example also manages information display and control interface
through push-buttons: 
 - When the application is Playing audio file:
     + KEY   : Pause
     + TAMPER: Volume UP
     + WAKEUP: Volume DOWN
 - When the application is Paused:
     + KEY   : Play
     + TAMPER: Switch output target to Headphone
     + WAKEUP: Switch output target to Speaker

This example plays the audio file stored in internal flash memory and replay it
when it reach end of file. But it can be tailored to used different media storage
devices; SDCard (through SDIO), external Memory (through FSMC) ...) or to play 
in streaming mode (ie. from USB port in device or host mode). In this case, Circular
DMA mode should be preferred (by enabling the define AUDIO_MAL_MODE_CIRCULAR in
stm324xg_eval_audio_codec.h/stm324x7i_eval_audio_codec.h files).  

List of Known Limitations and more detailed user notes are provided in file 
stm324xg_eval_audio_codec.c   (under Utilities\STM32_EVAL\STM3240_41_G_EVAL)
stm324x7i_eval_audio_codec.c   (under Utilities\STM32_EVAL\STM324x7I_EVAL)

The provided sample audio file (stored in internal flash memory) is extracted from:
 - Title: artofgardens-instr 
 - Artist/Composer: Dan O'Connor
 - Creative Commons license: Attribution 3.0 United States
   Please read the license following this link:
   http://creativecommons.org/licenses/by/3.0/us/


@par Directory contents 
  
  - I2S/I2S_Audio/system_stm32f4xx.c   STM32F4xx system clock configuration file
  - I2S/I2S_Audio/stm32f4xx_conf.h     Library Configuration file
  - I2S/I2S_Audio/stm32f4xx_it.c       Interrupt handlers
  - I2S/I2S_Audio/stm32f4xx_it.h       Interrupt handlers header file
  - I2S/I2S_Audio/main.c               Main program
  - I2S/I2S_Audio/main.h               Main program header file
  - I2S/I2S_Audio/audio_sample.c       Audio Sample file (in tab format)

      
@par Hardware and Software environment 

  - This example runs on STM32F405xx/407xx, STM32F415xx/417xx and STM32F427xx/437xx devices.
    
  - This example has been tested with STMicroelectronics STM324xG-EVAL (STM32F40xx/
    STM32F41xx Devices) and STM32437I-EVAL (STM32F427xx/STM32F437xx Devices) 
    evaluation boards and can be easily tailored to any other supported device 
    and development board.

  - STM324xG-EVAL/STM32437I-EVAL Set-up
    - Make sure the jumper JP16 is in position 2-3
    

@par How to use it ? 

In order to make the program work, you must do the following:
 - Copy all source files from this example folder to the template folder under
   Project\STM32F4xx_StdPeriph_Templates
 - Open your preferred toolchain
 - Select the project workspace related to the used device 
   - If "STM32F40_41xxx" is selected as default project Add the following files in the project source list:
     - Utilities\STM32_EVAL\STM3240_41_G_EVAL\stm324xg_eval.c
     - Utilities\STM32_EVAL\STM3240_41_G_EVAL\stm324xg_eval_lcd.c
     - Utilities\STM32_EVAL\STM3240_41_G_EVAL\stm324xg_eval_ioe.c      
     - Utilities\STM32_EVAL\STM3240_41_G_EVAL\stm324xg_eval_audio_codec.c
     - audio_sample.c 
      
   - If "STM32F427_437xx" is selected as default project Add the following files in the project source list:
     - Utilities\STM32_EVAL\STM324x7I_EVAL\stm324x7i_eval.c
     - Utilities\STM32_EVAL\STM324x7I_EVAL\stm324x7i_eval_lcd.c
     - Utilities\STM32_EVAL\STM324x7I_EVAL\stm324x7i_eval_ioe.c      
     - Utilities\STM32_EVAL\STM324x7I_EVAL\stm324x7i_eval_audio_codec.c
     - audio_sample.c 
             
 - Rebuild all files and load your image into target memory
 - Run the example
   
 * <h3><center>&copy; COPYRIGHT STMicroelectronics</center></h3>
 */
