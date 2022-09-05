# Introduction
Magnetic levitation systems have practical importance in many engineering systems such as in high-speed maglev passenger trains, frictionless bearings, levitation of wind tunnel models, vibration isolation of sensitive machinery, levitation of molten metal in induction furnaces, and levitation of metal slabs during manufacturing. The maglev systems can be classified as attractive systems or repulsive systems based on the source of levitation forces. These kind of systems are usually open-loop unstable and are described by highly nonlinear differential equations which present additional difficulties in controlling these systems. Therefore, it is an important task to construct high-performance feedback controllers for regulating the position of the levitated object. 

In this particular project, I worked on designing a magnetic levitation system with Sliding Mode Control of static scheme and dynamic scheme under the guidance of Dr. Bijoy Krishna Mukherjee, a professor of the Department of EEE at BITS Pilani. 

# About Magnetic Levitation Technique
Magnetic Levitation is a technique whereby an object is suspended with no support but magnetic field. The main desire of the system is to recommend an appropriate controller for the positioning of the ball in the air with the use of magnetic force. The principle of magnetic levitation has been known for over centuries and is widely used in many engineering systems such as high-speed maglev passenger trains, frictionless bearings, vibration isolations, etc.

# Model of the Levitation System
The magnetic levitation system considered here consists of a ferromagnetic ball suspended in a voltage-controlled magnetic field. Only the vertical motion is considered. The objective is to keep the ball at a prescribed reference level. The schematic diagram of the system is shown in the figure given below: 

![Maglev System](https://user-images.githubusercontent.com/74113713/188432107-46ca5d10-a77a-40be-bdf8-b74e90fad9f9.jpg)

The dynamic model of the system can be written as: 

![Dynamic Model](https://user-images.githubusercontent.com/74113713/188432714-6708e4ca-9d29-47e8-9401-d40af79e5bc0.jpg)

where, p denotes the ball’s position, v is the ball’s velocity, i is the current in the coil of the electromagnet, e is the applied voltage, R is the coil’s resistance, L is the coil’s inductance, g<sub>c</sub> is the gravitational constant, C is the magnetic force constant, and m is the mass of the levitated ball. 

The inductance L is a nonlinear function of the ball’s position p approximately given by: 

![Induction Equaton](https://user-images.githubusercontent.com/74113713/188434490-65d62c6b-abfc-4733-bee4-8178d850baba.jpg)

where, L1 is a parameter of the system.

# Simulation Results: 
Simulations are performed for the static and the two dynamic sliding mode controllers proposed. The complete model along with the controllers was built using Simulink. The results are shown in this section. 

* Static SMC: 

  The model of static SMC is given below: 
  
  ![Static SMC](https://user-images.githubusercontent.com/74113713/188436835-39c862b0-7f34-46cc-9660-cdc9bef61728.jpg)
  
  The figure shows the position versus time and the control (the applied voltage) versus time for the system when the mass value is nominal and when the mass value is   changed by ±40%.  
  
  ![Static SCM Simulation](https://user-images.githubusercontent.com/74113713/188441322-7da8b45d-5ae7-4a1c-86f0-e91007718d4c.jpg)
  
  It can be seen from the figure that the position converges to its desired value when the mass value is nominal. However, there is a small steady-state error in the position when the mass is changed. Also, some chattering can be seen due to this controller.
  
* Dynamic SMC: 

  The model of Dynamic SMC is given below:
  
  ![Dynamic SMC](https://user-images.githubusercontent.com/74113713/188441725-1c5fc7c1-b961-4573-b310-05552d2fb279.jpg)
  
  The figure shows the position versus time and the control versus time for the system when the mass value is nominal and when the mass value is changed by ±40%. 
  
  ![Dynamic SMC Simulation](https://user-images.githubusercontent.com/74113713/188443583-3f0e5f53-a2d7-4d3b-b533-1f28c1570e54.jpg)
  
  It can be seen from the above figure that the position converges to its desired value even when the mass of the object varies by ±40%. Hence, the controlled system is robust to changes in the mass value. Also, it can be seen from the figure that the chattering in the control signal is greatly reduced when the dynamic sliding mode controller is applied.
  
* Modified Dynamic SMC

  The model of Modified Dynamic SMC is given below:
  
  ![Modified Dynamic SMC](https://user-images.githubusercontent.com/74113713/188443954-48c28bce-b02a-4d4a-b902-9c2e567ff84e.jpg)
  
  The figure shows the position versus time and the control versus time for the system when the mass value is nominal and when the mass value is changed by ±40%. 
  
  ![Modified Dynamic SMC Simulation](https://user-images.githubusercontent.com/74113713/188445814-561a6d18-4753-482e-b55f-c7906397d687.jpg)
 
  It can be seen from the above that the position converges to its desired value even when the mass of the object varies by ±25%. Hence, the controlled system is robust to changes in the mass value. Also, it can be seen from the figure that the chattering in the control signal is almost eliminated when applying the modified dynamic sliding mode controller.


Finally, the below figure shows the position versus time for the three proposed controllers for the case when the mass
value is nominal.  

![Comparison](https://user-images.githubusercontent.com/74113713/188446518-92ff5d01-9f52-474d-81c2-b533c66bf181.jpg)

The simulation results indicate that the proposed control schemes work well when applied to the magnetic levitation system. Moreover, the robustness
of the developed control schemes to variations in the parameters of the system is investigated. It can be concluded from the simulations that the static control scheme is somewhat robust to changes in the mass of the object. However, the dynamic controllers are very robust. It is also clear that the dynamic controllers greatly reduce the chattering. Clearly, The third control scheme (the modified dynamic sliding mode scheme) gives the best results among the three controllers.

# Note: 
I haven't included the derivation and equations of the proposed controllers here. You can refer to the following presentation for the equations of the controllers.  
https://docs.google.com/presentation/d/1WB3b9q4LgEHdtEV8Yyfv44NVU2DjbPQkT4U9KsdY0Ew/edit#slide=id.p  

