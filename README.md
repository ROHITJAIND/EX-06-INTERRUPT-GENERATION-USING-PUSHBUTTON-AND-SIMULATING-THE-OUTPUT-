# EX-06 INTERRUPT GENERATION USING PUSHBUTTON AND SIMULATING THE OUTPUT
### Aim:
To Interface a push button and generate an interrupt , simulate it using an led and simuate it on  proteus 
### Components required:
STM32 CUBE IDE, Proteus 8 simulator .
### Theory:
ARM v7 Core supports multiple great features for handling exceptions and interrupts. Which includes the Nested Vectored Interrupt Controller (NVIC).
Micro-Coded Architecture So that interrupt stacking, entry, and exit are done automatically in hardware. Which offloads this work overhead from the CPU
### Processor Mode
The processor mode can change when exceptions occur. And it can be in one of the following modes:
Thread Mode: Which is entered on reset.
Handler Mode: Which is entered on all other exceptions.<br>
<img height=10% width=20% src="https://github.com/vasanthkumarch/EXPERIMENT-06-INTERRUPT-GENERATION-USING-PUSHBUTTON-AND-SIMULATING-THE-OUTPUT-/assets/36288975/4f52f2d6-4cdb-4315-b2b2-b55dc1639c43"><br>
The STM32 ARM microcontroller interrupts are generated in the following manner:
The system runs the ISR and then goes back to the main program. The NVIC and EXTI are configured. The Interrupt Service Routine (ISR) also known as the interrupt service routine handler is defined to enable the external interrupts.
Let us learn about the important features which are needed to configure external interrupts in STM32 microcontrollers.<br>
Interrupt Lines (EXTI0-EXTI15)
The STM32 ARM microcontroller features 23 event sources which are divided into two sections. The first section corresponds t external pins on each port which are P0-P15. The second section corresponds to RTC, ethernet, USB interrupts. Therefore, in the first section, we have 16 lines corresponding to line0 till line15. All of these map to a pin number.
The diagram below shows how the GPIO pins are connected to the 16 interrupt lines:<br>
<table>
	<tr>
		<td width=78%>
			
			
   One important thing to note here is that same number pins are connected to line with the same number. All of these then join to form a single line. Additionally, we can not use two pins one one line at the same time. For example out of PA1, PB1, PC1, PD1, PE1, PF1 and PG1 you can only use a single pin out of all these. This is because they are all connected to the same line EXTI1. However you can use PA1 and PA2 at the same time as they are connected with different lines.
Now each of these lines EXTI0-EXTI15 can be used to trigger an interrupt on different modes of the signal : rising edge, falling edge or rising_falling edge.
		</td>
  		<td>
	<img height=25% width=90% src="https://github.com/vasanthkumarch/EXPERIMENT-06-INTERRUPT-GENERATION-USING-PUSHBUTTON-AND-SIMULATING-THE-OUTPUT-/assets/36288975/3e1ededb-144c-4103-a64e-9132b7e06e1b">
    		</td>
	</tr>
</table>

### Procedure:
<table>
	<tr>
		<td width=50%>
			1. click on STM 32 CUBE IDE, the following screen will appear.
		</td>
 		<td>
			
