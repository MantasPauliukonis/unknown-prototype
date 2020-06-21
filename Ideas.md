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

Static time to respond (independent from clock)

#### Durability

Signifies how long the component will last before it needs to be replaced

## Memory

Stores data on demand. Can be volatile or non-volatile

* if amount can be transferred in one go, usage will decrease
* data that is not being processed or transferred, that is queued, will be stored
* running multiple tasks will severely increase usage
* will a different varieties for different purposes:
    * cache -- very fast and small
    * ram -- balance between speed and size
    * hard drive -- slow but large

#### Size

Amount of data that can be stored

#### Throughput

How many bits can be written/read per cycle

*(inherits everything else from processor)*

## Interface

Interconnects blocks together

* like a regular processor, consumes power, produces heat that is carried to the near blocks (as the interfaces are not blocks themselves)
* it's only work is to carry data

*(inherits everything else from processor)*

## Heatsink

Placed on top of the blocks. Increases maximum heat that the block can dissipate

#### Max Dissipation

Maximum heats that can be dissipated

## Fan

Exhaust the air out of the chassis

#### Max Dissipation

TODO

## Heat pipe

Routes the heat through the blocks. Supports mounting the heatsink on top

#### Max Heat

Maximum heat that can be carried

## Tasks

Machines compute tasks

* task is basically a list of action that the system has to complete
* task can take up to two inputs, and will make one output
* performance will depend on how well qualified machine is for this specific task
* components used for execution can be chosen (e.g. if one is more suitable than another)
* multiple tasks (same and different) can be run at the same time but it will have further ramifications

An example:

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
