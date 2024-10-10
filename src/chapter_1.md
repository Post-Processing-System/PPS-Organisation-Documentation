# Chapter 1


```plantuml
@startuml Functional diagram

start

:Start;
repeat
repeat while (gear present?) is (no) not (yes)
repeat
repeat while (start pressed?) is (no) not (yes)
:start transport;
repeat
:clamp;
:check clamp;
repeat while (gear clamped?) is (no) not (yes)
:deburring;
:cleaning;
:check quality;
:defix;
if (quality ok?) then (yes)
:transport to end pos;
else (no)
:put away;
endif 
:end;
:end;

stop
@enduml

