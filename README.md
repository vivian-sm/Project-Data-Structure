# PROJECT DATA STRUCTURE
# Table of Content
- [PROJECT DATA STRUCTURE](#project-data-structure)
- [Table of Content](#table-of-content)
- [Anggota](#anggota)
- [How to create a(n)](#how-to-create-an)
  - [INPUT](#input)
    - [Input section](#input-section)
    - [Input format](#input-format)
  - [Algorithm](#algorithm)
  - [OUTPUT](#output)
- [Sorting Algorithm](#sorting-algorithm)
  - [1. Singly Linked List Sort Algorithm](#1-singly-linked-list-sort-algorithm)

# Anggota
|NRP|Anggota|
|-|-|
|160423034 |  Joshua Nehemia Subagyo|
|160423020| Kevin Nathaniel Sutopo|
|160423033| Evan Daniel Tandiawan|
|1604230XX| Vivan Sisca Maria|
|1604230XX| Fransiskus Hendra Setiawan Roni|

# How to create a(n)
## INPUT
### Input section
```c#
#region INPUT
    Console.WriteLine("INPUT : ");
```
### Input format
```c#
    string input = Console.ReadLine();
```
Input are formated into **string**
```c#
    string[] buffer = input.Split(' ');
    int size = buffer.Length; 
```
Then the input are splitted into **string elements inside an array**
```c#
    int[] dataset = new int[size];
    int[] result = new int[size];
    for (int i = 0; i < size; i++)
    {
        dataset[i] = int.Parse(buffer[i]);
    }
#endregion
```
Finally, input are parse into **array of integers**
`int[] result` is an array of **int** to store the **sorted result**

## Algorithm
All sorting algorithm are created in class **solution.cs**
> **REMINDER**
> All class needed to support the algorithm, must created outside of the `solution.cs` 
```c#
    #region SELECT METHOD OF SORTING
    var watch = System.Diagnostics.Stopwatch.StartNew();
```
Section above are for calculating time needed to run that algorithm
```c#
    // the code that you want to measure 
    result = Solution.SinglyLinkedListSort(dataset);
```
The Method in class **solution.cs** are called, in this example the `SinglyLinkedListSort();` are called from inside the class.

>**REMINDER**
All the class should be **static**
And return an array of int as **result**

```c#
    watch.Stop();
    double elapsedMs = watch.ElapsedMilliseconds;
    #endregion
```
Stop the calculating time.

## OUTPUT
```c#
    #region OUTPUT
    Console.WriteLine("OUTPUT : ");
    for (int i = 0; i < size; i++)
    {
        Console.Write(result[i] + " ");
    }

    #region Performance Checker
    //Accuracy tester
    double counter =1;
    double accuracy;
    for ( int i=0; i< size-1;i++)
    {
        if (result[i] <= result[i+1])
        {
            counter++;
        }
    }
    accuracy = counter / size;
    Console.WriteLine("");
    Console.WriteLine("Accuracy : " + (accuracy*100) + "% (" + counter + "/"+size+")");
    Console.WriteLine("Time elapsed : " + elapsedMs + " ms");
    #endregion
    Console.ReadLine();
    #endregion
```
Output also able to calculate the accuracy of an algorithm you created

# Sorting Algorithm
Explaining how each of the algorithm work
## 1. Singly Linked List Sort Algorithm
