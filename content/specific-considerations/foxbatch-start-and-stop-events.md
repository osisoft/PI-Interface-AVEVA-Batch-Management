---
uid: FoxBatchStartAndStopEvents
---

# FoxBatch Start and Stop Events

Customers that require connectivity to a legacy Foxboro Batch system can enable the `/FOXBATCH` switch in the Operational Settings section of PI Event Frames Interface Manager. This setting updates the start and stop events to be compatible with a Foxboro Batch system. 

## Batch

Supported Batch start codes:

| Action code | Action description | Details | Event level |
|--|--|--|--|
| 210 | Batch Open | First Action Code 210 | Batch |

Supported Batch end codes:

| Action code | Action description | Details | Event level |
|--|--|--|--|
| 211 | Batch Close | Last UnitProcedure not open since batch start Action Code 211 | Batch |

## Unit Procedure

Supported Procedure start codes:

| Action code | Action description | Event level |
|--|--|--|
| 210 | Unit Procedure Open | Unit Procedure |

Supported Procedure end codes:

| Action code | Action description | Event level |
|--|--|--|
| 211 | Unit Procedure Close | Unit Procedure |

## Operation

Supported Operation start codes:

| Action code | Action description | Details | Event level |
|--|--|--|--|
| 228 | Operation Start | First Operation name under UnitProcedure Action Code 228 | Operation |
| 230 | Operation Start | First Operation name under UnitProcedure Action Code 230 | Operation |

Supported Operation end codes:

| Action code | Action description | Details | Event level |
|--|--|--|--|
| 233 | Operation Close | Last Count of Operation Name under UnitProcedure Action Code 233 | Operation |
| 234 | Operation Close | Last Count of Operation Name under UnitProcedure Action Code 234 | Operation |

## Phase

Supported Phase start codes:

| Action code | Action description | Event level |
|--|--|--|
| 228 | Phase Start | Phase |
| 230 | Phase Start | Phase |

Supported Phase end codes:

| Action code | Action description | Event level |
| --------- | --------- | --------- |
| 233 | Phase Close | Phase |
| 234 | Phase Close | Phase |

## Phase State

| Action code | Action description | Event level |
|--|--|--|
| phaseStateRun_228 | Phase Run | Phase |
| phaseStateHeld_230 | Phase Held | Phase |
| phaseStateAborted_233 | Phase Aborted | Phase |
| phaseStateRun_234 | Phase Done | Phase |
