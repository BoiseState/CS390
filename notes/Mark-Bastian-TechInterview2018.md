# Technical Interviews
Mark Bastian
<br>28 August 2018

----

## About Me
* Work
  * Senior Software Developer at Clearwater Analytics
  * Former Principal Member of Technical Staff at Sandia National Laboratories
* Education
  * BSME, Boise State University
  * MSME, Washington State University   
* Conducted many, many technical interviews

---

# Getting the right interview

----

## One View on Interviewing
<ul>
<li>You</li>
<ul>
<li class="fragment">Have programming skills</li>
<li class="fragment">Want a job/money</li>
</ul>
<li>I</li>
<ul>
<li class="fragment">Need a programmer with a given skill set</li>
<li class="fragment">Have money</li>
</ul>
<li class="fragment">This is an incorrect view! </li>
</ul>

----

# Reality
* You have a diverse set of needs, desires, skills, and interests
* I have a diverse set of needs, problems, and opportunities
* Both of us are happiest when we can align what we are looking for

----

### What do you want?
* A Job
* Pay
* Domain area
* Continuing education
* Work-life balance
* Location
* Schools
* Take **a lot** of time to figure this out

----

## What do I want?
* Tactically: A specific skill set 
  * (not exactly what you may think, though)
* Strategically: To grow my company and capabilities
  * Lifelong learners
  * People with drive and self-motivation
* Personally: People that are "a good fit" on my teams

----

### How you make it happen
* Research lots of companies/opportunities
* What does the company do?
  * How does that align with your skills and interests?
* Is this where you want to be?
* If so, begin the process of making contact
  * Usually a resume
  * Make a targeted resume!

---

# The Interview
What happens when you've been contacted

----

## How I get prepared: 
## Your Resume
* If you list it, I will look at it
  * Linkedin, github, blog
* Only list that which you are prepared to discuss
  * Languages, projects, jobs
* For me, interest in programming is a plus
  * github projects (can be very small)
  * Esoteric languages, libraries, topics

----

## How you get prepared:
## More Research on the Company
* What kind of questions will be asked? 
  * Technical
  * Soft-skills
  * Brain teasers
* Does the company have an organized hiring pipeline?
* Do you know anyone that works there that you can talk to?

----

## Examples
What kinds of questions do these companies ask and what background is expected?
* Sandia National Laboratories
* Clearwater Analytics
* Google
* Microsoft

----

### The Interview Purpose
* The goal of the interview is to determine:
  * Are you a good match for our company?
  * Is our company a good match for you?
* The goal of the interview is **not** to give you pass/fail test
* Interviews cost a lot
  * Time
  * Money 
* A bad fit costs even more

----

## Ultimately, I want to know...
* Will you be a valuable contributor?
* What is it like working with you?
* Do I want to work with you?
* What kind of potential do you have?
* _How might I determine this?_

----

### How I work in real life
* There are problems, lots of them
* Solving problems is a process
* Understand the problem
* Formulate a solution
  * Rubber-ducking
  * Explaining/Critiquing solutions
* Implement then optimize
* Looking up API details - I do it all the time

----

### Interview Juxtaposition
* I will give you a problem/problems
* Do you understand the problem?
  * If not, what do you do? 
* How do you formulate a solution?
  * Can you explain your solution to me?
  * How do you handle my critiquing of your solution?
* Can you implement then optimize?
* Looking up API details - I'll help you here

----

# Specifics
* I generally ask 2-3 questions of increasing difficulty
* They will be selected based on your experience
* I end with an open invite to ask me whatever you want

---

# Expectations

----

## Soft Skills
* Do you understand the question?
* Do you ask questions?
* When you encounter a difficult problem, what do you do?
* Thinking out loud

----

### Basic Coding Skills
* Functions
* Iteration
* Recursion
* Searching (BFS, DFS)
* Recognizing patterns
* Correct Syntax*

----

### Algorithmic Complexity
* O(1), O(n), O(n<sup>2</sup>), O(b<sup>n</sup>), ...
* Is solution A better or worse than solution B?

----

### Data Structures
* List, Vector, Map, Set
* Know when and how to use them!
* If you use arrays for everything that's bad!

----

### Don't Care
* Object Oriented Design (Me)
* Strict syntax
* Note - Every interviewer is different!

----

## Bonuses
* Functional Programming
* Higher order functions
* Immutability
* Note - Every interviewer is different!

---

