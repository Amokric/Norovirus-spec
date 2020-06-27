# REQ-purpose
The goal of this project is to develop a reasonable replication of the Norovirus Model from the paper [NOROVIRUS OUTBREAKS: USING AGENT-BASED MODELING TO EVALUATE SCHOOL POLICIES](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=7822182).

The paper examines the transmission of the virus among primary school classrooms, evaluating policies to reduce the number of children who become infected. 

The model focuses on the daily activities that allow for students’ exposure to the virus including classroom activities and lunch.

To control the transmission, two policies were implemented to limit the amount of student-student interaction. The results demonstrated that implementation of either policy helps reduce the number of students who become ill and that the sooner the policy is implemented the shorter the duration of the outbreak.

  ## Structure
  

- [[ REQ-SUp]] - The setup. This will initialise the model with all the details needed to run the simulation, it will include the generation of the students, the student network and for how long the simulation should run for.


# SPC-paper
partof: REQ-purpose
###
# Norovrius Outbreaks: Using Agent-Based Modellig to Evaluate School Policies - Paper 2016

## About paper :
Norovirus is a contagious gastrointestinal illness which causes nausea, vomiting, diarrhoea and flu-type symptoms which spread through water, food and contaminated surfaces with the virus.

In the paper, two policies were implemented in order to reduce the number of children who become infected. The model follows the daily activities that allow for students' exposure to the virus including, classroom activities and lunch/recess.

## Methodology Overview:
Model focuses on the basic SEIR model, allowing students' health states to be susceptible, exposed, infectious, or recovered. The model follows three routes of how the students can be exposed to the virus:

- Seating arrangements (neighbours)
- Daily group activities (randomly pairing students to work in groups of 2, 3 or 4)
- Social interactions between students during lunch and recess


## Methodology - Initialising the Model:
Runs a standard school week, students go to school for five days and then are home for two.

During the five days at school, students have the chance to become infected with virus by their neighbours (each student has an assigned seat), classroom group work, and during their lunch or recess friends.

Neighbours and group members have a 10% chance of becoming sick. However, students in the infected students' friendship network have a slightly increased probability of being infected, 12%.

Students 'sick'/'healthy' status is updated at the end of each day, as well as, there absentee status. If student has 'sick' status for 2 days then they are removed from school temporarily.

Initial model parameters:

- Classroom size = 21 students
- Number of Classrooms = 6
- Risk of Infection = 50%
- Illness Rate (Post Infection) = 10%
- Incubation period = 2 days
- Symptomatic (Isolation) period = 3 days
- School Days per Week = 5 days
- Weekend Days per Week = 2 days

### Policy 1
If classroom reaches an absenteeism rate (AR) higher than the defined limit, then policy is implemented.
Example:
An AR of 10% for a classroom of 21 students would be 2 students absent when the policy is implemented; where AR of 40% would require 8 students to be absent before implementing the policy.
This policy stops group work between students, thus removing a route of exposure.

### Policy 2
Suspends group activities within the class and grade-wide lunches. For policy to be implemented the students would be required to eat in their classrooms to minimise contamination from outside their classroom.
After this the only way of spread is through assigned seat neighbours because the students no longer interact with their group work or friendship networks.