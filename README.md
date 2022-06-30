# petclinic-uml

Object Oriented Software Endineering: OOA and OOD of the Spring Petclinc using UML. 

## What is it?

That Demo Application is used here as "Rosetta Stone" for Migration to other OOP Web Application Frameworks like 

* Jakarta EE (Java)
* Symfony (PHP)
* Django (Python) 
* Flask, SQLalchemy (Python)
* Fluid,Extbase (TYPO3-CMS, PHP)

This OOA and OOD should extract and divide the functional Requirements from the nonfunctional Requirements 
of the Frameworks.

* Most of the Frameworks compared here use Model-2 MVC Pattern for the Web/Presentation-Tier 
but Jakarta EE uses JSF (Java Server Faces), a Component Based Web/Presentation-Tier.
* This Specification should also serve as Specification for non-Web Frontends like Qt (C++, Python) etc.

## Why Petclinic? 

* The Domain Classes show all relationships like one-to-many (1:n), many-to-one (n:1) and many-to-many (n:m)
* It is simple enough but yet it shows more than just the CRUD Use Cases (Create, Read, Update, Delete) of most Demos and Training Examples. 
* You can think of it as smallest complete Web App with the usual things to solve. 

## Functional Requirements 

Object Oriented Design

## Petclinic

### Petclinic Domain Class Modell
![Figure Domain Class Modell](uml/Domain_Class_Modell-Petclinic_Domain_Class_Modell.png)

### Petclinic Use Case Diagram

![Figure Uses Cases Petclinic](uml/Use_Cases-Petclinic_Use_Case_Diagram.png)

## PetType 

### PetType Use Case Diagram

PetType Use Cases
* a
* b
* c

![Figure Uses Cases PetType](uml/pettype/PetType__UseCases-PetType_Use_Case_Diagram.png)
### PetType State Diagram
![Figure Uses Cases PetType](uml/pettype/PetType__StateEngine-PetType_State_Diagram.png)


## Specialty

### Specialty Use Case Diagram

Specialty Use Cases
* Specialty.list
* Specialty.search
* Specialty.addNew
* Specialty.edit
* Specialty.delete

![Figure Uses Cases Specialty](uml/specialty/Specialty__UseCases-Specialty_Use_Case_Diagram.png)

### Specialty State Diagram

Specialty States 
* SPECIALTY_LIST
* SPECIALTY_NEW
* SPECIALTY_DELETE
* SPECIALTY_LIST2
* SPECIALTY_LIST3
* SPECIALTY_LIST4

![Figure Uses Cases Specialty](uml/specialty/Specialty__StateEngine-Specialty_State_Diagram.png)


## Vetinarian

### Vetinarian Use Case Diagram

Vetinarian Use Cases
* a
* b
* c

![Figure Uses Cases Vet](uml/vet/Vet__UseCases-Vetinarian_Use_Case_Diagram.png)

### Vetinarian State Diagram

Vetinarian States
* a
* b
* c

![Figure Uses Cases Vet](uml/vet/Vet__StateEngine-Vetinarian_State_Diagram.png)


## Owner

### Owner Use Cases

Owner Use Cases
* a
* b
* c

![Figure Uses Cases Owner](uml/owner/Owner__UseCases-Owner_Use_Case_Diagram.png)
### Owner State Diagram
![Figure Uses Cases Owner](uml/owner/Owner__StateEngine-Owner_State_Diagram.png)
### Owner State Diagram without Pet and Visits
![Figure Uses Cases Owner](uml/owner/Owner__StateEngine__without_details-Owner_State_Diagram_without_Pet_and_Visits.png)
### Owner State Diagram of Pet and Visits
![Figure Uses Cases Owner](uml/owner/Owner__StateEngine__details-Owner_State_Diagram_of_Pet_and_Visits.png)