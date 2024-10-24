# Risk assesment 

```plantuml

@startuml 1

' analyse for cartesian robot 
start

:Hazard: Cartesian Machine;
:Risk: Unexpected movements;
:Consequence: Hitting by the machine;
:Risk grading: medium;
:Controls to minimize risks
1. Put a warning sticker on the machine 
2. Place the Cartesian robot in a safety cabinet;
stop

@enduml

@startuml 2

' Analyse for clamping system 

start
:Hazard: Clamping mechanism;
:Risk: Danger of pinching;
:Consequence: Injuries from pinching (e.g., fingers, hands);
:Risk grading: Medium;
:Controls to minimize risks
1. Install safety guards around the clamping area
2. Add warning signs about the pinch hazard
3. Ensure proper training for all operators
4. Implement an emergency stop button near the clamping mechanism;
stop

@enduml

@startuml 3

' Flowchart voor gevaren van gereedschap

start
:Hazard: 
Tool;
:Risks:
- Flying metal parts
- Heat and sparks
- Intensive noise;

:1: Injury to skin or eyes from flying metal parts
2: Burns or fire hazards from heat and sparks
3: Hearing damage from loud noise;

:Risk grading: Medium;

:Controls to minimize risks
1. Use protective equipment (e.g., safety goggles, gloves)
2. Install heat shields and spark 
3. Place machine in safety cabinet
4. Provide ear protection for workers
5. Clearly mark hazardous zones and use warning signs
6. Regular maintenance and inspection of tools;

stop

@enduml
