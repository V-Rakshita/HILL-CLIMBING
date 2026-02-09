<h1>ExpNo 5 : Implement Simple Hill Climbing Algorithm</h1> 
<h3>Name:             </h3>
<h3>Register Number:             </h3>
<H3>Aim:</H3>
<p>Implement Simple Hill Climbing Algorithm and Generate a String by Mutating a Single Character at each iteration </p>
<h2> Theory: </h2>
<p>Hill climbing is a variant of Generate and test in which feedback from test procedure is used to help the generator decide which direction to move in search space.
Feedback is provided in terms of heuristic function
</p>


<h2>Algorithm:</h2>
<p>
<ol>
 <li> Evaluate the initial state.If it is a goal state then return it and quit. Otherwise, continue with initial state as current state.</li> 
<li>Loop until a solution is found or there are no new operators left to be applied in current state:
<ul><li>Select an operator that has not yet been applied to the current state and apply it to produce a new state</li>
<li>Evaluate the new state:
  <ul>
<li>if it is a goal state, then return it and quit</li>
<li>if it is not a goal state but better than current state then make new state as current state</li>
<li>if it is not better than current state then continue in the loop</li>
    </ul>
</li>
</ul>
</li>
</ol>

</p>
<hr>
<h3> Steps Applied:</h3>
<h3>Step-1</h3>
<p> Generate Random String of the length equal to the given String</p>
<h3>Step-2</h3>
<p>Mutate the randomized string each character at a time</p>
<h3>Step-3</h3>
<p> Evaluate the fitness function or Heuristic Function</p>
<h3>Step-4:</h3>
<p> Lopp Step -2 and Step-3  until we achieve the score to be Zero to achieve Global Minima.</p>

<hr>
<h3>Program:</h3>
<hr>

```python
import random
import string
def generate_random_solution(ans):
    l=len(ans)
    random_soln=[random.choice(string.printable) for _ in range(l)]
    return random_soln
def mutate(soln):
    ind=random.randint(0,len(soln)-1)
    soln[ind]=random.choice(string.printable)
    return soln
def evaluate(solution,answer):
    
    ans=list(answer)
    diff=0
    for i in range(len(solution)):
        s=solution[i]
        a=ans[i]
        diff= diff+ abs(ord(a)-ord(s))
    return diff
        
def simplehillclimbing():
    answer=input()
    best=generate_random_solution(answer)
    best_score=evaluate(best,answer)
    while True:
        print(best_score,''.join(best))
        if best_score==0:
            break
        new_soln=mutate(list(best))
        score=evaluate(new_soln,answer)
        if score<best_score:
            best_score=score
            best=new_soln
simplehillclimbing()
```

<hr>
<h2>Sample Input and Output</h2>
<h2>Sample String:</h2> Artificial Intelligence
<h2>Output:</h2>
Score: 643  Solution :  8RzF:oG ]%;CPORRMe!zGvk<br>
Score: 609  Solution :  8RzF:oG ]%;CPqRRMe!zGvk<br>
Score: 604  Solution :  8RzF:oG ]%;CPqRRMe!zGqk<br>
Score: 594  Solution :  8RzF:oG ]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
....................................................<br>
..................................................<br>
................................................<br>
Score: 1  Solution :  Artificial Intelligencf<br>
Score: 1  Solution :  Artificial Intelligencf<br>
Score: 1  Solution :  Artificial Intelligencf<br>
Score: 1  Solution :  Artificial Intelligencf<br>
Score: 0  Solution :  Artificial Intelligence<br>


<hr>
<h3>Output:</h3>
<hr>

<img width="189" height="973" alt="image" src="https://github.com/user-attachments/assets/c7dce186-5e3b-45c3-97aa-ea8bec425a95" />

<img width="202" height="967" alt="image" src="https://github.com/user-attachments/assets/1dc0907b-f737-4382-8185-1f0634c04604" />


<img width="210" height="971" alt="image" src="https://github.com/user-attachments/assets/aad01577-57cf-44c7-9091-f0cc65668c78" />

<img width="181" height="970" alt="image" src="https://github.com/user-attachments/assets/c5fddd3e-4ece-4d87-a790-0370ef0ae1a2" />

<img width="196" height="965" alt="image" src="https://github.com/user-attachments/assets/e14a2f0b-eaca-4e0a-8467-77d48e739834" />

<img width="173" height="955" alt="image" src="https://github.com/user-attachments/assets/58ff134e-c9ff-4ceb-99b8-e33dea4f58c6" />


<img width="192" height="935" alt="image" src="https://github.com/user-attachments/assets/ffa346a0-32b5-4c46-a506-ceeee707994e" />











