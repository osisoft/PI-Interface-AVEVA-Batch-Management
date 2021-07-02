---
uid: BIF_DataSources
---

# Data sources

<!-- Customized for WonderWare -->

The following tables map placeholders to the data source table from which they are derived.

## Combined - BatchDetail + BatchIDLog

| Template Placeholder | SQL Column Name | Description |
| -------------------- | --------------- | ----------- |
| [ActionCD] | Action_CD | Defined in BatchDetail table. |
| [TimeStamp] | DateTime | Defined in BatchDetail table. |
| [UniqueID] | Batch_Log_ID | Used to bind both BatchDetail and BatchIDLog tables. Serves as UniqueID of each batch. |
| [BatchID] | Batch_ID | Defined in BatchIDLog table. |
| [Product] | Product_Name or Product_ID | Defined in BatchIDLog table. This placeholder maps to Product_Name if non-empty, otherwise it maps to Product_ID. |
| [Procedure] | Recipe_ID | Defined in BatchIDLog table. |
| [Unit] | UnitOrConnection | Defined in BatchDetail table. |
| [UnitProcedure] | UnitProcedure_ID | Defined in BatchDetail table. |
| [Operation] | Operation_ID | Defined in BatchDetail table. |
| [Phase] | Phase_ID | Defined in BatchDetail table. |
| [PhaseInstance] | Index derived from Phase_Instance_ID | Defined in BatchDetail table. Provides phase instance index. |
| [PhaseUID] | Phase_Incident_ID | Defined in BatchDetail table. All phase states under this phase will have the same PhaseUID in the WWInBatch database. |
| [UserID] | DoneBy_User_ID | Defined in BatchDetail table. |
| [Campaign] | Campaign_ID | Defined in BatchIDLog table. |
| [Lot] | Lot_ID | Defined in BatchIDLog table. |
| [Train] | Train_ID | Defined in BatchIDLog table. |
| [BatchSize] | Batch_Size | Defined in BatchIDLog table. |
| [ProductID] | Product_ID | Defined in BatchIDLog table. |
| [ProductName] | Product_Name | Defined in BatchIDLog table. |
| [RecipeID] | Recipe_ID | Defined in BatchIDLog table. |
| [RecipeName] | Recipe_Name | Defined in BatchIDLog table. |
| [RecipeVersion] | Recipe_Version | Defined in BatchIDLog table. |
| [RecipeState] | Recipe_State | Defined in BatchIDLog table. |
| RecipeType] | Recipe_Type | Defined in BatchIDLog table. |

## Combined ProcessVar + BatchIDLog

| Template Placeholder | SQL Column Name | Description |
| -------------------- | --------------- | ----------- |
| [TimeStamp] | DateTime | Defined in ProcessVar table. |
| [BatchID] | Batch_ID | Defined in BatchIDLog table. |
| [UniqueID] | Batch_Log_ID | Used to bind both ProcessVar and BatchIDLog tables. Serves as UniqueID of each batch |
| [Product] | Product_Name or Product_ID | Defined in BatchIDLog table. This placeholder maps to Product_Name if non-empty, otherwise it maps to Product_ID |
| [Procedure] | Recipe_ID | Defined in BatchIDLog table. |
| [Unit] | UnitOrConnection | Defined in ProcessVar table. |
| [UnitProcedure] | UnitProcedure_ID | Defined in ProcessVar table. |
| [Operation] | Operation_ID | Defined in ProcessVar table. |
| [Phase] | Phase_ID | Defined in ProcessVar table. |
| [PhaseInstance] | Index derived from Phase_Instance_ID | Defined in ProcessVar table. Provides phase instance index. |
| [Parameter] | Parameter_ID | Defined in ProcessVar table. |
| [Descript] | N/A | Contains "Actual_Value" if column Actual_Value is NOT empty, otherwise contains text "Target_Value". |
| [Value] | Actual_Value or Target_Value | Contains the data from Actual_Value column if it is not empty, otherwise contains data from Target_Value column. |
| [TargetValue] | Target_Value | Defined in ProcessVar table. |
| [ActualValue] | Actual_Value | Defined in ProcessVar table. |
| [EU] | UnitOfMeasure | Defined in ProcessVar table. |
| [Campaign] | Campaign_ID | Defined in BatchIDLog table. |
| [Lot] | Lot_ID | Defined in BatchIDLog table. |
| [Train] | Train_ID | Defined in BatchIDLog table. |
| [BatchSize] | Batch_Size | Defined in BatchIDLog table. |
| [ProductID] | Product_ID | Defined in BatchIDLog table. |
| [ProductName] | Product_Name | Defined in BatchIDLog table. |
| [RecipeID] | Recipe_ID | Defined in BatchIDLog table. |
| [RecipeName] | Recipe_Name | Defined in BatchIDLog table. |
| [RecipeVersion] | Recipe_Version | Defined in BatchIDLog table.|
| [RecipeState] | Recipe_State | Defined in BatchIDLog table. |
| [RecipeType] | Recipe_Type | Defined in BatchIDLog table. |

