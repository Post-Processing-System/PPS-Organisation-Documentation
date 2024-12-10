# TEST


```plantuml




@startuml
[*] --> CYLINDER.INITIALIZE

CYLINDER.INITIALIZE : Initializing process...
CYLINDER.INITIALIZE --> CYLINDER.PLUS75 : After Timer > 12 seconds, Home operation done

CYLINDER.PLUS75 : Moving to position +75
CYLINDER.PLUS75 --> CYLINDER.UITVOER : After Timer > 50ms, move to next position

CYLINDER.PLUS225 : Moving to position +225
CYLINDER.PLUS225 --> CYLINDER.UITVOER : After Timer > 50ms, move to next position

CYLINDER.MIN150 : Moving to position -150
CYLINDER.MIN150 --> CYLINDER.UITVOER : After Timer > 50ms, move to next position

CYLINDER.PLUS150 : Moving to position +150
CYLINDER.PLUS150 --> CYLINDER.UITVOER : After Timer > 50ms, move to next position

CYLINDER.MIN75 : Moving to position -75
CYLINDER.MIN75 --> CYLINDER.UITVOER : After Timer > 50ms, move to next position

CYLINDER.UITVOER : Moving to the final position
CYLINDER.UITVOER --> CYLINDER.WACHT : After Timer > 5 seconds, wait before next move

CYLINDER.SLEEP : Waiting for next move (after multiple steps)
CYLINDER.SLEEP --> CYLINDER.WACHT : After Timer > 500ms, move to next state

CYLINDER.WACHT : Waiting for next step to trigger
CYLINDER.WACHT --> CYLINDER.PLUS225 : Step 1
CYLINDER.WACHT --> CYLINDER.MIN150 : Step 2
CYLINDER.WACHT --> CYLINDER.SLEEP : Step 3
CYLINDER.WACHT --> CYLINDER.PLUS150 : Step 4
CYLINDER.WACHT --> CYLINDER.MIN150 : Step 5
CYLINDER.WACHT --> CYLINDER.PLUS75 : Step 6
CYLINDER.WACHT --> CYLINDER.MIN150 : Step 7
CYLINDER.WACHT --> CYLINDER.PLUS75 : Step 8
CYLINDER.WACHT --> CYLINDER.MIN75 : Step 9
CYLINDER.WACHT --> CYLINDER.MIN75 : Step 10
CYLINDER.WACHT --> CYLINDER.POWER_OFF : Step 11, disable power

CYLINDER.POWER_OFF : Powering off the system
CYLINDER.POWER_OFF --> [*] : End of process

@enduml

@startuml

rectangle "Power Supply" as PowerSupply
rectangle "AC to DC Converter\nNDR-120-24" as AC_DC_Converter
rectangle "PLC" as PLC
rectangle "Servo Driver\nCMMT-ST-EC" as ServoDriver
rectangle "Stepper Motor\nEMMS-ST-42-S-SE-G2" as StepperMotor
rectangle "Axial Kit\nEAMM-A-V32-42A" as AxialKit1
rectangle "Toothed Belt Axes\nELGG-TB-KF-45-300" as ToothedBeltAxes
rectangle "Laptop" as Laptop
rectangle "Encoder" as Encoder

Laptop --> PLC : Ethernet
PowerSupply --> AC_DC_Converter : 230V
AC_DC_Converter --> PLC : 24V
AC_DC_Converter --> ServoDriver : 24V
PLC --> ServoDriver : Ethernet

ServoDriver --> StepperMotor : X8
ServoDriver --> AxialKit1 : X2

StepperMotor --> Encoder
StepperMotor --> AxialKit1 : Mechanical Connection
AxialKit1 --> ToothedBeltAxes : Mechanical Connection

@enduml



@startuml 
title Risicoanalyse

package "Risico's" {
    [Mechanische Verwondingen] 
    note right: Waarschijnlijkheid: 3 (mogelijk)\nErnst: 4 (ernstig)\nRisicoscore: 12\nBeheersmaatregelen: Veiligheidsbescherming, training.

    [Inademingsgevaar] 
    note right: Waarschijnlijkheid: 2 (weinig waarschijnlijk)\nErnst: 3 (matig)\nRisicoscore: 6\nBeheersmaatregelen: Stofafzuiging, ademhalingsmaskers.

    [Geluidsoverlast] 
    note right: Waarschijnlijkheid: 3 (mogelijk)\nErnst: 2 (licht)\nRisicoscore: 6\nBeheersmaatregelen: Geluidsisolatie, gehoorbescherming.

    [Ongevallen met de robot] 
    note right: Waarschijnlijkheid: 2 (weinig waarschijnlijk)\nErnst: 4 (ernstig)\nRisicoscore: 8\nBeheersmaatregelen: Afschermingen, veiligheidsinstructies.

    [Elektrocutie of brand] 
    note right: Waarschijnlijkheid: 1 (zeer onwaarschijnlijk)\nErnst: 5 (catastrofaal)\nRisicoscore: 5\nBeheersmaatregelen: Regelmatige inspecties van elektrische systemen.

    [Ergonomische risico's] 
    note right: Waarschijnlijkheid: 2 (weinig waarschijnlijk)\nErnst: 3 (matig)\nRisicoscore: 6\nBeheersmaatregelen: Ergonomische werkplekinrichting.

}

@enduml