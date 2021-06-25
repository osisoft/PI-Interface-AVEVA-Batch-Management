---
uid: BIF_Introduction
---

# Introduction to [!include[interface](../includes/interface-name.md)]

<!-- Customized for  -->

PI Interface for Rockwell FactoryTalk Batch is a scan-based interface that collects batch data from the Rockwell FactoryTalk system. It reads Event Journals (EVT files) and stores that data as event frames and elements in a PI Batch Database or a PI Asset Framework (PI AF) Database. 

The interface also collects associated batch data in the form of PI Tags and PI Batch properties.

In addition to collecting batch data, the interface populates the PI Point Database. 

PI Point creation, commonly known as tag creation and event population, is controlled by using tag templates. All modules, tags, tag aliases, and health tags are automatically created on the PI server. The Interface does not use the PI API Buffering Service, because batch and tag data is already buffered by the source historian databases. To maximize performance, the interface writes events to PI tags in bulk; that is, it writes all events per interface scan.

The flow of data in the interface is unidirectional: data can only be read from the specified data source and written to the PI Server.  This interface can read data from multiple batch data sources simultaneously.  By design, the interface does not edit or delete source data.

<!-- end comment-->

<!-- Content below applies to all interfaces. -->

Two different models are used to describe batch processes: 

1. The **equipment model** describes the physical equipment necessary to create a batch. 

2. The **recipe model** describes the procedures that are performed during the execution of a recipe. 

There is no intrinsic or direct relationship between the models. With the exception of arbitration events, journal files contain only recipe model event information. 

The interface is compliant with the ISA S88.01 standard and uses the S88 process model, which is composed of the following hierarchy: 

* Procedure (recipe) 
* Unit procedures 
* Operations 
* Phases 
* Phase steps 
* Phase states 

**Note:** According to the ISA S88.01 standard, procedures and unit procedures are optional. A recipe can be composed solely of operations and phases. The PI Batch Database does not use a strict S88 approach to describe or record batch data.

The physical model is composed of the following equipment-oriented hierarchy:

* Enterprise 
* Site 
* Area 
* Process cell 
* Unit 
* Equipment module 
* Control module 

Unit procedures from the data source are mapped to PIUnitBatches. Only a single unit procedure can be active in a unit at any given time, which restricts the configuration of recipes that can be run by the batch execution system if batch data is to be captured by the interface in a reliable and meaningful way. By contrast, event frames support parallel unit procedures natively. 

You can configure the interface to create PI points and properties by defining templates, which specify the events that trigger creation, configure how the property or tag is named, and define the data to be stored. 