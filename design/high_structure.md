# REQ-model
partof: REQ-purpose
###
## Model

The requirements for the model will outline what the model must do to reach the goals defined in the REQ-purpose. 

In order to run the model and produce the results wanted, it should have:
- Agents with attributes and behaviours, this includes giving the student agents health statuses to help track disease progression.
- Agent environment
- Connections and relationships between the agents

To meet the requirements needed to run the correct implementation of the model, we will have to initialise the main conceptual objects which make up the model. The main conceptual objects for the model have their own specifications and they are listed below:

1. [[SPC-model_agents]] - Initialise agents within the model.
2. [[SPC-model_network]] - Initialise the network and set up the networks between the students
3. [[SPC-model_disease]] - Initialise the disease within the model and set up the disease progression
4. [[SPC-model_background]] - Initialise the model baseline and then setup the mitigation strategies as options within the model.

### Intervention/ Mitigation 

 It is important to understand that the interventions are different than the base model. Only after you have implemented the baseline requirements and met the specifications for generating and initialising the agents, network and disease should you implement them. As the interventions can only work when the general requirements are fulfilled.

### The Model Process

The process of this model should follow a daily route to evaluate the chances of exposure for the students. At the end of each day, we update the status of our students' health status, which is then checked again at the beginning of the next day, if our student is symptomatic, then they are sent back home and the other students proceed with their day evaluation. The image below is to provide an idea of how the model should work as it goes through each step.

