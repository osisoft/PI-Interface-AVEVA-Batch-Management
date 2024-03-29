---
uid: BIF_EventFrames
---

# Event frames

<!-- Customized for WonderWare -->

Use event frames to record batch data. Event frames allow you to use recipe templates to define the attributes to be stored in event frames at every level of the hierarchy.

Each event frame contains the following fields:

* Name
* Description
* Start time
* End time
* Template
* Category (Default is "OSIBatch")
* Batch properties (stored in event frame attributes)
* Referenced elements such as unit or phase module

To view batch event frames and AF elements generated by the interface, use PI System Explorer. In the root-level event frame, the Name field contains the batch ID from the data source. In lower-level event frames, the Name field contains the recipe name. In event frames for a procedure-level recipe, the product and recipe properties from the data source are stored as attributes. For unit procedure-level recipes, the batch ID and product from the data source are stored as attributes.

If the highest recipe level is an operation or phase (that is, neither procedure nor unit procedure levels are defined), the interface creates event frames that correspond to the procedure and unit procedure level.

The following sections explain how data is stored in event frames for each level of the batch hierarchy.

## Procedure
    
For each batch in the data source, the interface creates a root-level event frame that represents the procedure in the recipe. Each root-level event frame contains a collection of child event frames that correspond to unit procedures. Data from source batch events (that is, properties) can be recorded in the attributes of the event frame and in PI points. Source batches can have identical IDs and recipe names in the same time frame.
    
To match the source batch with an event frame, the interface stores additional information in the extended properties of the root event frame. The Name property contains the ID of the source batch, and the Value property contains an XML structure composed of the following batch data:

* Batch ID
* Product (searchable)
* Formula name
* Recipe (searchable)
* Recipe type
* Start time UTC
* End time UTC
* Interface name
* Interface ID
* Data source
    
The following table shows how the source batch properties map to event frame data.

| Source Procedure Property | Event Frame Field | Event Frame Attribute |
|--|--|--|
| BatchID | Name |  |
| Procedure Name |  | Recipe |
| Product |  | Product |
| Start Time | Start Time |  |
| End Time | End Time |  |
        
By default, the interface captures the following batch-associated properties and stores them in procedure-level event frame attributes:

* Recipe header
* Formula header
* Recipe value
* Report
    
For the preceding attributes, the name is assigned from the source [DESCRIPTION] column, the value from the source [PVALUE] columns, and the unit of measure attribute from the [EU] column. 

The procedure-level event frame can represent merged source batches. The product and recipe attributes contain data associated with the source batch that started the merged event frame. For each merged source batch, the interface creates an entry node in the event frame's extended properties, named using the unique ID of the source batch, with its value containing an XML structure composed of the original source batch properties. 

## Unit Procedure
    
The interface creates a unit procedure-level event frame for each unit procedure read from the data source. Each unit procedure-level event frame is a child of the procedure-level event frame and contains the subset of event frames that represent the source batch operation-level recipe. The start and end times of an event frame record the start and end of physical processing in a unit. 

The name field of the unit procedure-level event frames contains the unit procedure name as read from the data source. The batch ID and product properties are searchable attributes of the event frame. The following table shows how, by default, the source batch properties map to event frame data:

| Source UnitProcedure Property | Event Frame Field | Event Frame Attribute | Reference Element |
|--|--|--|--|
| BatchID |  | BatchID |  |
| UnitProcedure Name | Name | Procedure |  |
| Product |  | Product |  |
| Start Time | Start Time |  |  |
| End Time | End Time |  |  |
| Unit |  |  | Unit |
    
In addition to batch ID, procedure and product attributes, the interface records recipe and report events in event frame attributes. For these events, the attribute name is assigned from the [DESCRIPTION] column, the value from the source [PVALUE] column, and units of measure from the [EU] column. 

Unit procedure-level event frame properties do not change if the parent object is a merged event frame. By default, unit procedure event frames contain the batch ID and procedure name read from the data source. (To override the default, use PI Event Frame Interface Manager to configure the Batch ID mask field on the Batch Settings page.) 

When operation or phase-level recipes are run, the interface uses the operation or phase name as the name of the unit procedure-level event frame. 

## Operation

The interface creates an operation-level event frame for each operation read from the data source. Each operation-level event frame is a child of the unit procedure-level event frame and contains the subset of event frames that represent the source batch phase-level recipe. 
    
The name field of the operation-level event frames is the operation name read from the data source. The following table shows how the source batch properties map to event frame attributes:
    
| Source Operation Property | Event Frame Field | Reference Element |
|--|--|--|
| Operation Name | Name |  |
| Start Time | Start Time |  |
| End Time | End Time |  |
| Unit |  | Unit |

By default, the interface records recipe value and report events in event frame attributes. For these events, the attribute name is assigned from the [DESCRIPTION] column, the value from the source [PVALUE] column, and units of measure from the [EU] column. 

## Phase
    
The interface creates a phase-level event frame for each phase read from the data source. Each phase-level event frame is created as a child of an operation-level event frame and contains the subset of event frames that represent the source batch phase states-level recipe. 

The name field of the phase-level event frame contains the phase name read from the data source. The following table shows how the source batch properties map to event frame attributes:

| Source Phase Property | Event Frame Field | Reference Elements |
|--|--|--|
| Phase Name | Name |  |
| Start Time | Start Time |  |
| End Time | End Time |  |
| Unit |  | Unit |
| Phase Module |  | Phase Module |
    
By default, the interface records recipe value and report events in event frame attributes. For these events, the attribute name is assigned from the [DESCRIPTION] column, the value from the source [PVALUE] column, and units of measure from the [EU] column. 

## Phase State

The interface creates a phase state-level event frame for each phase state read from the data source. Each phase state-level event frame is created as a child of a phase-level event frame and, if so configured, can contain the subset of event frames that represent the phase steps. The start of new phase state ends the previous one, unless the new state is COMPLETE, ABORTED or STOPPED, which end the current phase state without beginning a new one. These phase states have a zero-duration time frame. 

The name field of the phase state event frames reflects an actual source recipe phase state name. Below is the mapping of source phase state to event frame fields and attributes:

| Source Phase State Property | Event Frame Field | Referenced Element |
|--|--|--|
| Phase State | Name |  |
| Start Time | Start Time |  |
| End Time | End Time |  |
| Unit |  | Unit |
| Operation Module |  | Operation Module |
| Phase Module | Phase Module | Phase Step |

<!-- WonderWare content -->

Phase steps are not S88-compliant and support varies among BES vendors. AVEVA Batch Management does not support phase steps. Phase steps are created beneath the first phase state sub-batch named "RUNNING", regardless of whether the parent phase state is ended. The name of phase step start and stop events is read from the data source [DESCRIPT] column. The triggering event is "Report". Phase steps do not trigger the creation of parent-level events if the parent phase is not found. If the phase step was not closed by an appropriate closing event, the interface closes it by the end of its parent operation-level event frame. Zero-duration phase steps are ignored.
