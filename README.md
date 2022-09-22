# GHC SiliconSuperstars: The star power of firmware in computing

<br>

# **Programming Exercises**

## **Exercise 1: Blink an LED using Wokwi Simulator for Raspberry Pi Pico**
Link to the exercise:
	https://wokwi.com/projects/343525071518696020
  
* Exercise 1.1: Use gpio_init that programs GPIO pin to LED_PIN

	```
	/*
    	Initialize the given GPIO by:
    	- Clear the output enable (i.e. set to input). 
    	- Clear the output value for the given GPIO
    	@params[in]: gpio   GPIO number
    	@return:     none
	*/
	void gpio_init(uint32_t gpio);
	```
* Exercise 1.2: Use gpio_set_dir that programs direction of LED_PIN to GPIO_OUT

	```
	/*
    	Set a single GPIO direction as input or output

    	@params[in]: gpio       GPIO pin number
    	@params[in]: direction  true for out, false for in
    	@return:     none
	*/
	void gpio_set_dir(uint32_t gpio, bool direction);
	```

* Exercise 1.3: Use gpio_put and drive LED to ON and OFF

	```
	/*
    	Drive a single GPIO high/low.
    	@param[in]: gpio    GPIO pin number
    	@param[in]: value   false: clear the pin,
                            true: set the pin
    	@return: none
	*/
	void gpio_put(uint32_t gpio, bool value);
	```

* Exercise 1.4: Use sleep_ms() to add some delay in between different LED states

	```
	/*
    	Wait for the given number of milliseconds before returning.
    	@param[in]: ms      the number of milliseconds to sleep

	*/
	void sleep_ms	(uint32_t ms);	
	```

## **Exercise 2: Develop an API for the GPIO library**

We will be doing this exercise in an online tool called Compiler Explorer. All the required libraries and skeleton code is setup for you at the link below.

Follow along here:
	https://godbolt.org/z/YvKM6Mxcs 
	
GOAL: Develop an API for gpio_set_dir(uint gpio, bool direction)

* You have a set of failing unit tests (gpio/test_gpio.cpp) that checks for the functionality of gpio_set_dir()
* Write the source code in gpio/gpio.cpp to get all unit tests to pass


Unit testing framework used for this exercise: [Catch2 version 3.0.0-preview](https://github.com/catchorg/Catch2)
<br>
You do not need to download this for this exercise as Compiler Explorer is setup to include the required libraries.

### API details: gpio_set_dir(uint gpio, bool direction)
	Set the direction for a single GPIO pin. The direction refers to configuring the GPIO pin as an input or an output pin.
	
	Parameters: gpio ==> pin number
		    direction ==> 1: the pin is programmed as an output pin 
 				  0: the pin is programmed as an input pin
				
This is achieved by writing to the GPIO output enable (gpio_oe) register.

### Register details: gpio_oe register
	GPIO output enable register
	32-bit register
		Bits[29:0] corresponds to the pin direction for GPIO pins [29:0] respectively
		Bit positions [31:30] are ignored by the hardware

* For example: 
gpio_oe = 0x5 [101 in binary] means:
	* GPIO_2 & GPIO_0 are programmed as output pins
	* GPIO_29..GPIO_3 & GPIO_1 are programmed as input pins



<br>

# Answer Keys
  * ***Wokwi Exercise*** 
  
    https://wokwi.com/projects/342301731204366931
  
  * ***Compiler Explorer Exercise***
  
    https://godbolt.org/z/1s9M4v19c 
    
<br>
