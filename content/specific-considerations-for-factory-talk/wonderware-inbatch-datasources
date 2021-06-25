---
uid: wonderwareinbatchdatasources
---

# Wonderware InBatch data sources

The Wonderware InBatch Batch Execution System (BES) version 8.1 SP1 and above stores batch data in Microsoft SQL Server. The interface reads data from the following tables:

| ---------- | ---------------------- |
| View/Table | Data read by interface |
| ---------- | ---------------------- |
| BatchIDLog | UniqueID, BatchID, start time, end time |
| BatchDetail | Batch recipe data, product, equipment used for recipe execution, Start/End batch events. |

Union of tables:

*	ProcessVar
*	ProcessVarChange
*	OperatorComment
*	PhaseInstruction
*	MaterialInput
*	MaterialInputChange
*	MaterialOutput
*	EquipStatus
*	Transition
*	TransitionExpression
*	BatchQuestion
	
BatchDetail data and data for all batches, including Variable Name, Variable Actual Value, Variable Target or Old Value, and Event Timestamp.

To communicate with SQL Server databases, the interface requires Microsoft ADO driver for Microsoft SQL, part of the SQL Native client package, to be installed on the interface node. To download the SQL Native client package, go to the MSDN web site.