## Combined ProcessVarChange + BatchIDLog

| Template Placeholder | SQL Column Name | Description |
| -------------------- | --------------- | ----------- |
| [TimeStamp] | DateTime | Defined in ProcessVarChange table. |
| [BatchID] | Batch_ID | Defined in BatchIDLog table. |
| [UniqueID] | Batch_Log_ID | Used to join the ProcessVarChange and BatchIDLog tables. Serves as UniqueID of each batch. |
| [Product] | Product_Name or Product_ID | Defined in BatchIDLog table. This placeholder maps to Product_Name if non-empty, otherwise it maps to Product_ID. |
| [Procedure] | Recipe_ID | Defined in BatchIDLog table. |
| [Unit] | UnitOrConnection | Defined in ProcessVarChange table. |
| [UnitProcedure] | UnitProcedure_ID | Defined in ProcessVarChange table. |
| [Operation] | Operation_ID | Defined in ProcessVarChange table. |
| [Phase] | Phase_ID | Defined in ProcessVarChange table. |
| [PhaseInstance] | Index derived from Phase_Instance_ID | Defined in ProcessVarChange table. Provides phase instance index. |
| [Parameter] | Parameter_ID | Defined in ProcessVarChange table. |
| [Descript] | N/A | Contains text "ProcessVarChange". |
| [Value] | New_Target_Value | Defined in ProcessVarChange table. |
| [TargetValue] | New_Target_Value | Defined in ProcessVarChange table. |
| [OldValue] | Old_Target_Value | Defined in ProcessVarChange table. |
| [EU] | UnitOfMeasure | Defined in ProcessVarChange table. |
| [UserID] | DoneBy_User_ID | Defined in ProcessVarChange table. |
| [ReviewerID] | CheckBy_User_ID | Defined in ProcessVarChange table. |
| [Campaign] | Campaign_ID | Defined in BatchIDLog table. |
| [Lot] | Lot_ID | Defined in BatchIDLog table. |
| [Train] | Train_ID | Defined in BatchIDLog table. |
| [BatchSize] | Batch_Size | Defined in BatchIDLog table. |
| [ProductID] | Product_ID | Defined in BatchIDLog table. |
| [ProductName] | Product_Name | Defined in BatchIDLog table. |
| [RecipeID] | Recipe_ID | Defined in BatchIDLog table. |
| [RecipeName] | Recipe_Name | Defined in BatchIDLog table. |
| [RecipeVersion] | Recipe_Version | Defined in BatchIDLog table. |
| [RecipeState] | Recipe_State | Defined in BatchIDLog table. |
| [RecipeType] | Recipe_Type | Defined in BatchIDLog table. |

## Combined PhaseInstruction + BatchIDLog

