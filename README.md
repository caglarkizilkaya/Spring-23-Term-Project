# IE343-Spring-Term-Project-Questions:
1.When the cooling rate value is 0.0003 it takes some time to execute the code but when we increase the cooling rate to 0.005, the code executes instantly so when the cooling rate increase the execution time decrease because higher cooling rate causes less iteration. 
2.As for parameters we decided initial temperature as 1000 and stopping temperature as 0 so the algorithm gives reasonable high optimal value results, but when we increase the stopping temp to 900 the difference decrease, and we get worse results less optimal solutions. On the other hand, the code executes faster.
Code:
At first, we defined the necessary parameters we created a solution array for our initial solution then we defined cooling rate and stopping criterion. In this algorithm stopping criterion is the value of the temperature so when the temperature reaches certain value the algorithm stops. Before creating algorithm, we created a neighbourhood function which generates neighbouring solutions.  
neighbourhood():  first this function needs weight integer to track the weight constraint because we don’t want to exceed our constraints while generating new solution. Then we create an array which keeps the solution in, here for loop is used to fill every index in the array and in the for loop there is an if statement. that is looking for random integer which is 1 or 0. İf it is 1 that index become true and because we used that item the weight of that item adds up to weigh variable. Then there is another if statement which checks the constraint If the value is exceeded, the changes made in this index are undone, so this index is back to false. The for loop continues like that for each index and then it returns the solution array which is created in this function. 
Algorithm: at the start of the algorithm there is a for loop to control the iterations. Here we define the initial temperature, and the loop continues until the temp reaches to stopping criterion, each iteration of for loop temperature decreases 0.0003 which is cooling rate. In the algorithm first we create neighbouringsolution by using neighbourhood function then we check that neighbouring solution is bigger or that by using calculateAcceptanceProbability() function according to this function if the neighbouring is bigger than current solution it returns 1 so in order to check this we use if statement and look for calculateAcceptanceProbability() = 1 equation. If this equation is true then current solution takes the index of neighboring solutions. If it is false it means that the neighboring solution is worse and we need to decide that the worse solution will be accepted or not. calculateAcceptanceProbability() returns the probability of acceptance when the neighbouringvalue is worse. Here another if statement is used. If the probability + random float between 0 and 1 is bigger than 1 the worse solution is accepted because the ratio of the number of random numbers whose sum with a P value is greater than 1 to the total number of random numbers between 0 and 1 is the same as the P value. If this possibility happens again current value becomes neighboring value. The algorithm continues same for each iteration. After for loop ends the last solution is the best solution so we print the solution and the best value
