# Ex.No: 8  Logic Programming –  Medical Diagnosis Expert System
### DATE:16.09.25                                                                        
### REGISTER NUMBER : 212222060255
### AIM: 
Write a Prolog program to build a medical Diagnosis Expert System.
###  Algorithm:
1. Start the program.
2. Write the rules for each diseases.
3. If patient have mumps then symptoms are fever and swollen glands.
4. If patient have cough, sneeze and running nose then disease is measles.
5. if patient have symptoms headache ,sneezing ,sore_throat, runny_nose and  chills then disease is common cold.
6. Define rules for all disease.
7. Call the predicates and Collect the symptoms of Patient and give the hypothesis of disease.
        

### Program:
```
% Medical Diagnosis Expert System

% Disease rules
hypothesis(Patient, mumps) :-
    symptom(Patient, fever),
    symptom(Patient, swollen_glands).

hypothesis(Patient, german_measles) :-
    symptom(Patient, fever),
    symptom(Patient, headache),
    symptom(Patient, runny_nose),
    symptom(Patient, rash).

hypothesis(Patient, flu) :-
    symptom(Patient, fever),
    symptom(Patient, headache),
    symptom(Patient, body_ache),
    symptom(Patient, conjunctivitis),
    symptom(Patient, chills),
    symptom(Patient, sore_throat),
    symptom(Patient, runny_nose),
    symptom(Patient, cough).

hypothesis(Patient, common_cold) :-
    symptom(Patient, headache),
    symptom(Patient, sneezing),
    symptom(Patient, sore_throat),
    symptom(Patient, runny_nose),
    symptom(Patient, chills).

hypothesis(Patient, chicken_pox) :-
    symptom(Patient, fever),
    symptom(Patient, chills),
    symptom(Patient, body_ache),
    symptom(Patient, rash).

hypothesis(Patient, measles) :-
    symptom(Patient, cough),
    symptom(Patient, sneezing),
    symptom(Patient, runny_nose).

% Sample patient symptoms
symptom(raju, headache).
symptom(raju, sneezing).
symptom(raju, sore_throat).
symptom(raju, runny_nose).
symptom(raju, chills).

% Go predicate to diagnose a patient
go :-
    write('*** MEDICAL DIAGNOSIS EXPERT SYSTEM ***'), nl,
    write('Enter patient name (end with a dot): '), nl,
    read(Patient),
    (   hypothesis(Patient, Disease)
    ->  write(Patient), write(' is likely suffering from '), write(Disease), nl
    ;   write('No disease could be diagnosed for '), write(Patient), nl
    ).

```










### Output:
<img width="454" height="316" alt="image" src="https://github.com/user-attachments/assets/c26bac92-61e8-4ad0-aafe-23f1947e2c63" />



### Result:
Thus the simple medical diagnosis system was built sucessfully.
