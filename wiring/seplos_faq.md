# Seplos FAQ


# Seplos hardware and wiring
## Configure DIP switches for CAN

**Setup:** 
* Seplos 10C Hardware version

**Basics:**
* Dip Switch 1-4 define the amount of slaves connected to the master, dip switch 1 = 2^0, 2 = 2^1, 3 = 2^2, 4 = 2^3
* Dip Switch 5-8 define the address of a slave, 5 = 2^0, 6 = 2^1, 7 = 2^2, 8 = 2^3

e.g.

1 Pack: 
=> all dip switches zero

3 Pack:
=> master: has two slaves, dip 1-4: 0100
=> slave1: dip 5-8 1000, slave2: dip 5-8 0100

4 Pack:
=> master: has three slaves, dip 1-4: 1100
=> slave1: dip 5-8 1000, slave2: dip 5-8 0100, slave3: dip 5-8 1100

Matrix is available [here](./CAN_DIP_ADDRESS_SETUP.pdf)

## Configure DIP switches for RS485

* Dip Switch 1-4 define the address of the device, 1 = 2^0, 2 = 2^1, 3 = 2^2, 4 = 2^3

Matrix is available [here](./RS485_DIP_ADDRESS_SETUP.pdf)

## Seplos Master not visible in Battery Monitor

Setup: 
* Seplos 10C Hardware version
* CAN hooked up to e.g. Cerbo GX
* Master connected to Win PC, Battery Monitor running
* Slave(s) connected to Master using RS485

Problem:
Only Slave(s) visible in Battery Monitor

Solution:
If Seplos communicates on the CAN bus Master is not visible. 1. Remove CAN plug 
1. Remove CAN dip switch configuration (Dip 1-4 for CAN must be set to Zero)
1. Set Master/Slave RS485 configuration on Dip 5-8, now Master is visible in Batter Monitor 


# Seplos software configuration

## Seplos Monitor shows wrong values, 100x too much

**Problem:**

Seplos Battery Montior shows e.g. 5221.00V instead of 52.2100V

**Solution:**

Change delimiter in Windows system, usuals european format is `1.234,56`, change this to `1,234.56`.

Means: In Windows configuration 
* change comma delimiter to dot 
* change 1000 separator from dot to comma 