![diagramFlowChat](https://user-images.githubusercontent.com/33029552/88933839-cec24200-d277-11ea-9def-c36845917ec3.jpg)


# REQ-output
partof: REQ-purpose
###
What shall be outputted from the programme after it has been run.
### Programme Report

When the program is complete it shall report:
#### 1. Stabilising results across runs:
- Outbreak duration (days), this will include data from multiple runs.
#### 2. Baseline Simulation Results:

From the data that is gathered from the runs, this will allow for specific results to be acquired for analysis. The results should include:
- Duration (days)
- Duration range (days)
- Max Absentee Rate 
- Total Number of Students Affected 
- Range of students affected across runs


### Understanding the results

According to the paper, the average duration of the simulation is 22 days.

However, the results based off of the paper, seem to contradict the logic behind the disease progression. If someone has acquired infection on a Friday, then they begin their incubation period on Saturday. On Monday the sick student would have entered the isolation period, which would conclude by Thursday, where the student will return to school healthy again. 

As mentioned in [[SPC-model_disease]], the students can only be exposed to the disease during the weekdays when they are at school. Therefore, no matter how many students acquire the infection on Friday, the disease outbreak for the simulation cannot last longer than 10 days based off of this logic.


# SPC-model_agents
partof: REQ-model
###
### Initialise agents 

The Agents of the model will need to be initialised with three user-defined attributes.

This will include:
- Their status - "Healthy", "Sick", "Absent", "Recovered"
- Days of infection
- Location - School or Home 

The model parameters can be found in: [[SPC-model_background]]

In total there should 126 agents within the model each split into six classrooms, of 21 students per class.

The location will allow for the weekdays and weekends to be initiated. When it is the weekend, the students are at the location, Home. Otherwise, they are at school.

When a student has surpassed the 2 days of incubation period they will enter the isolation period, where their location will have to be Home for 3 days. 

#### NetLogo commands of interest:

In NetLogo, the students can be segregated into six different breeds denoting the six classrooms.

1. "Sprout" 
2. "Breed"

#### PanaXea commands of interest:

You can set up a function to generate your students:
- [[.generate_students]]


To add the agents you must:

`model.schedule.agents.add(person)`

This allows agents to be added to the Schedule, which holds all simulation steppables and provides methods to progress simulation epochs.


# SPC-model_background
partof: REQ-model
###
### Initialise the model:
The Initial Model parameters include: 


<img width="374" alt="Screenshot 2020-07-30 at 01 40 34" src="https://user-images.githubusercontent.com/33029552/88867559-b6b1da80-d205-11ea-8a21-fe45d4a33e81.png">

The model will need these parameters and follow a process of evaluation to be executed.

### The intervention strategies as options within the model

The model should include mitigation strategies to limit the number of students being infected. If the rate of student reaches a certain amount these strategies should be put to place whilst the model is being run. 

1. Stop the students from doing group work 
2. Stop the students from doing group work and having lunch outside of class.

#### NetLogo commands of interest:
You can add onto the interface a Switch for each strategy if the Switch is 'on' then that strategy will do its intended purpose, prevent the students from interacting.


#### PanaXea commands of interest:
You can set up boolean attributes, for whether the student is having group work and lunch. These attributes will be set to true, however, if the absentee rate goes up then they will be set to false.


# SPC-model_disease
partof: REQ-model
###
### Initialise the disease

To initialise the disease you must change the attribute of the appropriate number of agents from susceptible to infected.

At the start of the model one "initial" agent is given the status of 'Sick'. The disease model is based on an SEIR compartment model. As the infected agent interacts with their connected neighbours or friends, they have a certain probability of infecting susceptible agents they come into contact with.

#### NetLogo commands of interest:
You can set up a global variable that has 1 as the value and then:
- "ask n-of initial-infected turtles" and set to be infected

#### PanaXea commands of interest:
You can go through the list of agents and randomly pick one agent and then set their attribute status as "sick". 
- random.choice() could be used.

### Disease progression

For the disease spread, it will depend on who the student is with. The probabilites will be evaluated more than once, as the students spend time with their seat neighbours and friends. 

#### Evaluating the chances of infection:

During the 5 days, the students have a chance of being infected with the virus by their neighbours, students they connect with for group work, and their lunch. For the spread of infection to happen, the chances will have to be evaluated. 

- Neighbours and group members: The probability of getting infected is 10%.

`p_of_infection_neighbour_groups = 0.10`


- Friend: The probability of getting infected is 12%.

`p_of_infection_friend = 0.12`


Each day you evaluate all the chances, therefore evaluating the chance of infection twice. When the students are in their classroom next to their neighbours, doing group work or at lunch. The chances of them being infected shall be evaluated. After the day finishes for the students, the status with either be updated or not, depending on if they acquired the infection throughout the day.

If the agent acquires the infection on day 1 it doesn’t affect an evaluation on day 1, their status will be updated for the next day, where they will start the day with their status now being 'sick'.


# SPC-model_network
partof: REQ-model
###
### Initialise network:

#### Baseline network

The original model uses a small-world network to model the connections between the agents. To create this network you first need to connect each agent to the other agents within the classroom in a lattice structure which is visualised below:

<img width="253" alt="Screenshot 2020-07-30 at 01 25 23" src="https://user-images.githubusercontent.com/33029552/88866767-8bc68700-d203-11ea-8ab9-aa084c16e26d.png">

There should be six versions of this network within the model initially which will then get rewired twice.


#### Creating Neighbour Networks (Rewire 1):

The first rewire requires each connection to be evaluated. If a 60% chance is successful then the connection must be rewired to a random individual within the classroom.



#### Creating Friendship Networks (Rewire 2): 

The second rewire also requires each connection to be evaluated. If a 10% chance is successful then the connection must be rewired to a random individual in the different classroom.


#### NetLogo commands of interest:

1. "create-link" 
2. "list"

#### PanaXea commands of interest:

For generating the network, you can use NetworkX, which is a Python library for studying graphs and networks. You can generate the small-world network. You can find out more here -> [Watts Strogatz Graph](https://networkx.github.io/documentation/networkx-1.10/reference/generated/networkx.generators.random_graphs.watts_strogatz_graph.html)

Graphs work by generating a set of nodes and generating the edges. The main idea is that when the graph is generated, for each node on it, it represents a student. So for each node in nodes, a student will be appended to it. Once you have the nodes initialised with the students then you generate the graph from those nodes.


# SPC-output
### Outputting

Alongside outputting the results correctly. An important process of acquiring the results from the model is understanding if the output we are getting is correct. If the duration of the simulation is going over 30 days then something is wrong. 


#### NetLogo

When running the simulation from NetLogo you need to use the tool, BehaviourSpace. An example of the interface can be seen below, where you set up the amount runs you want to do and what output you want specifically. 

<img width="492" alt="Screenshot 2020-07-30 at 20 02 22" src="https://user-images.githubusercontent.com/33029552/88963322-98002200-d29f-11ea-934e-3f381c51d4d1.png">

This example shows that the simulation was run 4,000 times and was counting the students who were infected. 

#### PanaXea

For the PanaXea model, you can set up a Launcher.py. Here you just iterate through your model.run() however many times you want to and then put the data into a file.


# TST-model_disease
## Test Disease Spread

- Pass test: For the agents to be exposed to the virus, they need to be in school. 

- Fail test: If a student gets exposed over the weekend, then it is a fail. During the weekend there should be no disease spread. 

- Pass test: The student goes through a 2 day incubation period.
- Pass test: Students who are infectious should only infect other students during the 2 day incubation period, after that, they are home.
- Pass test: After 2 days incubation period, the student enters 3 day isolation period, their location should be "Home"


- Pass test: The total duration of the disease should be 5 days per student who is infected.

#### Important to check:

If someone is infected on Friday, then they will start their incubation period on Saturday. When Monday comes the infected student should have entered their isolation period. This means no matter how many students get infected on Friday, the total disease outbreak for the simulation will completely finish after 5 days starting Saturday when their incubation period begins. By Thursday the students infected would have all become healthy again ending the simulation.


# TST-model_network
## Testing Model Network 

All students need to be generated and split into classrooms, the test must check:
- Pass test: There should be 126 agents in this model
- Pass test: 21 students per class equating to 6 classrooms

When generating the network that connects the students to each other, you need to check:
- Pass test: students should have > 2 seat neighbours


#### An example finished network 

This provides an idea of how the network connections between the agents should be generated. There are 6 classrooms, holding 21 agents in each. The agents all have their seat neighbours and group members within the class. 

![network-edit](https://user-images.githubusercontent.com/33029552/88955574-00e19d00-d294-11ea-9bd8-7cfb25b3ff55.png)


# TST-output
## Test Output
The test output is to help see if we are meeting the requirements for what the model should be accurately outputting to us. 

- Pass test: The disease outbreak duration is 5 days. It is important to make sure that it lasts 5 days and nothing less than that.
- Fail test: If the model only runs for 2 days, this could be that it is only taking into account the 2 days of incubation period and not the 3 days of isolation that the student needs to complete. 
- Fail test: If the model run is lasting longer than 10 days from the results, something is incorrect.