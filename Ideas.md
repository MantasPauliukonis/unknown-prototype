# Ideas

## Intro

TODO

## Hardware

## Chassis

This is where all the components are placed. It's simply a 2D grid of component blocks with gaps in-between for interface blocks.

Chassis is limited by the amount of blocks vertically and horizontally.

## Processor

Executes tasks based on supported instructions set types (CPU, GPU)

* may accommodate a single or multiple instruction sets (fixed purpose or general purpose)

#### Throughput

How many bits can be processed per cycle

Calculation: `Throughput = Clock * Throughput per Clock`

#### Power

How much power is used.

Power usage profile has two main variables:
* Maximum Power - usage under full load
* Idle Power - usage under zero load

Power can be adjusted to increase efficiency and/or performance

Calculation: `Power = max(Clock * Power by Clock * Load %, Idle Power)`

*Power by Frequency* describes maximum power that is used under certain clock on full load. Component will have such specs:
* power under minimum clock (equals to Idle Power)
* power under maximum clock (equals to Maximum Power)

#### Clock

Clock dictates performance of the component and is limited by maximum power consumption set per component

#### Latency

Static time to respond (independent from clock)

#### Durability

Signifies how long the component will last before it needs to be replaced. Durability rating will changed based on the power used

## Memory

Stores data on demand. Can be volatile or non-volatile

* if data can be transferred in one go, memory won't be used
* data that is not being processed or transferred, that is queued, will be stored
* running multiple tasks will severely increase the usage
* will have a different varieties for different purposes:
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

Maximum heat that can be dissipated

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
* performance will depend on how well qualified machine is for this specific task
* components used for execution can be chosen (e.g. if one is more suitable than another)
* multiple tasks (same and different) can be run at the same time but it will have further ramifications


#### Execution

| Instruction | Incoming Size | Outgoing Size | Max Parallel Processes |
|---|---|---|--|
|CPU (AB)|4|8|2|
|CPU (AB2)|8|16|1|

* task is executed synchronously from top to bottom
* when parallel processing is supported the load can be distributed among the same type of components
* if system does not have a processor with a required instruction, task can't be executed

## Gameplay

* player advances through the levels in a non linear fashion
* each level involves one or multiple criteria that the built system must match
* criteria might be assigned with the bronze, silver or gold reward (so player can return to the level later)
* player gains points that can be spent to unlock new components and or levels
* levels are grouped into chapters, that unlike levels are unlocked in a linear way
* each chapter has a set of components that can be unlocked (may or may not overlap)