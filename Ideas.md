# Ideas

## Intro

TODO

## Hardware

## Chassis

This is where all the components are placed. It's simply a 2D grid of component blocks with gaps in-between for interface blocks.

Chassis is limited by the amount of blocks vertically and horizontally.

## Processor

Executes tasks based on supported instructions set types (CPU, GPU, LAN)

#### Throughput

How many bits can be processed per cycle

#### Power

How much power is used.

Power usage profile has two main variables:
* Maximum Power - usage under full load
* Idle Power - usage under zero load

Power can be adjusted to increase efficiency and/or performance

#### Clock

Clock dictates performance of the component and is limited by maximum power consumption set per component

#### Latency

Static time to respond

## Memory

Stores data on demand. Can be volatile or non-volatile

#### Size

Amount of data that can be stored

#### Throughput

How many bits can be written/read per cycle

*(inherits everything else from processor)*

## Interface

Interconnects blocks together

*(inherits everything else from processor)*

## Heatsink

Placed on top of the blocks. Increases maximum heat that the block can dissipate

#### Max Dissipation

TODO

## Fan

Exhaust the air out of the chassis

#### Max Dissipation

TODO

## Heat pipe

Routes the heat through the blocks. Supports mounting the heatsink on top

#### Max Heat

TODO

## Tasks

Machines compute tasks

Task is basically a list of action that the system has to complete.

An example:

Task can take up to two inputs, and will make one output

#### Inputs

| Name | Amount Transferred |
|---|---|
|X|1|
|Y|2|

#### Execution

| Instruction | Amount Transferred | Max Parallel Processes |
|---|---|---|
|CPU (AB)|8|2|
|CPU (AB2)|16|1|

#### Outputs

| Name | Amount Transferred |
|---|---|
|Z|16|
