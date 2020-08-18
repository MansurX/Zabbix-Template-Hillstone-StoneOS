# Zabbix Template for Hillstone StoneOS

 [中文](README_CN.md)

## Overview

Here is the first template for hillstone firewall!

- Support Hillstone E series and X series

- Compatible with Zabbix 4.x and 5.x.


## Setup

Import templates on the GUI.
>Before importing, please make sure the template `Template Net Network Generic Device SNMPv2` built in zabbix exists.


## OID's

| Item | Description |
| ------------- | ------------- |
| sysCPU | Overall CPU usage rate |
| sysCurMemory | Machine memory usage |
| sysCurSession | Concurrent session of the whole machine |
| sysHAStatus | Device HA role |
| sysOverallThroughput | Throughput of the whole equipment |
| sysRamUpRate | New session rate per second |
| sysTotalMemory | Maximum device memory |
| sysTotalSession | Maximum concurrent session supported by the device |
| Fan Status | Automatically discover device fan status |
| Power Status | Automatically discover device power status |
| Slot Status | Automatically discover Slot information |
| Slot \{#SLOTINDEX\} CPU | Slot CPU usage rate |
| Slot \{#SLOTINDEX\} MemCPTotal | Maximum memory on Slot control plane |
| Slot \{#SLOTINDEX\} MemCPUsage | Memory usage of Slot control plane |
| Slot \{#SLOTINDEX\} MemDPTotal | Maximum memory on Slot data plane |
| Slot \{#SLOTINDEX\} MemDPUsage | Memory usage of Slot data plane |
| Slot \{#SLOTINDEX\} Status | Slot Status |

SNMP status and interface rate are monitored by `Template Net Network Generic Device SNMPv2`.

## Mapping
The template already contains the following mapping values.

### Fan/power status

| Value | Map |
| ------------- | ------------- |
| 0 | Good |
| 1 | No installed |
| 2 | Warning |
| 3 | Failure |
| 4 | Failure or pwered off |
| 5 | Cannot get the this staus |

### Slot status

| Value | Map |
| ------------- | ------------- |
| 0 | Invalid |
| 1 | Empty |
| 2 | In Slot |
| 3 | Wait for online |
| 4 | Online initialization completed |
| 5 | Online |
| 6 | Waiting for offline |
| 7 | Offline |
| 8 | Connection lost |
| 9 | Starting |
| 10 | Loading |
| 11 | Error |
| 12 | System does not support obtaining slot status |

### HA role

| Value | Map |
| ------------- | ------------- |
| 0 | Invalid |
| 1 | Started |
| 2 | Hello |
| 3 | Backup device |
| 4 | Primary device |
| 5 | Standby device |
| 15 | Failure |
