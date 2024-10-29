# System process


```plantuml
@startuml
title Burr cleaning process in a cartesian robot

start

:Gear preparation;

if (Manual or automatic placement?) then (Manual)
    :Operator places the gear;
else (Automatic)
repeat
    :Conveyor position gear;

 :Check gear position; 
repeat while (Gear in position?) is (no)
->yes;
endif

:Start clamping system;

repeat
:Acquire gear parameters through vision;
:Save data in database;
:Send initial parameters to the controller;
:Configure cleaning parameters;
:Start burr cleaning process;
:Verify cleaning quality with vision system;
repeat while (Satisfactory cleaning?) is (no)
->yes;
@enduml
