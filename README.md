# City_EE2702_DESIR

## EE2702 Computer Science and Programming
## Discrete Event Simulation of an Internet Router
#### 2018/2019

### Assignment:
Simulation is a method of analysing real-world events or newly designed algorithms and solutions. The discrete event simulation model consists of identifying individual events in the simulated model and assigning these events a unique time in the time schedule. Discrete event simulation can be used to simulate a number of real systems, including computers networks, biomedical processes, supply chains, and a variety of scheduling problems.

For this assignment, you are expected to produce a python code which performs a full discrete event simulation of a very simple Internet router. The router is characterized by: 
- Random arrival of packets
- Random distribution of packet sizes
- Multiple router output interfaces (‘servers’)
- Serving schedule – the simulation will have to support both first-in-first-out (FIFO) serving, and also priority serving

The case study used for this assignment is operation of a very simple Internet router. Internet packets of variable sizes arrive at the router to be processed and forwarded further in the networks. Your simulation will enable performance evaluation of the router, by identifying the average waiting time, the probability of immediate response, the average packet size, and other performance parameters. Assumption is made that the router has fixed output data rate – the duration of the packet processing can be considered identical to the packet size. To develop the simulator, you are asked to complete the following challenges:

#### 1 – one server, FIFO queueing

In this first assignment, you are asked to develop a discrete-event simulation of an Internet router with a single input queue and a single output interface. The packets arrive following a random Poisson process, with a pre-defined average time between two arriving packets. The Poisson process is characterized with an exponential distribution of inter-arrival times. The packets have random sizes – the packet size should be calculated by the simulator at the packet arrival. The packet size should be considered a random variable with exponential distribution. In the case the packet has arrived and cannot be immediately served, it has to wait for the first available opportunity to be served. The output interface – the server – should operate without any pauses, and should operate at a constant serving rate – this means that packet size determines the service time duration.

Your code should request the average system parameters – average packet size and average interarrival time for the packets, and should calculate the following parameters: 
 - average waiting time
 - average queue size
 - probability that the queue size is 0 at arrival of a new call
 - probability that the queue size is greater than 5 times the average packet size.

#### 2 – multiple servers, FIFO queueing, random choice of server

In the second assignment, your code from the previous assignment should be modified to support four separate servers (four output router interfaces). In the simulation, upon the arrival of the packet, the server (output interface) should be randomly identified for that packet, regardless of the queue sizes. 
Your code should request the average system parameters – average packet size and average inter-arrival time for the packets, and should calculate the same simulation results as in assignment 1. 
Similarly to 1, generate graphs to show how calculated parameters change with the change in the input values – the average packet size or the average packet inter-arrival time.

#### 3 – two servers, two classes, random assignment of classes with mean probabilities 20-80, one queue for the priority class and one for the non-priority

In the third assignment, your simulator should operate as in the previous assignments, but this time at the generation (“arrival”) of the packets the packets should be assigned a class (“priority” or “economy”). The class assignment should be random, but on average 20% of the packets should be “priority” and 80% should be “economy”. The serving policies should be as follows: 
 - Policy A: one server should be dedicated for the priority packets only, and one for the economy packets. If there are no priority packets, that server should be empty
 - Policy B: one server should be dedicated for the priority packets, and one for the economy packets. If there are no priority packets, the first waiting economy packet should be served. 
Your code should request the average system parameters – average packet size and average inter-arrival time for the packets, probability of the priority packets (default = 20%) and should calculate the following parameters: 
 - average waiting time for both traffic classes
 - average queue size for both traffic classes
 - probability that the queue size for each of the classes is more than 5
 - probability that the queue size is 0 at arrival of a new packet
Again, your program should generate graphs to show how calculated parameters change with the changes in the input values. What conclusion can you make when you compare the performance of policy A and policy B?

### Presenting Simulation Results

For all simulations: 
 - The mean values for these parameters should be calculated in the simulation. 
 - In addition to this, the simulation(s) should generate a time graph, to show how average values for the average waiting time and the average queue size change with simulation time. 
 - The simulation should also show how the parameters given above change with the increase in the average packet size or with the increase in the average inter-arrival time. This is best done using graphs, with values for average packet size / average inter-arrival time on x-axis, and calculated parameters on the y-axis. 
 - When running simulations, make sure the simulation run to process at least 10,000 packets.
