a simple project to learn interrupt driven Reception. 

* UART2 interrupt enabled in NVIC settings. 
* Call-back function updates a flag "rx_byte_NE". because initially echoed from the call-back function itself. but because it was inside the ISR, I noticed UART Rx drops. Hence  flag-based deferred processing tried and succeeded. 
* in the main function, if this flag is set, rx_byte will be echoed. Then HAL_UART_Receive_IT will be re-armed. 

