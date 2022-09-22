
# GPIOs
* GPIO stands for General Purpose I/O
* It is an interface that allows the processor to connect to external peripherals
* It can be programmed through software using the SIO interface
  * Check out **gpio_registers_t** struct in **gpio.h** for a list of registers we will be using in the programming exercise
  * Details on all the GPIO registers available in the Raspberry Pi SDK Datasheet Section 2.3.1.7. List of Registers
  * Datasheet: https://datasheets.raspberrypi.com/rp2040/rp2040-datasheet.pdf#tab-registerlist_sio


* APIs we will be working on (based on the Raspberry Pi Pico SDK):
  
  * Enable the pin: 									     ***gpio_init***
  * Change the direction of a given pin: 	***gpio_set_dir***
      * Updates the *gpio_oe* register to drive the direction for the given GPIO pin
  * Get the direction of a given pin: 		***gpio_get_dir***
      * Reads the *gpio_oe* register to get the direction for the given GPIO pin
  * Write to the gpio pin: 							 ***gpio_put***
      * Updates the *gpio_out* register to drive the output value for the given GPIO pin
  * Read from a gpio pin: 							  ***gpio_get***
      * Reads the *gpio_in* register to get the status of the given pin


# Additional Resources

Raspberry Pi Resources:
<br>
https://github.com/raspberrypi/pico-sdk
<br>
https://datasheets.raspberrypi.com/pico/raspberry-pi-pico-c-sdk.pdf
<br>
https://datasheets.raspberrypi.com/rp2040/rp2040-datasheet.pdf
<br>
https://github.com/raspberrypi/pico-examples


<br>
Unit Testing:
<br>
https://en.wikipedia.org/wiki/Test-driven_development
<br>
https://www.codecademy.com/article/tdd-red-green-refactor
<br>
https://en.wikipedia.org/wiki/Unit_testing
<br>

<br>
Memory Mapped I/O:
<br>
https://en.wikipedia.org/wiki/Memory-mapped_I/O
