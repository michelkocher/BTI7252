# Infrastructure Architecture
![Infra Arch](https://github.com/jorisbaiutti/BTI7252/raw/master/02_DigitalImage/InfrastructureArchitecture.png)

## Hardware
Es wird eine Infrastruktur in einer zu definierenden Cloud aufgebaut, welche Linux Container ausführen kann. Ein möglichst ähnliches Setup ist auch auf einer Hardware (Fog-Device), welche im Gebäude steht, zu betreiben.

## Synchronisation Fog-Cloud
Zwischen dem Fog-Device und der Cloud muss eine Synchronisation erfolgen. Dies bedeutet dass Publikationen in der MQ in beide Richtungen repliziert werden und die Subskriptionen sowohl in der Fog als auch in der Cloud funktionieren.
Je nachdem welche Daten die Datenbank hält, muss diese ebenfalls repliziert werden, wobei der Primary das Fog-Device darstellt, damit das Gebäude autonom betrieben werden kann.
Die Synchronisierung/Replikation muss asynchron erfolgen können, damit bei einem Ausfall einer Komponente zwischen dem Fog und der Cloud das Fog-Device weiterlaufen kann.

## Deployment
Die sowohl auf der Cloud als auch auf dem Fog-Device laufende Software soll als Container Image (OCI-Format) vorliegen und durch eine Linux Containerlaufzeitumgebung ausgeführt werden. 
Neben Infrastruktursoftware wie der MQ laufen auch die Geschäftsanwendungen auf der selben Umgebung.

## Things Schnittstelle
Für die Things ist die MQ als Einstiegspunkt gedacht. Protokollbrücken sind ausserhalb der Kerninfrastruktur zu implementieren und dürfen diese nicht beeinflussen.

## IAM
Das IAM für natürliche Benutzer erfolgt auf Seite der Geschäftsanwendungen. Die Infrastrukturanwendungen setzen nur rudimentäre ACLs für technische Benutzer um.
