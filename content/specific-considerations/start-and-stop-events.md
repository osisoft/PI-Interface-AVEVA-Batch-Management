---
uid: BIF_StartAndStopEvents
---

# Start and stop events

<!-- Customized for WonderWare -->

Events are read from the BatchIDLog and BatchDetail tables. The InBatch system can optionally provide status for Batch, Unit, and Phase level states by specifying the EnableAllStates parameter. For more information, see Command-line parameter reference. An event read from the BatchDetail table must have the UnitOrConnection information available for the interface to process and associate it with the unit. If the UnitOrConnection information is empty, the interface does not know which unit to associate the event with and waits for another event with more information.

## PIBatch/Procedure

Supported PI Batch/Procedure start codes

| Action code | Action description | Event level |
| ----------- | ------------------ | ----------- |
| 201 | Batch received Start | Batch |

Supported PI Batch/Procedure end codes

| Action code | Action description | Event level |
| ----------- | ------------------ | ----------- |
| 205 | Batch set Done | Batch |
| 206 | Batch set Closed | Batch |
| 209 | Batch set Aborted | Batch |

## PIUnitBatch/Unit Procedure

Supported PI UnitBatch/Unit Procedure start codes

| Action code | Action description | Event level |
| ----------- | ------------------ | ----------- |
| 500 | Unit Procedure received Run | Unit Procedure |

Supported PI UnitBatch/Unit Procedure end codes

| Action code | Action description | Event level |
| ----------- | ------------------ | ----------- |
| 501 | Unit Procedure received Done | Unit Procedure |

## Operation

Supported PI Operation start codes

| Action code | Action description | Event level |
| ----------- | ------------------ | ----------- |
| 502 | Operation received Run | Operation |

Supported PI Operation end codes

| Action code | Action description | Event level |
| ----------- | ------------------ | ----------- |
| 503 | Operation received Done | Operation |

## Phase

Supported PI Phase start codes

| Action code | Action description | Event level |
| ----------- | ------------------ | ----------- |
| 223 | WAIT FOR ENTRY ACK | Phase |
| 224 | Receive Entry ACK | Phase |
| 226 | Receive Ready | Phase |
| 227 | Start | Phase |
| 241 | Wait for Req Edits | Phase |
| 243 | Wait for Req Cmmt | Phase |

The start time of a phase should be represented by the first occurrence of any supported phase start codes listed in the "Supported PI Phase start codes" table.

Supported PI Phase end codes

| Action code | Action description | Event level |
| ----------- | ------------------ | ----------- |
| 233 | Received Aborted | Phase |
| 234 | Received Done | Phase |
| 235 | Reset Phase | Phase |
| 239 | Received Bad Ready | Phase |
| 415 | Done | Phase. If Collect415 is enabled, then this also sends Phase Start. |

The end time of a phase should be represented by the first occurrence of any supported phase end codes listed in the "Supported PI Phase end codes" table.
Action code 415 acts as a normal phase close if flag Collect415 Is disabled. If flag Collect415 is enabled then:

*    If a Phase close already exists, the interface will do nothing to the phase
*    If a Phase does not exist, then the interface will create a zero duration phase event with one phase state child "DONE".

