# FreeRTOS_MSP432_LEDs_example
<b><i>Blink 2 built-in LEDS, with different frequency, on an MSP432P401R launchpad using FreeRTOS</i></b>


<br>FreeRTOS offers a demo for the MSP432 launchpad, blinkind one LED every 400 milliseconds.
<br>
<br>
<br>This demo expands the initial code, adding new threads for a second blinking LED.
<br>The second LED blinks in a different frequency than the first LED, and in various colours
(using the built-in RGB functionality of the launchapd)
<br>
<br>
<br>
The files that were modified are:
<br><b>-main.c</b>
<br><b>-main_blinky.c</b>
<br>
<br>
<br>In main.c file, new GPIOs that correspond to the LED were added
<br><i>MAP_GPIO_setOutputLowOnPin( GPIO_PORT_P2, GPIO_PIN0 );
<br>MAP_GPIO_setAsOutputPin( GPIO_PORT_P2, GPIO_PIN0 );
<br>MAP_GPIO_setOutputLowOnPin( GPIO_PORT_P2, GPIO_PIN1 );
<br>MAP_GPIO_setAsOutputPin( GPIO_PORT_P2, GPIO_PIN1 );
<br>MAP_GPIO_setOutputLowOnPin( GPIO_PORT_P2, GPIO_PIN2 );
<br>MAP_GPIO_setAsOutputPin( GPIO_PORT_P2, GPIO_PIN2 );</i>
<br>
<br>
<br>In main_blinky.c, new threads were added using the <i>xTaskCreate</i> function. A new frequency for the second LED
was used (<i>#define secondQUEUE_SEND_FREQUENCY_MS         ( pdMS_TO_TICKS( 500UL ) )</i>), and 2 new functions that are 
used by the threads were created.
<br>
<br>
<br>
<b>This is the launchpad that was used:</b>
<br>![alt text](https://cdn.lankatronics.com/pub/media/catalog/product/cache/c0bb400db441ec67b37045c5a66e35a8/m/s/msp_1_1_.jpg)
<br>
<br>You can buy it at: http://www.ti.com/tool/MSP-EXP432P401R

