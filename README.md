# L476-USART1-PCText
STM32 UART Hello World Project Overview

This project demonstrates basic UART communication using the STM32 Nucleo-L476RG development board.
The program sends the message:

Hello World! Nucleo-L476RG through USART2 at 9600 baud using the STM32 HAL library.

The message can be viewed on a serial terminal application such as: PuTTY


USART2 is connected to the onboard ST-LINK Virtual COM Port.

STM32 Pin	Function
PA2	USART2_TX
PA3	USART2_RX

No external USB-to-UART adapter is required.

Software Requirements
IDE
STM32CubeIDE
Terminal Program



Equivalent terminal settings: 9600 8N1


The project uses:

HAL_UART_Transmit()

to send strings through USART2.

Important Code
UART Send Function
void UART_SEND(UART_HandleTypeDef *huart, char buffer[]){
    HAL_UART_Transmit(huart,
                      (uint8_t*) buffer,
                      strlen(buffer),
                      HAL_MAX_DELAY);
}
Send Hello World
char Text2Display[]="Hello World! Nucleo-L476RG \n\r";

HAL_UART_Transmit(&huart2,
                  (uint8_t*) Text2Display,
                  strlen(Text2Display),
                  HAL_MAX_DELAY);

Example:

COM3
9600
Find COM Port

Windows:

Device Manager
→ Ports (COM & LPT)

Example:

STMicroelectronics STLink Virtual COM Port (COM3)
Expected Output

After opening the serial terminal: Hello World! Nucleo-L476RG

# Future Improvements

Possible extensions:

Receive UART data from PC
Echo received characters
PWM control through UART commands
Temperature monitoring
ADC data transmission
Interrupt-based UART communication
DMA UART communication