### Sample: Anagram
From the web: "A word, phrase, or name formed by rearranging the letters of another, such as _cinema_, formed from _iceman_."

----

### BadAnagram.java
<small style="width:100%">
````
import java.util.Arrays;

public class BadAnagram {    
    public static boolean anagram(String a, String b){
        byte[] aBytes = a.getBytes();
        byte[] bBytes = b.getBytes();
        
        byte[] aRes = new byte[aBytes.length];
        int aIndex = 0;
        for(int i = 0; i < aBytes.length; i++){
            byte x = aBytes[i];
            if((x >= 97 && x <= 122) || (x >= 65 && x <= 90)){
                aRes[aIndex] = (byte) (x - (x >= 97 ? 97 : 65));
                aIndex++;
            }
        }
        for(int i = aIndex; i < aRes.length; i++){
            aRes[i] = 127;
        }
    
        //I could have done my own quicksort here to make it extra awesome.
        Arrays.sort(aRes);
        
        byte[] bRes = new byte[bBytes.length];
        int bIndex = 0;
        for(int i = 0; i < bBytes.length; i++){
            byte x = bBytes[i];
            if((x >= 97 && x <= 122) || (x >= 65 && x <= 90)){
                bRes[bIndex] = (byte) (x - (x >= 97 ? 97 : 65));
                bIndex++;
            }
        }
        for(int i = bIndex; i < bRes.length; i++){
            bRes[i] = 127;
        }
        
        Arrays.sort(bRes);

        if(aIndex != bIndex)
            return false;
        else {
            for(int i = 0; i < aIndex; i++){
                if(aRes[i] != bRes[i]) return false;
            }
        }
        
        return true;
    }
    
    public static void main(String[] args){
        //Do this to decode the byte values of our desired characters
        System.out.println((byte)'a');
        System.out.println((byte)'z');
        System.out.println((byte)'A');
        System.out.println((byte)'Z');

        System.out.println(anagram("I am Lord Voldemort", "Tom Marvolo Riddle"));
        System.out.println(anagram("desert", "dessert"));
    }
}
````
</small>

----

### Anagram.java
<small style="width:100%">
````
import java.util.HashMap;
import java.util.Map;

public class Anagram {
    public static Map<Character, Integer> encode(String s){
        Map<Character, Integer> m = new HashMap<>();
        char[] a = s.toUpperCase().replaceAll("\\W", "").toCharArray();
        for(char c : a){
          Integer i = m.getOrDefault(c, 0);
          m.put(c, i+1);
        }
        return m;
    }
    
    public static boolean anagram(String a, String b){
        return encode(a).equals(encode(b));
    }
        
    public static void main(String[] args){
        System.out.println(anagram("I am Lord Voldemort", "Tom Marvolo Riddle"));
        System.out.println(anagram("desert", "dessert"));
    }
}
````
</small>

----

### A Concise Solution
````
(def encode 
  (comp frequencies cs/lower-case #(cs/replace % #"\W" "")))

(defn anagram? [s0 s1]
  (= (encode s0) (encode s1)))

(anagram? "dessert" "desert")
(anagram? "I am Lord Voldemort!" "Tom Marvolo Riddle")
````

---

### Sample OO Question: Animals
Create Animal API

----

### Textbook Object Oriented Design
Canonical Questions:
* Animals
* Shapes
* Anything with a natural ontology or type hierarchy

----

## Basic Expectations
* Inheritance
* Encapsulation
* Polymorphism

----

### OO In Real Life
* Design a sensing system
* Model a financial security

----

### Olympic Data
I have ~300,000 records like this:
````
 {:sport "Swimming",
  :noc "USA",
  :age 31,
  :sex "M",
  :name "Michael Fred Phelps, II",
  :city "Rio de Janeiro",
  :medal "Gold",
  :year 2016,
  :season "Summer",
  :event "Swimming Men's 4 x 100 metres Medley Relay",
  :team "United States",
  :weight 91,
  :id 94406,
  :games "2016 Summer",
  :height 193}
````
Design a type hierarchy
* What are the classes, methods, etc.?
* How many medals?

----

## What about?
* Dependency Injection
* Inversion of Control
* Factories
* Builders
* Other GoF Patterns
* Immutability/Value Classes
* Complexity

---

## Conclusion
* Interviewing is the process of aligning candidates with jobs
* Determine what kind of candidate you are and what kind of job you want
* Go after this aggressively
* If this is what you truly want you will focus all effort on it

----

# Questions?
