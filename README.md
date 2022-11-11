# Check-survival-posssibility
Check if it is possible to survive on Island

The problem is a dynamic programming problem.

Ishika got stuck on an island. There is only one shop on this island and it is open on all days of the week except for Sunday. Consider following constraints:

N – The maximum unit of food you can buy each day.
S – Number of days you are required to survive.
M – Unit of food required each day to survive.

Currently, it’s Monday, and she needs to survive for the next S days.
Find the minimum number of days on which you need to buy food from the shop so that she can survive the next S days, or determine that it isn’t possible to survive.

Solution: The first check should be that is the survival even possible, after that successful check then check how many times we need to buy that will be

= Math.floor((S*M)/N)

The first check for the survival possibility is if S>7 then we form a mathematical equation via the constraint that on  Sunday shopping cannot happen so whatever the consumption will happen on first sunday will be the leftout of the week left.
So i did it like this, sunday left out will be = 6*(N)-6*(M) , this leftout value needs to be gte M.

So final equation of survival possibility will be 6*N >= 7*M, for S>=7  and for S<7 the equation will be N >= M

Sharing the piece of code:

```cpp

class Solution{
    static int minimumDays(int S, int N, int M){
        // code here
        
        if(S<7){
            if(N>=M){
                return (int)Math.ceil(((double)S*M)/N);
            }
        }
        else{
            if(6*N>=7*M){
              return (int)Math.ceil(((double)S*M)/N);
            }
        }
        
        return -1;
        
    }
}

```

Time Complexity : O(1)

Space Complexity : O(1)
