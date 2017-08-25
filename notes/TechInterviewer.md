# Technical Interviews
## Mark Bastian
## 28 August 2017

----

# About Me
* Work
  * Senior Software Developer at Clearwater Analytics
  * Former Principal Member of Technical Staff at Sandia National Laboratories
* Education
  * BSME, Boise State University
  * MSME, Washington State University   
* Conducted many, many technical interviews

----

# What do you want?
* A Job
* Pay
* Domain area
* Continuing education
* Work-life balance
* Location
* Schools

----

# Research the Company
* What does the company do?
  * How does that align with your skills and interests?
* Is this where you want to be?

----

# Resumes
* If you list it, I will look at it
  * Linkedin, github
* Only list that which you are prepared to discuss
  * Languages, projects, jobs
* For me, interest in programming is a plus
  * github projects (can be very small)
  * Esoteric languages, libraries, topics

----

# Before the Interview: More Research on the Company
* What kind of questions will be asked? 
* Does the company have an organized hiring pipeline?

---

# The Interview
* Things **I** care about
  * Thought processes
  * Communication skills
* Things I don't care about
  * Syntax (to a degree)
  * API specifics

----

# How I work in real life
* Understand the problem
* Formulate a solution
  * Rubber-ducking
  * Explaining/Critiquing solutions
* Implement then optimize
* Looking up API details
* Juxtapose this with the interview

----

# Part 1: Easier Questions
* Can you write a simple program?
* Do you understand recursion?
* Do you understand data structures?
  * List, Vector, Map, Set

----

# An Easy Problem
````
(defn normalize [s]
  (-> s (cs/replace #"\W" "") cs/lower-case))

(defn anagram? [s0 s1]
  (= (-> s0 normalize frequencies)
     (-> s1 normalize frequencies)))
     
(defn anagram-2? [s0 s1]
  (= (-> s0 normalize sort)
     (-> s1 normalize sort)))

(anagram? "I am Lord Voldemort!" "Tom Marvolo Riddle")

(anagram? "dessert" "desert")
````

----

# Soft Skills
* Do you understand the question?
* Do you ask questions?
* When you encounter a difficult problem, what do you do?
* Thinking out loud

----

# Algorithmic Complexity
* O(1), O(n)...
* Is A worse than B? 

----

# Data Structures
* List, Vector, Map, Set
* Know when and how to use them!

----

# Algorithms
* recursion
* searching (BFS, DFS)

----

# Bonuses
* Functional Programming
* Higher order functions
* Immutability



