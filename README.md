# Hospital Simulator

## Caution ##

Unfortunately, I had to remove the code from this repo, as I was requested by the company for which I applied.
I want to make it clear to all candidates that I was not forced to do this, legally or morally and neither are you. 
I know how it is not to have time for side projects to build up a personal portfolio and being able to add the code to Github is a perfect opportunity to make the most out of an interview, even if unsuccessful.

Feel free to contact me if you have any questions about the solution.

### Context

This is an interview project, it does not have any utility otherwise.

### Problem description

You were asked by a doctor friend to prepare for her a “Hospital simulator”, which can
simulate the future patients’ state, based on their current state and a list of drugs they take.
Patients can have one of these states:
- F: Fever
- H: Healthy
- D: Diabetes
- T: Tuberculosis
- X: Dead

In the “Hospital simulator” drugs are provided to all patients. It is not possible to target a
specific patient. This is the list of available drugs:
- As: Aspirin
- An: Antibiotic
- I: Insulin
- P: Paracetamol

Drugs can change patients’ states. They can cure, cause side effects or even kill a patient if
not properly prescribed.
Drugs effects are described by the following rules:
- Aspirin cures Fever;
- Antibiotic cures Tuberculosis;
- Insulin prevents diabetic subject from dying, does not cure Diabetes;
- If insulin is mixed with antibiotic, healthy people catch Fever;
- Paracetamol cures Fever;
- Paracetamol kills subject if mixed with aspirin;

### Input

Parameter 1
 - List of patients' health status codes, separated by a comma. e.g. “D,F,F” means we have 3
patients, one with diabetes and two with fever.

Parameter 2
 - List of drugs codes, separated by a comma, e.g. “As,I” means patients will be treated with
Aspirin and Insulin.

### Output

The result should be sent to stdout.

It should be a comma separated string with number of patients with a given state, following
the format:

```F:NP,H:NP,D:NP,T:NP,X:NP```

Where:
- F, H, D, T, X are patients’ health status codes;
- NP is a number of patients for a given state;
- E.g. “F:0,H:2,D:0,T:0,X:1” means there are two healthy patients and one that is dead.

### Examples

Example 1
- Input: “D,D” “”
- Output: “F:0,H:0,D:0,T:0,X:2” (diabetic patients die without insulin)
- ```$ java -cp hospital-simulator.jar com.horatiuj.hospital.Application D,D```
- ```F:0,H:0,D:0,T:0,X:2```

Example 2 
- Input: “F” “P”
- Output: “F:0,H:1,D:0,T:0,X:0” (paracetamol cures fever)
- ```$ java -cp hospital-simulator.jar com.horatiuj.hospital.Application F P```
- ```F:0,H:1,D:0,T:0,X:0```
