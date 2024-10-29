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
@enduml
