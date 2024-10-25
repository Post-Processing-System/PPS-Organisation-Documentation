# Components and interfaces

This chapter describes the different components and how they are related to eachother.

```plantuml

@startuml
package "Operator" {
    [Operator puts gear into machine] as opPut
    [Quality control] as opQuality
    [Operator gets gear out of machine] as opGet
}

package "Base Frame" {
    [Cartesian robot] as robot
    [Tool] as tool
    [Vision system scans gear] as vision
}

package "Industrial PC" {
    [Define dimensions] as pcDimensions
    [Create travel path] as pcPath
    [Measure used force on tool] as pcForce
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



