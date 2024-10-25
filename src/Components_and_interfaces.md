# Components and interfaces

This chapter describes the different components and how they are related to eachother.

```plantuml

@startuml
package "Operator" {
    [Input machine] as opPut
    [Quality control] as opQuality
    [Output of machine] as opGet
}

package "Base Frame" {
    [Cartesian robot] as robot
    [Tool] as tool
    [Vision system] as vision
}

package "Industrial PC" {
    [Gear measurement] as pcDimensions
    [Travel path creator] as pcPath
    [Force measurements] as pcForce
}

opPut --> vision : "1.Scans gear"
vision --> pcDimensions : "2.Send dimensions"
pcDimensions --> pcPath : "Create path"
pcPath --> robot : "Deburr on path"
robot --> tool : "Start tool"
tool --> tool : "Stop tool"
tool --> pcForce : "Measure force"
pcForce --> opQuality : "Send data"
opQuality --> opGet : "Operator gets gear"

@enduml



