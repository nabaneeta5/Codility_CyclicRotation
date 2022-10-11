# Codility_CyclicRotation
Rotate an array to the right by a given number of steps.

# Task description
An array A consisting of N integers is given. Rotation of the array means that each element is shifted right by one index, and the last element of the array is moved to the first place. For example, the rotation of array A = [3, 8, 9, 7, 6] is [6, 3, 8, 9, 7] (elements are shifted right by one index and 6 is moved to the first place).

The goal is to rotate array A K times; that is, each element of A will be shifted to the right K times.

# Link Details
[trainingRS7BRU-PR4](https://app.codility.com/demo/results/trainingRS7BRU-PR4/)

# Programming Language
Java SE 8

# Solution Code

```
import java.util.*;

class Solution {
    public int[] solution(int[] A, int K) {
        // write your code in Java SE 11

        ArrayList<Integer> arr= new ArrayList<>();

        if(K<A.length && K!=0 && A.length!=0)
        {
            arr=rotate(K, A.length, A);
            int[] B=arr.stream().mapToInt(j -> j).toArray();
            return B;   
        }
        else if(K>A.length && K!=0 && A.length!=0){
            if(K%A.length==0)
            {
                return A;
            }
            else{
                arr=rotate(K%A.length, A.length, A);
                int[] B=arr.stream().mapToInt(j -> j).toArray();
                return B;  
            }
        }
        return A;
    }

    public ArrayList<Integer> rotate(int K, int L, int[] A){
        ArrayList<Integer> result=new ArrayList<>();
        for(int i=L-K; i<L; i++){
            result.add(A[i]);
        }
        for(int i=0; i<L-K; i++){
            result.add(A[i]);
        }
        return result;
    }
}

```