| Template Placeholder | SQL Column Name | Description |
| -------------------- | --------------- | ----------- |
| [TimeStamp] | DateTime | Defined in PhaseInstruction table. |
| [BatchID] | Batch_ID | Defined in BatchIDLog table. |
| [UniqueID] | Batch_Log_ID | Used to bind both PhaseInstruction and BatchIDLog tables. Serves as UniqueID of each batch. |
| [Product] | Product_Name or Product_ID | Defined in BatchIDLog table. This placeholder maps to Product_Name if non-empty, otherwise it maps to Product_ID. |
| [Procedure] | Recipe_ID | Defined in BatchIDLog table. |
| [Unit] | UnitOrConnection | Defined in PhaseInstruction table. |
| [UnitProcedure] | UnitProcedure_ID | Defined in PhaseInstruction table. |
| [Operation] | Operation_ID | Defined in PhaseInstruction table. |
| [Phase] | Phase_ID | Defined in PhaseInstruction table. |
| [PhaseInstance] | Index derived from Phase_Instance_ID | Defined in PhaseInstruction table. Provides phase instance index. |
| [Parameter] | N/A | Contains text: "PhaseInstruction" | 
| [Value] | Instruction (complex) | Defined in PhaseInstruction table. |
| [Campaign] | Campaign_ID | Defined in BatchIDLog table. |
| [Lot] | Lot_ID | Defined in BatchIDLog table. |
| [Train] | Train_ID | Defined in BatchIDLog table. |
| [BatchSize] | Batch_Size | Defined in BatchIDLog table. |
| [ProductID] | Product_ID | Defined in BatchIDLog table. |
| [ProductName] | Product_Name | Defined in BatchIDLog table. |
| [RecipeName] | Recipe_Name | Defined in BatchIDLog table. |
| [RecipeVersion] | Recipe_Version | Defined in BatchIDLog table. |
| [RecipeState] | Recipe_State | Defined in BatchIDLog table. |
| [RecipeType] | Recipe_Type | Defined in BatchIDLog table. |

## Combined OperatorComment + BatchIDLog

| Template Placeholder | SQL Column Name | Description |
| -------------------- | --------------- | ----------- |
| [TimeStamp] | DateTime | Defined in OperatorComment table. |
| [BatchID] | Batch_ID | Defined in BatchIDLog table. |
| [| UniqueID] | Batch_Log_ID | Used to bind both OperatorComment and BatchIDLog tables. Serves as UniqueID of each batch. |
| [Product] | Product_Name or Product_ID | Defined in BatchIDLog table. This placeholder maps to Product_Name if non-empty, otherwise it maps to Product_ID. |
| [Procedure] | Recipe_ID | Defined in BatchIDLog table. |
| Unit] | UnitOrConnection | Defined in OperatorComment table. |
| [UnitProcedure] | UnitProcedure_ID | Defined in OperatorComment table. |
| [Operation] | Operation_ID | Defined in OperatorComment table. |
| [Phase] | Phase_ID | Defined in OperatorComment table. |
| [PhaseInstance] | Index derived from Phase_Instance_ID | Defined in OperatorComment table. Provides phase instance index. |
| [Parameter] | N/A | Contains text: "OperatorComment" |
| [Value] | Operator_Comment (complex) | Defined in OperatorComment table. |
| [UserID] | DoneBy_User_ID | Defined in OperatorComment table. |
| [ReviewerID] | CheckBy_User_ID | Defined in OperatorComment table. |
| [Campaign] | Campaign_ID | Defined in BatchIDLog table. |
| [Lot] | Lot_ID | Defined in BatchIDLog table. |
| [Train] | Train_ID | Defined in BatchIDLog table. |
| [BatchSize] | Batch_Size | Defined in BatchIDLog table. |
| [ProductID] | Product_ID | Defined in BatchIDLog table. |
| [ProductName] | Product_Name | Defined in BatchIDLog table. |
| [RecipeID] | Recipe_ID | Defined in BatchIDLog table. |
| [RecipeName] | Recipe_Name | Defined in BatchIDLog table. |
| [RecipeVersion] | Recipe_Version | Defined in BatchIDLog table. |
| [RecipeState] | Recipe_State | Defined in BatchIDLog table. |
| [RecipeType] | Recipe_Type | Defined in BatchIDLog table. |

