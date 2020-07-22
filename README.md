## "NOROVIRUS OUTBREAKS: USING AGENT-BASED MODELING TO EVALUATE SCHOOL POLICIES"

### Introduction (What are we trying to model?)
Modelling the transmission of the Norovirus among elementary school classrooms, evaluating policies to reduce the number of children who become infected. The model will focus on the daily activities that allow for students’ exposure to the virus including classroom activities and lunch/recess.

### Extraction Process

**Methodology - Initialising the Model:**

Runs a standard school week, students go to school for five days and then are home for two. 

During the five days at school, students have the chance to become infected with virus by their neighbours (each student has an assigned seat), classroom group work, and during their lunch or recess friends. 

Neighbours and group members have a **10%** chance of becoming sick. However, students in the infected students' friendship network have a slightly increased probability of being infected, **12%**.

The model focuses on the basic SEIR model, allowing students' health status to be susceptible, exposed, infectious, or recovered. However, later on it is stated that the students will have specific statuses applied to them depending on their state of health: 
"The students ‘sick’/ ‘healthy’ status is updated at the end of each day, as well as, there absentee status"
So we can assume that the students statuses will be:
- Healthy
- Sick
- Absent
- Recovered 

Absent is linked to the students who are going through isolation period. 

**Policy 1**

If classroom reaches an absenteeism rate (AR) higher than the defined limit, then policy is implemented. 

Example:
An AR of 10% for a classroom of 21 students would be 2 students absent when the policy is implemented; where AR of 40% would require 8 students to be absent before implementing the policy.

This policy stops group work between students, thus removing a route of exposure. 

**Policy 2**

Suspends group activities within the class and grade-wide lunches. For policy to be implemented the students would be required to eat in their classrooms to minimise contamination from outside their classroom.  

After this the only way of spread is through assigned seat neighbours because the students no longer interact with their group work or friendship networks. 

### Initialising the model
In the model they run a standard school week, students go to school for five days and then are home for two. The model only includes exposure in the school and not at home or public venues -> only focus  5/7 days and during school time. During the 5 days, the students have a chance of being infected with the virus by their neighbours, students they connect with for group work, and their lunch and recess friends. 

Students 'sick'/'healthy' status is updated at the end of each day, as well as their absentee status. If a student has 'sick' status for 2 days then they are removed from school temporarily. But when they are home they are not considered to spread there, as the model only focuses on school spread. 


