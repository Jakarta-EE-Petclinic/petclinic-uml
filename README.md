# petclinic-uml

Object Oriented Software Engineering: OOA and OOD of the Spring Petclinc using UML. 

## What is it?

These Demo Application are planned to be a "Rosetta Stone" for compare OOP Web Application Frameworks like 

* [Jakarta EE (Java)](https://jakarta-ee-petclinic.github.io/petclinic-jakartaee/)
* [Java EE 7](https://jakarta-ee-petclinic.github.io/petclinic-javaee7/)
* [Java EE 6](https://jakarta-ee-petclinic.github.io/petclinic-jee6/)
* [Symfony (PHP)](https://jakarta-ee-petclinic.github.io/petclinic_symfony/)
* [Django (Python)](https://jakarta-ee-petclinic.github.io/petclinic_django/)
* [Flask with SQLalchemy (Python)](https://jakarta-ee-petclinic.github.io/petclinic_flask/)
* Fluid,Extbase (TYPO3-CMS, PHP)

This OOA and OOD should extract and divide the functional Requirements from the nonfunctional Requirements 
of the Frameworks.

* Most of the Frameworks compared here use Model-2 MVC Pattern for the Web/Presentation-Tier 
but Jakarta EE uses JSF (Java Server Faces), a Component Based Web/Presentation-Tier. 

This Specification should also serve as Specification for non-Web Frontends like:
* [Qt (C++)](https://jakarta-ee-petclinic.github.io/petclinic-qt5/)
* [Qt (Python)](https://jakarta-ee-petclinic.github.io/petclinic-pyqt/)
* [Java Swing](https://jakarta-ee-petclinic.github.io/petclinic-java-swing/)

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

| PetType Use Cases |
|-------------------|
| PetType.list      |
| PetType.search    |
| PetType.addNew    |
| PetType.edit      |
| PetType.delete    | 

![Figure Uses Cases PetType](uml/pettype/PetType__UseCases-PetType_Use_Case_Diagram.png)
### PetType State Diagram

| PetType States |
|----------------|
| PETTYPE_LIST   |
| PETTYPE_NEW    |
| PETTYPE_EDIT   |
| PETTYPE_DELETE |
| PETTYPE_LIST2  |
| PETTYPE_LIST3  |
| PETTYPE_LIST4  |


| Actions                          | Frontend to View              | View to Backend (DB) | outcome             | precondition                   | postcondition                                |
|----------------------------------|-------------------------------|----------------------|---------------------|--------------------------------|----------------------------------------------|
| PetType.button_addNew_dialog()   | x                             |                      | change state        | PETTYPE_LIST                   | PETTYPE_NEW                                  |
| PetType.button_edit_dialog()     | x                             |                      | change state        | PETTYPE_LIST                   | PETTYPE_EDIT                                 |
| PetType.button_delete_dialog()   | x                             |                      | change state        | PETTYPE_LIST                   | PETTYPE_DELETE                               |
| PetType.cancel_and_back()        | x                             |                      | change state        | PETTYPE_NEW                    | PETTYPE_LIST                                 |
| PetType.cancel_and_back()        | x                             |                      | change state        | PETTYPE_EDIT                   | PETTYPE_LIST                                 |
| PetType.cancel_and_back()        | x                             |                      | change state        | PETTYPE_DELETE                 | PETTYPE_LIST                                 |
| PetType.button_addNew_perform()  | x, calls: PetType.db_addNew() |                      | if OK: change state | PETTYPE_NEW                    | PETTYPE_LIST                                 |
| PetType.db_addNew()              |                               | x                    | OK                  | length(list(PetType)) = n      | length(list(PetType)) = n+1                  |
| PetType.db_addNew()              |                               | x                    | not OK, invalid     | length(list(PetType)) = n      | display cause as flash message               |
| PetType.button_update_perform()  | x, calls: PetType.db_update() |                      | if OK: change state | PETTYPE_EDIT                   | PETTYPE_LIST                                 |
| PetType.db_update()              |                               | x                    | OK                  | length(list(PetType)) = n > 0  | length(list(PetType)) = n; 1 element changed |
| PetType.db_update()              |                               | x                    | not OK, invalid     | length(list(PetType)) = n >= 0 | display cause as flash message               |
| PetType.button_delete_perform()  | x, calls: PetType.db_delete() |                      | if OK: change state | PETTYPE_DELETE                 | PETTYPE_LIST                                 |
| PetType.db_delete()              |                               | x                    | OK                  | length(list(PetType)) = n > 0  | length(list(PetType)) = n-1                  |
| PetType.db_delete()              |                               | x                    | not OK, invalid     | length(list(PetType)) = n >= 0 | display cause as flash message               |

![Figure Uses Cases PetType](uml/pettype/PetType__StateEngine-PetType_State_Diagram.png)


## Specialty

### Specialty Use Case Diagram

| Specialty Use Cases |
|---------------------|
| Specialty.list      |
| Specialty.search    |    
| Specialty.addNew    |
| Specialty.edit      |
| Specialty.delete    |

![Figure Uses Cases Specialty](uml/specialty/Specialty__UseCases-Specialty_Use_Case_Diagram.png)

### Specialty State Diagram

| Specialty States | 
|------------------|
| SPECIALTY_LIST   |
| SPECIALTY_NEW    |
| SPECIALTY_EDIT   |  
| SPECIALTY_DELETE |    
| SPECIALTY_LIST2  |
| SPECIALTY_LIST3  |
| SPECIALTY_LIST4  |

| Actions  | Frontend to View | View to Backend (DB) |
|----------|------------------|----------------------|
| asdf()   | x                |                      |
| fdsfsd() |                  | x                    |

| Actions                            | Frontend to View                | View to Backend (DB) | outcome             | precondition                     | postcondition                                  |
|------------------------------------|---------------------------------|----------------------|---------------------|----------------------------------|------------------------------------------------|
| Specialty.button_addNew_dialog()   | x                               |                      | change state        | SPECIALTY_LIST                   | SPECIALTY_NEW                                  |
| Specialty.button_edit_dialog()     | x                               |                      | change state        | SPECIALTY_LIST                   | SPECIALTY_EDIT                                 |
| Specialty.button_delete_dialog()   | x                               |                      | change state        | SPECIALTY_LIST                   | SPECIALTY_DELETE                               |
| Specialty.cancel_and_back()        | x                               |                      | change state        | SPECIALTY_NEW                    | SPECIALTY_LIST                                 |
| Specialty.cancel_and_back()        | x                               |                      | change state        | SPECIALTY_EDIT                   | SPECIALTY_LIST                                 |
| Specialty.cancel_and_back()        | x                               |                      | change state        | SPECIALTY_DELETE                 | SPECIALTY_LIST                                 |
| Specialty.button_addNew_perform()  | x, calls: Specialty.db_addNew() |                      | if OK: change state | SPECIALTY_NEW                    | SPECIALTY_LIST                                 |
| Specialty.db_addNew()              |                                 | x                    | OK                  | length(list(Specialty)) = n      | length(list(Specialty)) = n+1                  |
| Specialty.db_addNew()              |                                 | x                    | not OK, invalid     | length(list(Specialty)) = n      | display cause as flash message                 |
| Specialty.button_update_perform()  | x, calls: Specialty.db_update() |                      | if OK: change state | SPECIALTY_EDIT                   | SPECIALTY_LIST                                 |
| Specialty.db_update()              |                                 | x                    | OK                  | length(list(Specialty)) = n > 0  | length(list(Specialty)) = n; 1 element changed |
| Specialty.db_update()              |                                 | x                    | not OK, invalid     | length(list(Specialty)) = n >= 0 | display cause as flash message                 |
| Specialty.button_delete_perform()  | x, calls: Specialty.db_delete() |                      | if OK: change state | SPECIALTY_DELETE                 | SPECIALTY_LIST                                 |
| Specialty.db_delete()              |                                 | x                    | OK                  | length(list(Specialty)) = n > 0  | length(list(Specialty)) = n-1                  |
| Specialty.db_delete()              |                                 | x                    | not OK, invalid     | length(list(Specialty)) = n >= 0 | display cause as flash message                 |

![Figure Uses Cases Specialty](uml/specialty/Specialty__StateEngine-Specialty_State_Diagram.png)


## Vetinarian

### Vetinarian Use Case Diagram

| Vetinarian Use Cases |
|----------------------|
| Vet.list             |
| Vet.search           |
| Vet.addNew           |
| Vet.edit             |
| Vet.delete           |

![Figure Uses Cases Vet](uml/vet/Vet__UseCases-Vetinarian_Use_Case_Diagram.png)

### Vetinarian State Diagram

| Vetinarian States |
|-------------------|
| VET_LIST          |
| VET_NEW           |
| VET_EDIT          |
| VET_DELETE        |      
| VET_LIST2         |
| VET_LIST3         |  
| VET_LIST4         |  

| Actions                            | Frontend to View                 | View to Backend (DB) | outcome             | precondition                      | postcondition                                   |
|------------------------------------|----------------------------------|----------------------|---------------------|-----------------------------------|-------------------------------------------------|
| Vetinarian.button_addNew_dialog()  | x                                |                      | change state        | VET_LIST                          | VET_NEW                                         |
| Vetinarian.button_edit_dialog()    | x                                |                      | change state        | VET_LIST                          | VET_EDIT                                        |
| Vetinarian.button_delete_dialog()  | x                                |                      | change state        | VET_LIST                          | VET_DELETE                                      |
| Vetinarian.cancel_and_back()       | x                                |                      | change state        | VET_NEW                           | VET_LIST                                        |
| Vetinarian.cancel_and_back()       | x                                |                      | change state        | VET_EDIT                          | VET_LIST                                        |
| Vetinarian.cancel_and_back()       | x                                |                      | change state        | VET_DELETE                        | VET_LIST                                        |
| Vetinarian.button_addNew_perform() | x, calls: Vetinarian.db_addNew() |                      | if OK: change state | VET_NEW                           | VET_LIST                                        |
| Vetinarian.db_addNew()             |                                  | x                    | OK                  | length(list(Vetinarian)) = n      | length(list(Vetinarian)) = n+1                  |
| Vetinarian.db_addNew()             |                                  | x                    | not OK, invalid     | length(list(Vetinarian)) = n      | display cause as flash message                  |
| Vetinarian.button_update_perform() | x, calls: Vetinarian.db_update() |                      | if OK: change state | VET_EDIT                          | VET_LIST                                        |
| Vetinarian.db_update()             |                                  | x                    | OK                  | length(list(Vetinarian)) = n > 0  | length(list(Vetinarian)) = n; 1 element changed |
| Vetinarian.db_update()             |                                  | x                    | not OK, invalid     | length(list(Vetinarian)) = n >= 0 | display cause as flash message                  |
| Vetinarian.button_delete_perform() | x, calls: Vetinarian.db_delete() |                      | if OK: change state | VET_DELETE                        | VET_LIST                                        |
| Vetinarian.db_delete()             |                                  | x                    | OK                  | length(list(Vetinarian)) = n > 0  | length(list(Vetinarian)) = n-1                  |
| Vetinarian.db_delete()             |                                  | x                    | not OK, invalid     | length(list(Vetinarian)) = n >= 0 | display cause as flash message                  |

![Figure Uses Cases Vet](uml/vet/Vet__StateEngine-Vetinarian_State_Diagram.png)

## Owner

### Owner Use Cases

| Owner Use Cases        |
|------------------------|
| Owner.list             |
| Owner.search           |
| Owner.addNew           |
| Owner.edit             |
| Owner.delete           |
| Owner.Pet.list         |
| Owner.Pet.addNew       |
| Owner.Pet.edit         |
| Owner.Pet.delete       |
| Owner.Pet.Visit.list   |
| Owner.Pet.Visit.addNew |
| Owner.Pet.Visit.edit   |
| Owner.Pet.Visit.delete |

![Figure Uses Cases Owner](uml/owner/Owner__UseCases-Owner_Use_Case_Diagram.png)
### Owner State Diagram

| Owner States           |
|------------------------|
| OWNER_LIST             |       
| OWNER_NEW              |      
| OWNER_DETAILS          |      
| OWNER_EDIT             |      
| OWNER_DELETE           |      
| OWNER_PET_NEW          |      
| OWNER_PET_EDIT         |      
| OWNER_PET_DELETE       |     
| OWNER_PET_VISIT_NEW    |   
| OWNER_PET_VISIT_EDIT   |  
| OWNER_PET_VISIT_DELETE |
| OWNER_PET_VISIT_NEW    | 
| OWNER_PET_VISIT_EDIT   | 
| OWNER_PET_VISIT_DELETE |


| Actions  | Frontend to View | View to Backend (DB) |
|----------|------------------|----------------------|
| asdf()   | x                |                      |
| fdsfsd() |                  | x                    |

![Figure Uses Cases Owner](uml/owner/Owner__StateEngine-Owner_State_Diagram.png)
### Owner State Diagram without Pet and Visits
![Figure Uses Cases Owner](uml/owner/Owner__StateEngine__without_details-Owner_State_Diagram_without_Pet_and_Visits.png)
### Owner State Diagram of Pet and Visits
![Figure Uses Cases Owner](uml/owner/Owner__StateEngine__details-Owner_State_Diagram_of_Pet_and_Visits.png)

## Imprint
* [(c) 2022 Thomas Woehlke](https://github.com/thomaswoehlke)
* [This Document](https://jakarta-ee-petclinic.github.io/petclinic-uml/)
* [github repository](https://github.com/Jakarta-EE-Petclinic/petclinic-uml)