## Combined MaterialInput + BatchIDLog+BatchDetail

| Template Placeholder | SQL Column Name | Description |
| -------------------- | --------------- | ----------- |
| [TimeStamp] | DateTime | Defined in MaterialInput table. |
| [BatchID] | Batch_ID | Defined in BatchIDLog table. |
| [UniqueID]| Batch_Log_ID | Used to bind both MaterialInput and BatchIDLog tables. Serves as UniqueID of each batch. |
| [Product] | Product_Name or Product_ID | Defined in BatchIDLog table. This placeholder maps to Product_Name if non-empty, otherwise it maps to Product_ID. |
| [Procedure] | Recipe_ID | Defined in BatchIDLog table. |
| [Unit] | UnitOrConnection | Defined in MaterialInput table. |
| [UnitProcedure] | UnitProcedure_ID | Defined in MaterialInput table. |
| [Operation] | Operation_ID | Defined in MaterialInput table. |
| [Phase] | Phase_ID | Defined in MaterialInput table. |
| [PhaseInstance] | Index derived from Phase_Instance_ID | Defined in MaterialInput table. Provides phase instance index. |
| [Parameter] | N/A | Contains text: "MaterialInput" |
| [Descript] | Material_Parameter | Defined in MaterialInput table. |
| [Value] | Actual_Qty | Defined in MaterialInput table. |
| [ActualValue] | Actual_Qty | Defined in MaterialInput table. |
| [TargetValue] | Target_Qty | Defined in MaterialInput table. |
| [EU] | UnitOfMeasure | Defined in MaterialInput table. |
| [UserID] | DoneBy_User_ID | Defined in BatchDetail table. |
| [ReviewerID] | CheckBy_User_ID | Defined in BatchDetail table. |
| [MaterialID] | Material_ID | Defined in MaterialInput table. |
| [MaterialName] | Material_Name | Defined in MaterialInput table. |
| [MaterialLotID] | Mtrl_Lot_ID | Defined in MaterialInput table. |
| [Campaign] | Campaign_ID | Defined in BatchIDLog table. |
| [Lot] | Lot_ID | Defined in BatchIDLog table. |
| [Train] | Train_ID | Defined in BatchIDLog table. |
| [BatchSize] | Batch_Size | Defined in BatchIDLog table. |
| [ProductID] | Product_ID | Defined in BatchIDLog table. |
| [ProductName] | Product_Name | Defined in BatchIDLog table. |
| [RecipeID] | Recipe_ID | Defined in BatchIDLog table. |
| [RecipeName] | Recipe_Name | Defined in BatchIDLog table. |
| [RecipeVersion] | Recipe_Version | Defined in BatchIDLog table. |
| [RecipeState] | Recipe_State | Defined in BatchIDLog table. |
| [RecipeType] | Recipe_Type | Defined in BatchIDLog table. |

## Combined MaterialInputChange + BatchIDLog

