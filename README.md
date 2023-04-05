


- [Overview \& Vision](#overview--vision)
  - [Aim](#aim)
- [Big Picture](#big-picture)
- [Componenet selection](#componenet-selection)
- [Detail setup and configuration](#detail-setup-and-configuration)
  - [General wiring](#general-wiring)
  - [Seplos BMS setup](#seplos-bms-setup)
    - [Seplos firmware](#seplos-firmware)
    - [Seplos Best Practises](#seplos-best-practises)
    - [Seplos FAQ](#seplos-faq)
  - [Victron setup](#victron-setup)
    - [General setup](#general-setup)
    - [Victron Multiplus II Array setup](#victron-multiplus-ii-array-setup)
  - [Basics \& Glossary](#basics--glossary)

# Overview & Vision

We are a group of technophile guys and have set ourselves the goal of generating the energy consumed in our home ourselves as far as possible.

From this the idea was born to fill our roofs with photovoltaic, to produce as much energy as possible, to store it and to consume it ourselves.

Putting a lot of money in your hand and hiring a service provider with an all-inclusive carefree package is easy. But that was neither our idea nor our goal.

Our approach is as follows:

- from self-assembled components
- with a lot of own work and commitment
- by understanding the components and technologies
- by independent configuration and optimization of the interaction

to achieve the best possible yield using the least possible financial resources.

## Aim

The aim of this documentation is to

- document our progress and share information
- record and justify decisions together
- simplify access to information and decisions for third parties

# Big Picture

We have a wide variety of goals and approaches to how we want to build our facilities:

- "NON-GRID": Setup of a fully self-sufficient system in a non-grid-bound environment (immobile).
- "ISLAND" a partially self-sufficient grid-connected system with islanding solution in case of grid unavailability
- "STORE" a semi-autonomous grid-connected system without islanding solution

# Componenet selection

As a baseline, we have chosen a set of components and manufacturers for improved collaboration:

- Battery from XXX company (China direct order)
  - BMS: Seplos 16S-10c
  - Battery Cells: Eve LF50K
- Inverter: one version of a Victron
  - MultiPlus-II 48/3000/35
  - MultiPlus-II 48/5000/70
  - EasySolar-II 48/3000/35
- Controller: Victron
  - Cerbo GX
  - VenusOS on Raspberry Pi hardware

# Detail setup and configuration

## General wiring

This section details

- general wirings
  - control cable between the systems [here](./wiring/controlcable.md)
- PIN layout of cables to be individually crimped (Note: can also be purchased).
  - Connection Battery<->Cerbo, VE-CAN (Cerbo) to CAN (Battery/Seplos) [here](./wiring/can-vecan.md)
  - Connection Battery<->PC, Seplos Battery-Monitor to Windows as RS485-USB [here](./wiring/rs485-usb.md)

Pls find wirings for (shortcuts are explained in chapter "Big Picture")

- NON-GRID here
- ISLAND [here](./wiring/island.md)
- STORE here

## Seplos BMS setup

Here is a description of our Seplos configuration

### Seplos firmware

There are different Seplos firmwares around having advantages and disadvantages. 

Pls find a comparison including known bugs [here](./configuration/seplos_firmware.md)

### Seplos Best Practises

### Seplos FAQ

## Victron setup

In this section the Victron Multiplus configuration is described for the respective scenarios.

### General setup

Pls find details [here](./configuration/victron_mp_general.md).


### Victron Multiplus II Array setup

Pls find details [here](./configuration/victron_mp_array.md).

## Basics & Glossary

To make it easier for newcomers to get started, we have - in the confusion of common abbreviations - provided a

- [Glossary](./basics/glossary.md): created a glossary as a reference book
- summarized some basics in the context of PV, accumulators and battery management systems
