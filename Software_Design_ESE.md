#  Software_Design_ESE
> Author : Aaron Augustine

> Star the gist so that I can get a consensus on how many people are using this resource
> 
[Github Repo Link for all ESE Notes](https://github.com/ToothlessRider/ESE_Notes.git).

# Table of Contents
1. [Previous year questions](#previous-year-questions)
2. 
3. [Basis Path Testing](#basis-path-testing)


## Classtest Question

## Cyclometric graph questions





## Previous Year Questions

Q1. a. **Write a code to check if matrix has inverse or not. Draw control flow graph (CFG) for the same. <br>Find out total number of linearly independent path in CFG. <br>Give McCabe's metric or Number of test cases for the CFG.**

Ans.

<hr>

Q1. b. **Why it is said to "Keep level of Abstraction as high as possible"? <br>How does it help in software design**

Ans.

<hr>

Q1. c. **Which according to you is better architecture? Data flow architecture or data centered architecture?**

Ans. 

<hr>

Q1. d. **What are different types of Coupling? List and explain each of the type**

Ans.
#### Content Coupling
- It occurs when one component **secretly modifies data / instructions** that are **internal to another component**
#### Common Coupling
- Occurs whenever you use a global variable, i.e., All components using global variables get coupled to each other
#### Control Coupling
- Occurs when one **procedure calls another one and controls what the second procedure does**.
#### External Coupling
- When one module **depends on other modules**
#### Data coupling , etc
- When two or more modules **share data with each other**

<hr>

Q2. a. **Why do you think software development should focus on the needs of users?**

Ans.
 Software development should focus on the needs of the users for the following reasons : $R^3$
* To *reduce training and support* costs ( i.e, make it so that users naturally understand how to use the software ).
* To *reduce time to learn* the system..
* To *reduce costs by developing only the required features*.
* To *create a UI accurate to what the user wants*.
* Since UI is the entire application for users, making sure it is good and according to what the user wants is very important.

This is mainly to answer these following questions : 
- *What is it that they need to do?*
- *Are they comfortable with the UI?*
- *Do they ‘see’ what they feel they need to see?*

<hr>

Q2. b. **What characteristics of users must be focused on in the software development process?**

Ans.
#### Characteristics are as follows : 
- **Goals for using the system**
	- What is the work the users need to get done?
- **Potential patterns of use**
	- 24-7? EOM/EOD/EOY? On-line; batch? Peak load
times? Down times? MTTR?
- **Demographics**
	- Cultures; religions; sensitivities
- **Knowledge of the application domain**
	- Finance and accounting? Manufacturing? Process control? Real time? Student environment?
- **Physical ability**
	- ADA? Other physical limitations

<hr>

Q2. c. **Differentiate between usability and utility with respect to software design.**

Ans.
### Usability

* Does the system allow the user to learn and to use raw capabilities easily?

The Key aspects of usability are : 
- **Learnability:** How easy is it for users to learn how to use the system?
- **Efficiency:** Once users have learned the system, how quickly can they perform tasks?
- **Memorability:** After a period of not using the system, how easily can users re-establish proficiency?
- **Error Prevention and Recovery:** How well does the system prevent errors, and if errors occur, how easily can users recover?
- **User Satisfaction:** How satisfied are users with their overall experience?

*Example:* An e-commerce website with a clear and intuitive navigation menu, simple checkout process, and helpful error messages has good usability.

### Utility

* Does the system provide the raw capabilities to allow the user to achieve their goal

The key aspects of utility are :
- **Relevance:** How well does the system address the user's specific requirements or objectives?
- **Functionality:** Does the system provide the necessary features and tools to accomplish tasks?
- **Value:** How much value does the user perceive in using the system?
- **Fit for Purpose:** Is the system designed to serve its intended purpose effectively?
   
*Example:* A project management software that includes features such as task tracking, team collaboration, and reporting provides utility for users managing complex projects.

<hr>

Q2. d. **What aspects can usability be divided into? Explain with examples.**

Ans. 
### Usability

* Does the system allow the user to learn and to use raw capabilities easily?

The Key aspects of usability are : 
- **Learnability:** How easy is it for users to learn how to use the system?
- **Efficiency:** Once users have learned the system, how quickly can they perform tasks?
- **Memorability:** After a period of not using the system, how easily can users re-establish proficiency?
- **Error Prevention and Recovery:** How well does the system prevent errors, and if errors occur, how easily can users recover?
- **User Satisfaction:** How satisfied are users with their overall experience?

*Example:* An e-commerce website with a clear and intuitive navigation menu, simple checkout process, and helpful error messages has good usability.

<hr>

Q3. a. **How do various stakeholders in the software industry evaluate user interfaces?**

Ans.

<hr>

Q3. b. **Explain the top-down design approach in software architecture design.**

Ans.
#### Top-down 
* First design the high level structures of the system
* Then work your way down to the low level constructs
* Finally arrive at the detailed decisions such as : 
	* Format of data items
	* Individual algorithms

Start with the software architecture and the type of database to be used

<hr>

Q3. c. **List and explain principles leading to good design.** *[ DHLHI ]*

Ans.
There are certain Overall Goals of good design. These are to : 
- Increase the profit by reducing cost
- Ensure that the design accomodates the user requirements
- Increase qualities such as
	- Usability
	- Efficiency
	- Reliability
	- Maintainability
	- Resuability, in the design

The principles to achieve a good design are as follows : **[DHLHI ]**
1. **Divide and Conquer** :
Instead of dealing with something big all at once, we break it down into small subproblems, i.e., : 
	- Smaller components are easier to understand
	- Parts can be replaced or exchanged

Ways to implement divide and conquer are : 
- Distributed system -> *Clients and Servers*
- System -> *Subsystems*
- Subsystem -> *Packages*
- Packages -> *Classes*
- Classes -> *Methods*
- 
2. **High Cohesion** :
A subsystem module has high cohesion if it keeps together things that are related and removes those that aren't.<br>
Types of cohesion are : 
- Functional Cohesion
- Layer Cohesion
- Communicational Cohesion
- Sequential Cohesion
- Procedural Cohesion
- Temporal Cohesion
- Utility Cohesion

3. **Low Coupling** : 
Coupling occurs when there are **interdependencies between multiple modules**<br>
The types of coupling are as follows : 
- Content Coupling
- Commong Coupling
- Control Coupling
- External Coupling
- Data coupling , etc

4. **High level of Abstraction** : 
Ensure that your designs allow you hide consideration of details, making them **less complex**

5. **Increase Reusability**
Design for reusability of components of GUI

6. **Reuse existing material**
Reuse existing designs and code wherever possible ( taking advantage of the reusability concept )

<hr>

Q3. d. **Explain communication cohesion with reference to architectural design.**

Ans.

<hr>

Q4. a. **What are the different architectural styles? Which one would you choose for the software project "Digitization of Dr. B. R. Ambedkar Central Library of VJTI"?**

Ans.

<hr>

Q4. b. **Consider that software is to be built for the automatic recording of online meeting attendance. Assume suitable data and create a data model (ER-based).**

Ans.

<hr>

Q4. c. **List and explain Pattern Description Parameters with reference to software design patterns**

Ans.

<hr>

Q4. d. **List the various design patterns in Gangs of Four design pattern explain any one**

Ans. 

<hr>

Q5. **Write code and draw class diagram to explain observer pattern (consider suitable example)**

Ans.

<hr>

Q5. b. **Perform general class based modelling of delegator pattern also give specific example.**

Ans.

<hr>

Q5. c. **Give context, forces, problem, solution and anti-pattern for adaptor pattern.**

Ans.

<hr>

Q5. d. **Give real time example of façade pattern, give class diagram and code for same**

Ans. 

<hr>


<hr>

## Basis Path Testing
> [PPT Link](https://classroom.google.com/c/NjU0MzUzOTIxNTA0/m/NjY0MzMxNzg2MTEy/details)

Q1. **What is Software Testing Funadmentals, it's Objectives, Principles and Testability ?**

Ans.

<hr>

Q2. **What are the different CFG Notations?**

Ans. 


<hr>

## PPT 25
Q1. **What are the different types of Cohesion and mention the layers used in**
1. An Application Program
2. An Operating System
3. Communication

Ans.
A subsystem module has high cohesion if it keeps together things that are related and removes those that aren't.<br>
Types of cohesion are : 
#### Functional Cohesion
- When all the code that **computes a particular result** is kept together

#### Layer Cohesion
- Keeping all facilities for **providing or accessing related services** together
- Layers in an Application Program :
**![](https://lh7-us.googleusercontent.com/GtTLkn8BJplYsfjsPlvsDS6Dl1uxZyUvCCNxpeJEiOHJO5YBm6izCdVI8XE3LCl7hrCkMiq0gr6Pl9XbfQHqFTMxZFOv7vwRCnH2VJDQEr7oXTYVMh6sWM0f_f4nf09w18whFztMXPc_dj41svCplpw)**
- Layers in an OS 
**![](https://lh7-us.googleusercontent.com/vy-UvEsj3kWO5zDmNsklvyAmJb82LcVSZjTCtIZLdlP9bfFRNBj06YueAZJMoz-Sq9hcipRiEyfsWmYzrUbh3m16fDhpgLtS0LOfbZxd7QYMFvStz-BuWQRg-CZdWu0uR86cMbOTyLvHc-efR_0dvCM)**
- Layers in communication 
**![](https://lh7-us.googleusercontent.com/FKQ5vbd3sxpmvtc3KFmI2sp7ua8uZskd8k67Wod8ciS5pyfk9lpLr6A4EmdXh95w6vIuvzCOuIskBOyR1oNUw5x1-jhlTLoZZBvHf1I20M824SmdK0bPRafF6c-ecWAY3qU125h6sD9oqTIGGEi6K74)**

#### Communicational Cohesion
- All the modules that **manipulate certain data** are kept together

#### Sequential Cohesion
- Procedures which provide **input to the next module** are kept together
#### Procedural Cohesion
- **Procedures used one after another** are kept together
#### Temporal Cohesion
- Operations performed **during the same phase of execution** are kept together
#### Utility Cohesion
- Related utilities are kept together


<hr>

Q2. **What are the different types of Coupling?**

Ans. 
> [Link to ans](#content-coupling)
<hr>