| Template Placeholder | SQL Column Name | Description |
| -------------------- | --------------- | ----------- |
| [TimeStamp] | DateTime | Defined in MaterialInputChange table. |
| [BatchID] | Batch_ID | Defined in BatchIDLog table. |
| [UniqueID] | Batch_Log_ID | Used to bind both MaterialInputChange and BatchIDLog tables. Serves as UniqueID of each batch. |
| [Product] | Product_Name or Product_ID | Defined in BatchIDLog table. This placeholder maps to Product_Name if non-empty, otherwise it maps to Product_ID. |
| [Procedure] | Recipe_ID | Defined in BatchIDLog table. |
| [Unit] | UnitOrConnection | Defined in MaterialInputChange table. |
| [UnitProcedure] | UnitProcedure_ID | Defined in MaterialInputChange table. |
| [Operation] | Operation_ID | Defined in MaterialInputChange table. |
| [Phase] | Phase_ID | Defined in MaterialInputChange table. |
| [PhaseInstance] | Index derived from Phase_Instance_ID | Defined in MaterialInputChange table. Provides phase instance index. |
| [Parameter] | N/A | Contains text: "MaterialInputChange" |
| [Descript] | Material_Parameter | Defined in MaterialInputChange table. |
| [Value] | New_Target_Qty | Defined in MaterialInputChange table. |
| [TargetValue] | New_Target_Qty | Defined in MaterialInputChange table. |
| [OldValue] | Old_Target_Qty | Defined in MaterialInputChange table. |
| [MaterialID] | Material_ID | Defined in MaterialInput table. |
| [UserID] | DoneBy_User_ID | Defined in MaterialInputChange table. |
| [ReviewerID] | CheckBy_User_ID | Defined in MaterialInputChange table. |
| [Campaign] | Campaign_ID | Defined in BatchIDLog table. |
| [Lot] | Lot_ID | Defined in BatchIDLog table. |
| [Train] | Train_ID | Defined in BatchIDLog table. |
| [BatchSize] | Batch_Size | Defined in BatchIDLog table. |
| [ProductID] | Product_ID | Defined in BatchIDLog table. |
| [ProductName] | Product_Name | Defined in BatchIDLog table. |
| [RecipeID] | Recipe_ID | Defined in BatchIDLog table. |
| [RecipeName] | Recipe_Name | Defined in BatchIDLog table. |
| [RecipeVersion] | Recipe_Version | Defined in BatchIDLog table. |
| [RecipeState] | Recipe_State | Defined in BatchIDLog table. |
| [RecipeType] | Recipe_Type | Defined in BatchIDLog table. |

## Combined MaterialOutput + BatchIDLog

| Template Placeholder | SQL Column Name | Description |
| -------------------- | --------------- | ----------- |
| [TimeStamp] | DateTime | Defined in MaterialOutput table. |
| [BatchID] | Batch_ID | Defined in BatchIDLog table. |
| [UniqueID] | Batch_Log_ID | Used to bind both MaterialOutput and BatchIDLog tables. Serves as UniqueID of each batch. |
| [Product] | Product_Name or Product_ID | Defined in BatchIDLog table. This placeholder maps to Product_Name if non-empty, otherwise it maps to Product_ID. |
| [Procedure] | Recipe_ID | Defined in BatchIDLog table. |
| [Unit] | UnitOrConnection | Defined in MaterialOutput table. |
| [UnitProcedure] | UnitProcedure_ID | Defined in MaterialOutput table. |
| [Operation] | Operation_ID | Defined in MaterialOutput table. |
| [Phase] | Phase_ID | Defined in MaterialOutput table. |
| [PhaseInstance] | Index derived from Phase_Instance_ID | Defined in MaterialOutput table. Provides phase instance index. |
| [Parameter] | N/A | Contains text: "MaterialOutput" |
| [Descript] | Material_Parameter | Defined in MaterialOutput table. |
| [Value] | Actual_Qty | Defined in MaterialOutput table. |
| [ActualValue] | Actual_Qty | Defined in MaterialOutput table. |
| [TargetValue] | Target_Qty | Defined in MaterialOutput table. |
| [EU] | UnitOfMeasure | Defined in MaterialOutput table. |
| [MaterialID] | Material_ID | Defined in MaterialOutput table. |
| [MaterialName] | Material_Name | Defined in MaterialOutput table. |
| [Campaign] | Campaign_ID | Defined in BatchIDLog table. |
| [Lot] | Lot_ID | Defined in BatchIDLog table. |
| [Train] | Train_ID | Defined in BatchIDLog table. |
| [BatchSize] | Batch_Size | Defined in BatchIDLog table. |
| [ProductID] | Product_ID | Defined in BatchIDLog table. |
| [ProductName] | Product_Name | Defined in BatchIDLog table. |
| [RecipeID] | Recipe_ID | Defined in BatchIDLog table. |
| [RecipeName] | Recipe_Name | Defined in BatchIDLog table. |
| [RecipeVersion] | Recipe_Version | Defined in BatchIDLog table. |
| [RecipeState] | Recipe_State | Defined in BatchIDLog table. |
| [RecipeType] | Recipe_Type | Defined in BatchIDLog table. |

