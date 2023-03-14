# Computational Complexity

**Computational complexity** is a field from computer science which **analyzes algorithms based on the amount resources required for running it**. The amount of required resources varies based on the input size, so the complexity is generally expressed as a function of *n*, where *n* is the size of the input.

It is important to note that when analyzing an algorithm we can consider the **time complexity** and **space complexity**. The space complexity is basically the amount of memory space required to solve a problem in relation to the input size. 

> Even though the space complexity is important when analyzing an algorithm, in this story we will focus only on the time complexity. and space complexity will be your assignments
> 

# **Time Complexity**

As you’re reading this story right now, you may have an idea about what is time complexity, but to make sure we’re all on the same page, let’s start understanding what time complexity means with a short description from [Wikipedia](https://en.wikipedia.org/wiki/Time_complexity).

> In computer science, the time complexity is the computational complexity that describes the amount of time it takes to run an algorithm. Time complexity is commonly estimated by counting the number of elementary operations performed by the algorithm, supposing that each elementary operation takes a fixed amount of time to perform.
> 

When analyzing the time complexity of an algorithm we may find three cases: **best-case**, **average-case** and **worst-case**. Let’s understand what it means.

Suppose we have the following unsorted list **[1, 5, 3, 9, 2, 4, 6, 7, 8]** and we need to find the index of a value in this list using [linear search](https://en.wikipedia.org/wiki/Linear_search).

- **best-case**: this is the complexity of solving the problem for the best input. In our example, the best case would be to search for the value 1. Since this is the first value of the list, it would be found in the first iteration.
- **average-case**: this is the average complexity of solving the problem. This complexity is defined with respect to the distribution of the values in the input data. Maybe this is not the best example but, based on our sample, we could say that the average-case would be when we’re searching for some value in the “middle” of the list, for example, the value 2.
- **worst-case**: this is the complexity of solving the problem for the worst input of size n. In our example, the worst-case would be to search for the value 8, which is the last element from the list.

Usually, when describing the time complexity of an algorithm, we are talking about the worst-case.

Ok, but how we describe the time complexity of an algorithm?

We use a mathematical notation called Big-O.

---

## Big O Notation

Big O notation is a mathematical notation used to describe the time complexity of an algorithm or the growth rate of a function. It is a way of expressing the upper bound on the rate of growth of a function, usually in terms of the size of its input.

> is a mathematical notation that describes the [limiting behavior](https://en.wikipedia.org/wiki/Asymptotic_analysis) of a [function](https://en.wikipedia.org/wiki/Function_(mathematics))
 when the [argument](https://en.wikipedia.org/wiki/Argument_of_a_function) tends towards a particular value or infinity(`Wikipedia`)
> 

In computer science, Big O notation is commonly used to analyze the time complexity of algorithms. It expresses the worst-case scenario for the time required by an algorithm as the size of the input approaches infinity.

<aside>
💡 we use `Big O` to describe the performance of an algorithm and this helps are to determine if the given algorithm is scalable or not

</aside>

**Big-O notation**  sometimes called “asymptotic notation”, **is a mathematical notation that describes the limiting behavior of a function** when the argument tends towards a particular value or infinity.

Big O notation is a way to measure how much time and resources an algorithm needs to complete a task.

Imagine you are trying to sort a bunch of papers into alphabetical order. If you have a few papers, it's pretty easy to do by hand, but if you have a thousand papers, it will take you much longer. An algorithm is like a set of instructions that a computer follows to sort the papers.

Big O notation tells you how long it will take the algorithm to sort the papers as the number of papers gets bigger and bigger. For example, an algorithm with a Big O notation of O(n) means that if you double the number of papers, it will take the algorithm about twice as long to sort them.

## Data Structure and Big O

Certain operation can be more or less costly depending on the data structure 

Big O notation is used to analyze and compare the time complexity of different data structures and algorithms, which is an important consideration when designing efficient and scalable software systems.

---

## As a Developer, knowing Big O notation can provide several advantages, including:

1. **Performance optimization**: Understanding Big O notation can help developers optimize the performance of their code. By analyzing the time complexity of an algorithm or data structure, developers can identify bottlenecks and optimize their code to reduce the time it takes to complete a task.
2. **Choosing the right data structure**: Different data structures have different time complexities for various operations, such as searching, inserting, or deleting data. By knowing the Big O notation for these operations, developers can choose the best data structure for a given task and optimize the performance of their code.
3. **Scaling applications**: Big O notation is a useful tool for predicting how an application will perform as the data it processes grows larger. Developers can use Big O notation to estimate how much processing power and memory an application will need to handle increasingly large data sets, allowing them to design applications that can scale as needed.
4. **Communication with other developers**: Knowing Big O notation is useful for communicating with other developers about the performance characteristics of code. By using standardized terminology, developers can quickly and accurately convey the performance characteristics of an algorithm or data structure to others, allowing for better collaboration and problem-solving.

Overall, understanding Big O notation is essential for developing efficient and scalable software applications, and it can help developers optimize performance, choose the right data structures, and communicate effectively with other developers.

---

Here's a Java function that lists all the dividers of a given integer **`n`**:

Algo 1 

```jsx
public static void listDividers(int n) {
    System.out.print("Dividers of " + n + ": ");
    for (int i = 1; i <= n; i++) {
        if (n % i == 0) {
            System.out.print(i + " ");
        }
    }
}
```

Algo 2 

```jsx
public static void listDivisors(int n) {
    System.out.print("Divisors of " + n + ": ");
    for (int i = 1; Math.sqrt(n); i++) {
        if (n % i == 0) {
            System.out.print(i + " ");
            if (i != n/i) {
                System.out.print(n/i + " ");
            }
        }
    }
}
```

# O(1) big O notation (****Constant Notation)****

O(1) is a time complexity notation in Big O notation. It represents algorithms that take a constant amount of time to complete regardless of the input size. This means that the time taken by the algorithm remains constant even if the size of the input increases.

For example, consider a function that takes a single argument and returns the first element of an array. This function will always take the same amount of time to execute, no matter how large the array is. Therefore, its time complexity is O(1).

In Java, an example of an O(1) algorithm would be accessing an element in an array or getting the value of a variable. This is because accessing an element in an array or getting the value of a variable takes the same amount of time regardless of the size of the array or the complexity of the variable.

<aside>
💡 O(1) is the best-case scenario: O(1) means the algorithm's time complexity is constant, which is the best-case scenario because the algorithm takes the same amount of time to complete regardless of the input size.

</aside>

Here is an example code snippet:

```java
int[] array = new int[100];
int variable = 5;

// Accessing an element in an array
int element = array[0];

// Getting the value of a variable
int value = variable;
```

---

# O(n) big O notation (****Linear Notation)****

O(n) is a notation used to describe the time complexity of an algorithm or function, where the time taken to execute the algorithm increases linearly with the size of the input.

In Big O notation, "n" represents the size of the input to the algorithm. If an algorithm has a time complexity of O(n), it means that the time taken to execute the algorithm is directly proportional to the size of the input.

For example, if we have an algorithm that iterates over an array of size n and performs a constant-time operation on each element, the time complexity of this algorithm would be O(n). As the size of the array increases, the time taken to execute the algorithm also increases linearly.

Other examples of algorithms with O(n) time complexity include linear search, counting the frequency of elements in an array, and traversing a linked list.

It is worth noting that O(n) is considered to be a relatively efficient time complexity, as the time taken to execute the algorithm grows at a relatively slow rate with respect to the input size.

Example

```java
public static void printArray(int[] arr, String arr2) {
    for (int i = 0; i < arr.length; i++) {
        System.out.println(arr[i]);
    } o(n)

for (int i = 0; i < arr2.length; i++) {
        System.out.println(arr[i]);
    }

 0(m)
int element = arr[0];

comp = o(n)+o(n) =  o(n+m)
}
```

this method simply prints all the elements of an array one by one. The time complexity of this method is also O(n) since it has to iterate over all n elements of the array to print them.

```java
public static int sumArray(int[] arr) {
    int sum = 0;
    for (int i = 0; i < arr.length; i++) {
        sum += arr[i];
    }
    return sum;
}
```

This method computes the sum of all the elements in an array by iterating over them one by one and adding them to a running sum. The time complexity of this method is O(n) since it has to iterate over all n elements of the array to compute the sum.

![https://lukasmestan.com/assets/images/o-n.png](https://lukasmestan.com/assets/images/o-n.png)

Linear time complexity is generally considered to be fast and efficient for most input sizes. For example, an input size of 1000 would result in 1000 operations, which is still relatively fast and feasible for most applications.

It is important to note that while linear time complexity is generally considered to be fast, it is not always the fastest possible time complexity for a given problem. In some cases, it may be possible to find algorithms with even better time complexity, such as logarithmic time algorithms like O(log n) or constant time algorithms like O(1). However, linear time algorithms are often a good starting point for most problems, and are generally sufficient for many applications.

---

# O(n^2) big O notation(****Polynomial Notation)****

O(n^2) is the big O notation for an algorithm that has a quadratic time complexity with respect to the size of the input. This means that as the input size increases, the time required to solve the problem grows quadratically.

For example, a simple nested loop algorithm that compares each element in a list with every other element has a time complexity of O(n^2). This is because for each element in the list, the algorithm needs to compare it with every other element, resulting in a total of n*n = n^2 comparisons.

Quadratic time complexity is generally considered to be slow and inefficient for large input sizes. For example, an input size of 1000 would result in 1 million comparisons, which may be too slow for some applications.

It is often desirable to find algorithms with better time complexity, such as linear time algorithms like O(n) or logarithmic time algorithms like O(log n). However, there are some problems for which no known better time complexity algorithms exist, and quadratic time algorithms are the best option. In such cases, it may be necessary to optimize the algorithm or find alternative solutions that are more efficient for the specific problem at hand.

Here are some examples of Java code with O(n^2) time complexity:

```java
public static void generatePairs(int[] arr) {
    for (int i = 0; i < arr.length; i++) {
        for (int j = i+1; j < arr.length; j++) {
            System.out.println(arr[i] + ", " + arr[j]);
        }
    }
}
```

This method generates all possible pairs of elements in an array by iterating over all pairs of distinct elements. The time complexity of this method is O(n^2) since it has to iterate over all n elements of the array for each of the n-1 iterations in the outer loop.

![https://www.donnywals.com/wp-content/uploads/IMG_0021-1024x604.jpeg](https://www.donnywals.com/wp-content/uploads/IMG_0021-1024x604.jpeg)

---

# O(log n) big O notation(****Logarithmic Notation)****

In computer science, O(log n) represents a complexity class of algorithms whose running time grows logarithmically with the input size n. This means that as the size of the input increases, the running time of the algorithm increases at a much slower rate than the input size itself.

To put it simply, O(log n) algorithms are very efficient and scalable for large inputs. For example, binary search is an algorithm with a time complexity of O(log n) since it halves the search space with each iteration, leading to a logarithmic increase in running time as the input size increases.

Other examples of algorithms with O(log n) time complexity include certain tree traversal and search algorithms, as well as some sorting algorithms like MergeSort and QuickSort.

In summary, O(log n) notation is used to describe algorithms whose running time increases logarithmically with the input size n.

Logarithmic time complexity is generally considered to be very fast and efficient for large input sizes. In fact, algorithms with O(log n) time complexity are often used in performance-critical applications where fast response times are required.

It is important to note that the base of the logarithm is not specified in the big O notation. In practice, the base of the logarithm can have an impact on the actual running time of the algorithm, but it does not change the overall time complexity class. For example, an algorithm with a base 2 logarithm may be twice as fast as an algorithm with a base 10 logarithm for the same input size, but both algorithms would still have a time complexity of O(log n).

![https://i.stack.imgur.com/qPNNp.png](https://i.stack.imgur.com/qPNNp.png)

---

# O(2^n)  big O notation

O(2^n) is the big O notation for an algorithm that has an exponential time complexity with respect to the size of the input. This means that as the input size increases, the time required to solve the problem grows exponentially.

For example, an algorithm that generates all possible subsets of a set of size **`n`** has a time complexity of O(2^n). This is because there are 2^n possible subsets, and the algorithm needs to generate and process each one of them.

Exponential time complexity is generally considered to be very slow and impractical for large input sizes, as the running time quickly becomes unfeasible. Therefore, it is often desirable to find algorithms with better time complexity, such as polynomial time algorithms like O(n^2) or O(n^3). However, there are some problems for which no known polynomial time algorithms exist, and exponential time algorithms are the best option. In such cases, it may be necessary to optimize the algorithm or find alternative solutions that are more efficient for the specific problem at hand.

![https://www.101computing.net/wp/wp-content/uploads/Big-O-Notation-Exponential-Algorithm.png](https://www.101computing.net/wp/wp-content/uploads/Big-O-Notation-Exponential-Algorithm.png)

---

![Untitled](Computational%20Complexity%209edf00cda1d240a9b14c68e942186fd7/Untitled.png)