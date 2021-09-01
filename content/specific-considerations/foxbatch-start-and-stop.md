---
uid: FoxBatchStartAndStop
---

# FoxBatch Start and Stop


**I wasn't sure how to do this in GitHub (still a newbie), but we need a new subsection under the start and stop events section (https://osisoft-dev.zoominsoftware.io/bundle/pi-interface-wonderware-inbatch/page/specific-considerations/start-and-stop-events.html) for FOXBatch start and stops.**

This subsection should still use tables to represent the fox batch start and stops denoted here: 
Batch Open (First Action Code 210)
  UnitProcedure open ( Action Code 210)
    Operation Start ( First Operation name under UnitProcedure Action Code 228 or 230)
      Phase Start ( Action Code 228 or 230)
        Phasestate (phaseStateRun_(Action Code 228), 
          phaseStateHeld_( Action Code 230),
          phaseStateAborted_( Action Code 233),
        phaseStateDone_( Action Code 234))
      Phase Close ( Action Code 233 or 234)
    Operation Close (Last Count of Operation Name under UnitProcedure Action Code 233 or 234)
  UnitProcedure Close ( Action Code 211)
Batch Close (Last UnitProcedure not open since batch start Action Code 211)


I guess we also need a short introduction that states something like: 
  Customers that still require connectivity to a legacy Foxboro Batch system can enable the /FOXBATCH switch in the Operational Settings section of PI Event Frames Interface Manager. This setting updates the start and stop events to be compatable with a Foxboro Batch system. 