## Combined TransitionExpression + BatchIDLog

| Template Placeholder | SQL Column Name | Description |
| -------------------- | --------------- | ----------- |
| [TimeStamp] | DateTime | Defined in TransitionExpression table. |
| [BatchID] | Batch_ID | Defined in BatchIDLog table. |
| [UniqueID] | Batch_Log_ID | Used to bind both TransitionExpression and BatchIDLog tables. Serves as UniqueID of each batch. |
| [Product] | Product_Name or Product_ID | Defined in BatchIDLog table. This placeholder maps to Product_Name if non-empty, otherwise it maps to Product_ID. |
| [Procedure] | Recipe_ID | Defined in BatchIDLog table. |
| [UnitProcedure] | UnitProcedure_ID | Defined in TransitionExpression table. |
| [Operation] | Operation_ID | Defined in TransitionExpression table. |
| [Phase] | Transition_ID | Defined in TransitionExpression table. |
| [PhaseInstance] | Transition_Instance_ID | Defined in TransitionExpression table. |
| [Parameter] | N/A | Contains text: "TransitionExpression" |
| [Value] | Expression_Text (complex) | Defined in TransitionExpression table. |
| [Campaign] | Campaign_ID | Defined in BatchIDLog table. |
| [Lot] | Lot_ID | Defined in BatchIDLog table. |
| [Train] | Train_ID | Defined in BatchIDLog table. |
| [BatchSize] | Batch_Size | Defined in BatchIDLog table. |
| [ProductID] | Product_ID | Defined in BatchIDLog table. |
| [ProductName] | Product_Name | Defined in BatchIDLog table. |
| [RecipeID] | Recipe_ID | Defined in BatchIDLog table. |
| [RecipeName] | Recipe_Name | Defined in BatchIDLog table. |
| [RecipeVersion] | Recipe_Version | Defined in BatchIDLog table. |
| [RecipeState] | Recipe_State | Defined in BatchIDLog table. |
| [RecipeType] | Recipe_Type | Defined in BatchIDLog table. |

## Combined BatchQuestion + BatchIDLog + CodeTable

| Template Placeholder | SQL Column Name | Description |
| -------------------- | --------------- | ----------- |
| [TimeStamp] | DateTime | Defined in BatchQuestion table. |
| [BatchID] | Batch_ID | Defined in BatchIDLog table. |
| [UniqueID] | Batch_Log_ID | Used to bind both BatchQuestion and BatchIDLog tables. Serves as UniqueID of each batch. |
| [Product] | Recipe_ID | Defined in BatchIDLog table. |
| [Parameter] | N/A | Contains text: "BatchQuestion". |
| [Value] | Question, Description (complex) | Question defined in BatchQuestion table and Description obtained from CodeTable table corresponding to the code in the Answer column in BatchQuestion table. |
| [Campaign] | Campaign_ID | Defined in BatchIDLog table. |
| [Lot] | Lot_ID | Defined in BatchIDLog table. |
| [Train] | Train_ID | Defined in BatchIDLog table. |
| [BatchSize] | Batch_Size | Defined in BatchIDLog table. |
| [ProductID] | Product_ID | Defined in BatchIDLog table. |
| [ProductName] | Product_Name | Defined in BatchIDLog table. |
| [RecipeID] | Recipe_ID | Defined in BatchIDLog table. |
| [RecipeName] | Recipe_Name | Defined in BatchIDLog table. |
| [RecipeVersion] | Recipe_Version | Defined in BatchIDLog table. |
| [RecipeState] | Recipe_State | Defined in BatchIDLog table. |
| [RecipeType] | Recipe_Type | Defined in BatchIDLog table. |

