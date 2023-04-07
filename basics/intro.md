- [Theroretical intro and Getting Startded](#theroretical-intro-and-getting-startded)
- [LiFePo cells](#lifepo-cells)
- [Determination of the SoC](#determination-of-the-soc)


# Theroretical intro and Getting Startded

This abstract deals with the basics around 
* Batteries
* Threshold and limit values
* Battery Management Systems (BMS)
* Inverter
* Balancer

There are a lot of settings to be made in order to operate a battery cell as well as possible in its voltage comfort zone and to give it the longest possible life.

This documentation is intended to explain central relationships. The explanations are kept short, if possible, in order not to confuse newcomers unnecessarily. The values are often only example values, which everyone has to adapt sensibly - depending on own hardware setup. 

# LiFePo cells

In order not to damage a battery cell of the type LiFePo (LFP), it should be operated within the defined specification range of the manufacturer. For my 50Ah EVE K-cells this is - as for most other manufacturers and models - min. 2,5V and max. 3,65V. Please check the [product specification](./LF50K3.2V-50Ah-Product-SpecificationVersion-D.pdf) beforehand.

> Operate your LFP cells in the limits between 2.5V and 3.65V!

To maximize the number of cycles of the cells, one should however try to avoid the maximum marginal ranges downwards and upwards. In particular, one should avoid that a cell remains at this level for days after charging to 3.65V.

> The comfortable range of a LFP cell is about 3.0V to 3.4V 

This is a voltage delta of only about 0.5V. If one moves in this range (green area in the following picture), almost the maximum possible capacity can be used. 

![LFP charging discharging](./lfp-charging-discharging-curve.png)

LFP cells have a characteristic voltage behavior based on their cell chemistry and an associated very narrow voltage range. While the cell voltage is almost stable in the middle ~80% State of Charge (SoC) range, it "drops" very quickly towards the edges. 

On the one hand, this is very useful as the voltage does not drop significantly even with a low SoC. But on the other hand, it is also more difficult to catch a cell leaving the average range of the bulk. Furthermore, it is almost impossible to determine the SoC of a cell based on its voltage due to the relatively constant voltage in the medium operating range. 

# Determination of the SoC

During charging, the cell voltage can increase abruptly depending on the SoC. This may be the case if you are chaging with high power (>0.3c). 

On the other hand, when discharging, the voltage can collapse by 0.1V or more at higher load. With a targeted operational voltage range of less than 0.5V (comfort zone), this is an immense increase/decrease!

> BMS uses the voltage only as an initial indicator, it calculates the SoC during operation based on the upper and lower limits 

The limits "full" and "empty" are to be configured individually based on the data sheet, for example

* 100% SoC (fully charged) corresponds to 3.4V..3.5V 
* 0% SoC (fully discharged) corresponds to 3V 

After initial calibration, the power flowing into the cell over time (the work W) and correspondingly being removed during discharging is measured continuously. Knowing the battery capacity (in ampere-hours, Ah), the shunt (integrated in the BMS or as separate hardware) then calculates the current SoC.
