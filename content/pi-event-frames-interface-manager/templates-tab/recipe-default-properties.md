---
uid: ABM_RecipeDefaultProperties
---

# Recipe templates default properties

<!-- Topic requires customization for specific interface (WWare) -->

## Batch Level
The following are the recipe template default values for the BATCH level:

| Template | Default
| ----- | ----- |
| Name | [Procedure] 
| Batch ID | [BatchID]
| Product | [Product] |
| Category | OSIBatch |
| Template | Procedure |

**Default Properties**

[RECIPE]

The index in the recipe template heirarchy corresponds to the RECIPE item default property (1).

      Recipe[1].DEFAULTPROPERTY[1].NAME = Recipe
      Recipe[1].DEFAULTPROPERTY[1].VALUE = [PROCEDURE|UNITPROCEDURE|OPERATION|Phase|PhaseState|BatchState|UnitState|Transition|TransitionState]

[PRODUCT]

The index in the recipe template heirarchy corresponds to the PRODUCT item default property (2).

      Product[2].DEFAULTPROPERTY[2].NAME = Product
      Product[2].DEFAULTPROPERTY[2].VALUE = [Product]

## Unit Batch Level
The following are the recipe template default values for the UNIT BATCH level:

| Template | Default
| ----- | ----- |
| Name | [UnitProcedure] 
| Batch ID | [BatchID]
| Product | [Product] |
| Category | OSIBatch |
| Template | UnitProcedure |
| SearchByStartTime | true |
| SearchByEndTime | true |
| Module Path | [UNIT] |

**Note**: Unitbatches can have the same name when SearchByStartTime and SearchByEndTime equal true.

**Default Properties**

[PROCEDURE] = 3

      .NAME = PROCEDURE
      .VALUE = [UNITPROCEDURE|OPERATION|Phase|PhaseState|BatchState|UnitState|Transition|TransitionState]

[PRODUCT] = 2

      .NAME = Product
      .VALUE = [Product]

[RECIPE] = 1

      .NAME = BatchID
      .VALUE = [BatchID]

## Operation Level
The following are the recipe template default values for the OPERATION level:

| Template | Default
| ----- | ----- |
| Name | [Operation] 
| Category | OSIBatch |
| Template | Operation |

# Phase Level
The following are the recipe template default values for the PHASE level:

| Template | Default
| ----- | ----- |
| Name | [Phase] 
| Category | OSIBatch |
| Template | Phase |
| SearchByEndTime | false |
| SearchByKey | true |

## Phase State Level
The following are the recipe template default values for the PHASE STATE level:

| Template | Default
| ----- | ----- |
| Name | [PhaseState] 
| Category | OSIBatch |
| Template | PhaseState |
| SearchByKey | true |

## Batch State Level
The following are the recipe template default values for the BATCH STATE level:

| Template | Default
| ----- | ----- |
| Name | [BatchState] |
| Category | OSIBatch |
| Template | BatchState |
| SearchByEndTime | false |

## Unit State Level
The following are the recipe template default values for the UNIT STATE level:

| Template | Default
| ----- | ----- |
| Name | [UnitState] |
| Category | OSIBatch |
| Template | UnitState |
| SearchByEndTime | false |
| Module Path | [UNIT] |

## Transition Level
The following are the recipe template default values for the TRANSITION level:

| Template | Default
| ----- | ----- |
| Name | [Transition] |
| Category | OSIBatch |
| Template | Transition |
| SearchByEndTime | false |

## Transition State Level
The following are the recipe template default values for the TRANSITION STATE level:

| Template | Default
| ----- | ----- |
| Name | [TransitionState] |
| Category | OSIBatch |
| Template | Transition |
| SearchByEndTime | false |