## Combined Transition + BatchIDLog

| Template Placeholder | SQL Column Name | Description |
| -------------------- | --------------- | ----------- |
| [TimeStamp] | DateTime | Defined in Transition table. |
| [BatchID] | Batch_ID | Defined in BatchIDLog table. |
| [UniqueID]  | Batch_Log_ID | Used to bind both Transition and BatchIDLog tables. Serves as UniqueID of batch. |
| [Product] | Product_Name or Product_ID | Defined in BatchIDLogTable. This placeholder maps to Product_Name if non-empty, otherwise it maps to Product_ID. |
| [Procedure] | Recipe_ID | Defined in BatchIDLog table. |
| [UnitProcedure] | UnitProcedure_ID | Defined in Transition table. |
| [Operation] | Operation_ID | Defined in Transition table. |
| [Phase] | Transition_ID | Defined in Transition table. |
| [PhaseInstance] | Transition_Instance_ID | Defined in Transition table. |
| [Parameter] | N/A | Contains text: "Transition" |
| [TransitionID] | Transition_ID | Defined in Transition table. |
| [TransitionInstance] | Transition_Instance_ID | Defined in Transition table. |
| [Lot] | Lot_ID | Defined in BatchIDLog table. |
| [Campaign] | Campaign_ID | Defined in BatchIDLog table. |
| [Train] | Train_ID | Defined in BatchIDLog table. |
| [BatchSize] | Batch_Size | Defined in BatchIDLog table. |
| [ProductID] | Product_ID | Defined in BatchIDLog table. |
| [ProductName] | Product_Name | Defined in BatchIDLog table. | 
| [RecipeID] | Recipe_ID | Defined in BatchIDLog table. |
| [RecipeName] | Recipe_Name | Defined in BatchIDLog table. |
| [RecipeVersion] | Recipe_Verison | Defined in BatchIDLog table. |
| [RecipeState] | Recipe_State | Defined in BatchIDLog table. |

## Combined EquipStatus + BatchIDLog

| Template Placeholder | SQL Column Name | Description |
| -------------------- | --------------- | ----------- |
| [TimeStamp] | DateTime | Defined in EquipStatus table. |
| [BatchID] | Batch_ID | Defined in BatchIDLog table. |
| [Unit] | UnitOrSegment | Defined in EquipStatus table. |
| [UniqueID] | Batch_Log_ID | Defined in BatchIDLog table. |
| [Product] | Product_ID or Product_Name | Defined in BatchIDLog table. This placeholder maps to Product_Name if non-empty, otherwise it maps to Product_ID. |
| [Parameter] | N/A | Contains text "EquipStatus" |
| [EquipStatus] | New_Status | Defined in EquipStatus table. |
| [UserID] | DoneBy_User_ID | Defined in EquipStatus table. |
| [ReviewerID] | CheckBy_User_ID | Defined in EquipStatus table. |
| [Campaign] | Campaign_ID | Defined in BatchIDLog table. |
| [Lot] | Lot_ID | Defined in BatchIDLog table. |
| [Train] | Train_ID | | Defined in BatchIDLog table. |
| [BatchSize] | Batch_Size | Defined in BatchIDLog table. |
| [ProductID] | Product_ID | Defined in BatchIDLog table. |
| [ProductName] | Product_Name | Defined in BatchIDLog table. |
| [RecipeID] | Recipe_ID | Defined in BatchIDLog table. |
| [RecipeName] | Recipe_Name | Defined in BatchIDLog table. |
| [RecipeVersion] | Recipe_Version | Defined in BatchIDLog table. |
| [RecipeState] | Recipe_State | Defined in BatchIDLog table. |
| [RecipeType] | Recipe_Type | Defined in BatchIDLog table. |
