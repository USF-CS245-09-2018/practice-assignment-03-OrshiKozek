# CS 245 (Fall, 2018) PracticeAssignment03

The code that is in Practice03Test.java is correct and works. However, I was not able to make the program run from terminal.
I always got the message:

* Error: Could not find or load main class Practice03Test
* Caused by: java.lang.ClassNotFoundException: Practice03Test

However, I was able to manually change the size of the array through the intellij interface: Run > Edit Configurations
(Change program arguments to the desired length)

The only alterations I made to the Practice03Test.java file was the 3 methods I added:
* find_min_iterative(arr)
* find_min_recursive(arr)
* helper(arr, first, min)

---------
    public int find_min_iterative (double[] arr) {
        int indexOfMin = 0; //O(1)
        for (int i = 1; i < arr.length; i++) { //O(1)
            if (arr[i] < arr[indexOfMin]) //O(n)
                indexOfMin = i; //O(1)
        }
        return indexOfMin;
    }
    //total=> O(n)

---------

    public static int find_min_recursive (double[] arr) {
        return helper(arr, 1, 0); //O(whatever helper's total is)
        //total of find_min_recursive=> O(n)
        //O(n) because the function is called n times until the base case is reached

    }

    public static int helper(double[] arr, int first, int min){
        if (first == arr.length)  //O(1)
            return min;
        else{
            if (arr[first] < arr[min]) { //O(1)
                min = first; //O(1)
                first++; //O(1)
                return helper(arr, first, min); //O(n)
            }
            else{
                first++;
                return helper(arr, first, min); //O(n)
            }
        }
        //total=> O(n)
    }
--------------

COMPLEXITY OF ITERATIVE: O(n)
* because it loops through the array n-1 times (by getting rid of the constants, we get O(n))

COMPLEXITY OF RECURSIVE: O(n)
* because it calls the recursive function n-1 times (by getting rid of the constants, we get O(n)