![image](https://user-images.githubusercontent.com/36288975/226189166-ac10578c-c059-40e7-8b80-9f84f64bf088.png)
  		</td>
	</tr>
 	<tr>
		<td width=50%>
			2. click on FILE, click on new stm 32 project.
		</td>
 		<td>
			
			
 ![image](https://user-images.githubusercontent.com/36288975/226189215-2d13ebfb-507f-44fc-b772-02232e97c0e3.png)
![image](https://user-images.githubusercontent.com/36288975/226189230-bf2d90dd-9695-4aaf-b2a6-6d66454e81fc.png)
  		</td>
	</tr>
 	<tr>
		<td width=50%>
			3. select the target to be programmed  as shown below and click on next.
		</td>
 		<td>
			
![image](https://user-images.githubusercontent.com/36288975/226189280-ed5dcf1d-dd8d-43ae-815d-491085f4863b.png)
  		</td>
	</tr>
 	<tr>
		<td width=50%>
			4.select the program name.
		</td>
 		<td>
			<div align='center'>
   				<img height=10% width=50% src="https://user-images.githubusercontent.com/36288975/226189316-09832a30-4d1a-4d4f-b8ad-2dc28f137711.png">
   			</div>
  		</td>
	</tr>
 	<tr>
		<td width=50%>
			5. corresponding ioc file will be generated automatically.
		</td>
 		<td>
			
![image](https://user-images.githubusercontent.com/36288975/226189378-3abbdee2-0df6-470f-a3cd-79c74e3d3ad8.png)
  		</td>
	</tr>
 	<tr>
		<td width=50%>
			6.select the appropriate pins as gipo, in or out, USART or required options and configure.
		</td>
 		<td>
			
![image](https://user-images.githubusercontent.com/36288975/226189403-f7179f1a-3eae-4637-826b-ab4ec35ba1e1.png)
![image](https://user-images.githubusercontent.com/36288975/226189425-2b2414ce-49b3-4b61-a260-c658cb2e4152.png)
  		</td>
	</tr>
 	<tr>
		<td width=50%>
			7.click on cntrl+S , automaticall C program will be generated.
		</td>
 		<td>
			
![image](https://user-images.githubusercontent.com/36288975/226189443-8b43451d-0b14-47e4-a20b-cc09c6ad8458.png)
![image](https://user-images.githubusercontent.com/36288975/226189450-85ffa969-2ffb-4788-81e5-72d60fdda0f1.png)
  		</td>
	</tr>
 	<tr>
		<td width=50%>
			8. edit the program and as per required.
		</td>
 		<td>
			
![image](https://user-images.githubusercontent.com/36288975/226189461-a573e62f-a109-4631-a250-a20925758fe0.png)
  		</td>
	</tr>
 	<tr>
		<td width=50%>
			9. Select EXTI pin configuration and clock configuration.
		</td>
 		<td>
			
![image](https://user-images.githubusercontent.com/36288975/226189554-3f7101ac-3f41-48fc-abc7-480bd6218dec.png)
  		</td>
	</tr>
 	<tr>
		<td width=50%>
			10. once the project is bulild.
		</td>
 		<td>
			
![image](https://user-images.githubusercontent.com/36288975/226189577-c61cc1eb-3990-4968-8aa6-aefffc766b70.png)
  		</td>
	</tr>
 	<tr>
		<td width=50%>
			11. click on debug option.
		</td>
 		<td>
			
![image](https://user-images.githubusercontent.com/36288975/226189625-37daa9a3-62e9-42b5-a5ce-2ac63345905b.png)
  		</td>
	</tr>
 	<tr>
		<td width=50%>
			12.  Creating Proteus project and running the simulation.
   We are now at the last part of step by step guide on how to simulate STM32 project in Proteus.
13. Create a new Proteus project and place STM32F40xx i.e. the same MCU for which the project was created in STM32Cube IDE. 
14. After creation of the circuit as per requirement as shown below.
		</td>
 		<td>
			
![image](https://user-images.githubusercontent.com/36288975/233856847-32bea88a-565f-4e01-9c7e-4f7ed546ddf6.png)
  		</td>
	</tr>
 	<tr>
		<td width=50%>
			13. Double click on the the MCU part to open settings. Next to the Program File option, give full path to the Hex file generated using STM32Cube IDE. Then set the external crystal frequency to 8M (i.e. 8 MHz). Click OK to save the changes.
</td>
 		<td>
			
<img src="https://engineeringxpert.com/wp-content/uploads/2022/04/26.png">
  		</td>
	</tr>
 	<tr>
		<td width=50%>
			14. click on debug and simulate using simulation as shown below.
		</td>
 		<td>
			
![image](https://user-images.githubusercontent.com/36288975/233856904-99eb708a-c907-4595-9025-c9dbd89b8879.png)
  		</td>
	</tr>
</table>
 
 
### STM 32 CUBE PROGRAM :
```
Developed By:ROHIT JAIN D
Register Number: 212222230120
```

```C
void HAL_GPIO_EXTI_Callback(uint16_t GPIO_Pin)
{
	if((GPIO_Pin==GPIO_PIN_0))
	{
		HAL_GPIO_TogglePin(GPIOA,GPIO_PIN_1);
	}
}

```
### CIRCUIT DIAGRAM: 

<table border="3">
	<tr>
		<td>

   ### Led is OFF:
   ![Screenshot 2023-09-27 140717](https://github.com/ROHITJAIND/EX-06-INTERRUPT-GENERATION-USING-PUSHBUTTON-AND-SIMULATING-THE-OUTPUT-/assets/118707073/68ebc553-649e-47e0-8e8a-f11eacf7f9df) 
		</td>
  
 <td>

   ### Led is ON:
![Screenshot 2023-09-27 135840](https://github.com/ROHITJAIND/EX-06-INTERRUPT-GENERATION-USING-PUSHBUTTON-AND-SIMULATING-THE-OUTPUT-/assets/118707073/56f09be8-7746-46b6-bc49-626e27a69dec)
  		</td>
	</tr>
</table>
 
### Result :
Interfacing a push button and interrupt genrateion is simulated using proteus.
