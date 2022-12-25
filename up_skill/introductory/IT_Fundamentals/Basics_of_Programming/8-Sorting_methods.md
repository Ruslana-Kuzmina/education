# Sorting Methods

## Bg O Notation

Big O notation is used to describe the complexity of algorithms or to predict the
effectiveness of a written block of code.

The ways to look at the efficiency of an algorithm include:

- worst-case scenario
- best-case scenario
- average-case scenario

In a worst-case scenario, an algorithm gets a data input that would take the
largest possible number of actions to process compared to other possible inputs
of the same size.

Basic rules for calculating an algorithm's Big O Notation as follows:

- Ignore constants: we are concerned only with those elements of the function that
  influence the order of growth.

- Certain terms "dominate" other terms (ignore low-order terms): we ignore low-order
  terms when they are dominated by high-order ones.

O(1), O(log n), O(n), O(n logn), O(n2), O(2n), O(n!)

Big O is called an **asymptotic** function since it takes care of the performance
of an algorithm at the limit, that is, when a lot of input data is entered into
it. It should also be noted that there are other asymptotic functions.

## Binary Search, Search in Array

Use several ways to fill arrays:

- **Assigning values to elements**: the values of some arrays are known in advance.
  For example, the number of days in each of the 12 months of the year, the business
  results of the previous year, etc. Such arrays with the available data are usually
  initialized at the time of declaring these arrays or by using an assignment operation.

- **User input**: a user can fill arrays with data entered from the keyboard.

- **Reading data from the files stored on a disk or from another input source**:
  a user can also fill arrays with the data read from a file. Some stock information
  or a school report card are examples of large amounts of data that are difficult
  to enter manually each time you start a program. Therefore, it is better to store
  them in files and read them into the application as needed.

There are several basic search algorithms in programming languages. The simplest,
but not the most efficient one, is a **linear** or **sequential** search. The search
is carried out by full sequential iteration over the array elements and by comparing
its values with a given key. The speed of the algorithm is quite low.

```C
#include <stdio.h>
#include <string.h>

int main()
{
    char *studentNames[8] = {"Smith","Johnson","Williams","Jones","Brown","Davis",
    "Miller","Wilson"};
    printf("Enter the name of the student: \n");
    char searchName[15];
    scanf("%s",searchName);
    int i = 0;
    for(i = 0; i < 8; i++)
    {
        if(strcmp(studentNames[i],searchName)==NULL)
        {
            printf("\nThe student %s is present in the class. \n", searchName);
            break;
        }
    }
    if(i==8)
    {
        printf("\nThe student %s is absent from class. \n", searchName);
    }
    return (0);
}
```

The result:

Enter the name of the student:
Davis
The student Davis is present in the class.

```Python
student_names = ["Smith","Johnson","Williams","Jones","Brown","Davis","Miller",
"Wilson"]
print("The list of the students is", student_names)
search_name = input("Enter the name of the student: ")

for ind, name in enumerate(student_names):
    if name == search_name:
       print("The student", search_name, " is present in the class.")
       break
else:
    print("The student", search_name, " is absent from class.")
```

The result:

The list of the students is ['Smith', 'Johnson', 'Williams', 'Jones', 'Brown',
'Davis', 'Miller', 'Wilson']
Enter the name of the student: Jones
The student Jones is present in the class.

Typically, a linear search is used for a single search in a small unsorted (unordered)
array. And this is the only and most efficient way to find an element in an unordered
array. The time complexity of the mentioned above algorithm is O(n). In other cases,
it is better and more efficient to sort the array first or (it's better) to keep
it sorted, and apply another search algorithm such as a binary (binary) search.

Consider the situation when we have a sorted array that contains unique numbers
of library cards, and we need to determine by the number whether a reader is
registered in the library. We can use a **binary** search. In this case, a search
is performed in a sorted array by repeatedly dividing the search interval in half.
In other words, let's first check the middle element of the array. If it is greater
than the desired value, then check the middle element of the second half; otherwise,
сheck the middle element only of the first half. We will repeat this procedure until
the required element is found, or until there are no unchecked elements. On average
and in the worst case,the time complexity of a binary search algorithm is O(log(n)).

The C Program with Iterative Implementation of Binary Search

```C
#include <stdio.h>

int binarySearch(int *libraryNum, int arrSize, int key) {
    int low, high, mid;
    low = 0;
    high = arrSize-1;
    while(low <= high) {
        mid = (low+high)/2;
        if(key < libraryNum[mid])
            high = mid-1;
        else if(key > libraryNum[mid])
            low = mid+1;
        else return mid;
    }
    return -1;
};

int main()
{
    int arrSize = 10;
    int libraryNum[] = {108,123,124,235,285,379,456,476,756,998};
    int requiredNum = -1;
    int result=-2;
    printf("To exit enter 0.\n");
    while(requiredNum!=0){
        printf("Enter the library card number: ");
        scanf("%d", &requiredNum);
        if (requiredNum==0)
            {
                printf("The search is over.");
            }
        else {
            if (requiredNum <0) {
                printf("\nYou entered an invalid customer library card number.\n");
            }
            else {
                result = binarySearch(libraryNum,arrSize,requiredNum);
                if (result==-1)
                {
                    printf("The entered library card number %d was not found in
                    the list.\n",requiredNum);
                }
                else{
                    printf("The entered library card number %d was found in the
                    list.\n",requiredNum);
                }
            }
        }
    }
    return 0;
}
```

The result:

To exit enter 0.
Enter the library card number: 555
The entered library card number 555 was not found in the list.
Enter the library card number: -124

You entered an invalid customer library card number.
Enter the library card number: 124
The entered library card number 124 was found in the list.
Enter the library card number: 0
The search is over.

Python

```Python
def binary_search(arr, left, right, elem):
    while left <= right:
        mid_index = (right + left) // 2
        if arr[mid_index] == elem:
            return arr[mid_index]
        elif arr[mid_index] < elem:
            left = mid_index+1
        else:
            right = mid_index-1
    return None

library_num = [108, 123, 124, 235, 285, 379, 456, 476, 756, 998]
print("The list of the library card numbers are", library_num)
required_num = int(input("Enter the library card number: "))
if required_num > 0:
    amount = binary_search(library_num, 0, len(library_num)-1, required_num)
    if amount is None:
        print("\nThe reader is not registered in the library.")
    else:
        print("The reader", amount, "is registered in the library and took book(s).")
else:
    print("You entered an invalid customer library card number.")
```

The result:

The list of the library card numbers are [108, 123, 124, 235, 285, 379, 456, 476,
756, 998]
Enter the library card number: 456
The reader 456 is registered in the library and took book(s).

## Different Sorts

**Sorting** is a process of ordering individual elements of a list according to
their proper rank, either in an ascending or descending order. The problem of
"sorting" (ordering) is one of the first interesting and complex problems in the
theory of algorithms. There are entire books devoted to techniques for sorting and
finding values.

Different types of sorting algorithms have different logic and different steps but
they are all based on:

- **Comparison operations**: sequential comparison of array elements (except radix
  sort).
- **Permutations**: the method that swaps out-of-order elements. The exchange
  continues until all elements are ordered.

The difference in sorting methods is what to sort, and what and in what order to
permit. Sorting algorithms can be implemented using any programming language, such
as C ++, C #, JAVA, Python, etc. In this topic, we will look at the classic basic
algorithms for ordering array elements.

Considering the algorithms, we will evaluate which algorithm works better. An
optimal algorithm is the one that solves a problem in the best way, implying that
there is no algorithm that does it better. There are many optimal algorithms that
have the same complexity, and the sorting problem can also be solved optimally in
many ways.

The purpose of sorting is to make it easier to later find items in an ordered
dataset. Sorting can be classified into:

- Internal sorting – a type of sorting algorithms or their implementations, in
  which the amount of RAM is sufficient to place a sorted array of data into it
  with random access to any cell and, in fact, to execute the algorithm no additional
  memory is used. In this case, sorting occurs as quickly as possible, since the
  speed of access to RAM is much higher than to peripheral devices (accordingly,
  the access time is much shorter).
- External sorting – a type of sorting of the data located on peripheral devices
  which does not fit into RAM, that is, when one of the internal sorts cannot be
  applied.

Internal sorting is basic for any external sorting algorithm - individual parts
of the data array are sorted in RAM and, using a special algorithm, are concatenated
into one array, sorted by a key.

Below we will consider a description of some sorting algorithms, the complexity,
number of comparisons and swaps, the need for additional memory, stability, and
applicability. A **stable** sort is a sort that does not change the relative order
of the sorted elements that have the same values, by which the sorting occurs.

### Buble sort

Bubble Sort is the simplest sorting algorithm. We compare pairs of adjacent elements
and swap them if they are not in the correct order. As a result of the first step,
it turns out that the largest element moves to the end of the array. At the second
stage, the second largest element following it moves to the penultimate place, and
so on.

To reduce the number of N iterations, if an array is partially sorted, we can use
a flag that keeps track of whether we have swapped any element in the last iteration.
If no elements have been swapped, this means that the array is already sorted and
you can stop iterating earlier. This turns bubble sort into an adaptive sort algorithm.

```C
#include <stdio.h>
#include <stdbool.h>

void bubbleSort(int arr[], int n)
{
   int i, j;
   int count = 0;
   bool needIteration = true;
   while(needIteration) {
       needIteration = false;
       for(i = 0; i < n-1; i++)
       {
           for(j = 0; j < n-i-1; j++)
           {
               if(arr[j] > arr[j+1])
               {
                   int temp = arr[j];
                   arr[j] = arr[j+1];
                   arr[j+1] = temp;
                   needIteration = true;
                   count++;
                }
            }
        }
    }
   printf("The number of permutations is %d. \n", count);
}

void showArray(int arr[], int size)
{
    int i;
    for(i=0; i < size; i++)
        printf("%d ", arr[i]);
    printf("\n");
}

int main()
{
    int libraryNum[] = {124,235,456,123,756,476,285,998,379,108};
    int n = sizeof(libraryNum)/sizeof(libraryNum[0]);

    printf("Initial array: \n");
    showArray(libraryNum, n);
    bubbleSort(libraryNum, n);
    printf("Sorted array: \n");
    showArray(libraryNum, n);
    return 0;
}
```

The result:

Initial array:
124 235 456 123 756 476 285 998 379 108
The number of permutations is 20.
Sorted array:
108 123 124 235 285 379 456 476 756 998

```Python
def bubble_sort(arr):
    count = 0
    need_iteration = 'true'
    while need_iteration == 'true':
        need_iteration = 'false'
        for i in range(len(arr)):
            for j in range(0, len(arr)-i-1):
                if arr[j] > arr[j+1]:
                    arr[j], arr[j+1] = arr[j+1], arr[j]
                    need_iteration = 'true'
                    count +=1
    print("The number of permutations is", count)

libraryNum = [124,235,456,123,756,476,285,998,379,108]
print("Initial array:", libraryNum)
bubble_sort(libraryNum)
print ("Sorted array:", libraryNum)
```

The result:

Initial array: [124, 235, 456, 123, 756, 476, 285, 998, 379, 108]
The number of permutations is 20
Sorted array: [108, 123, 124, 235, 285, 379, 456, 476, 756, 998]

You should choose the bubble sort when:

- an array is partially sorted as the bubble sort is adaptive
- an array to be sorted is relatively small
- a simple sorting implementation is desired
- there are limits on memory usage

### Insertion sort

Insertion sort iterates through an array and moves the desired value to the beginning
of the array. After the next position has been processed, we know that all positions
preceding it are sorted, but not the positions following it. This sort is "stable"
since identical elements will not change their order.

```C
#include <stdio.h>

void insertionSort(int arr[], int n)
{
   int i, j, keyItem;
   int count=0;
   for(i = 1; i < n; i++)
   {
       keyItem = arr[i];
       j = i - 1;
       while(j >= 0 && arr[j] > keyItem)
       {
           arr[j + 1] = arr[j];
            j = j - 1;
            count ++;
       }
       arr[j + 1] = keyItem;
   }
   printf("The number of permutations is %d. \n", count);
}

void showArray(int arr[], int size)
{
    int i;
    for(i=0; i < size; i++)
        printf("%d ", arr[i]);
    printf("\n");
}

int main()
{
    int libraryNum[] = {124,235,456,123,756,476,285,998,379,108};
    int n = sizeof(libraryNum)/sizeof(libraryNum[0]);

    printf("Initial array: \n");
    showArray(libraryNum, n);
    insertionSort(libraryNum, n);
    printf("Sorted array: \n");
    showArray(libraryNum, n);
    return 0;
}
```

The result:

Initial array:
124 235 456 123 756 476 285 998 379 108
The number of permutations is 20.
Sorted array:
108 123 124 235 285 379 456 476 756 998

```Python
def insertion_sort(arr):
    count = 0
    for i in range(1, len(arr)):
        key_item = arr[i]
        j = i-1
        while j >= 0 and key_item < arr[j]:
            arr[j + 1] = arr[j]
            j -= 1
            count +=1
        arr[j + 1] = key_item
    print("The number of permutations is", count)

library_num = [124,235,456,123,756,476,285,998,379,108]
print("Initial array:", library_num)
insertion_sort(library_num)
print ("Sorted array:", library_num)
```

The result:

Initial array: [124, 235, 456, 123, 756, 476, 285, 998, 379, 108]
The number of permutations is 20
Sorted array: [108, 123, 124, 235, 285, 379, 456, 476, 756, 998]

You should choose the insertion sort when:

- an array is partially sorted as the insertion sort is adaptive
- an array to be sorted is relatively small
- a simple sorting implementation is desired
- there are limits on memory usage

### Selection Sort

Selection sort is a kind of hybrid between the bubble sort and the insertion sort.
Like the bubble sort, this algorithm iterates over an array over and over, moving
one value to the correct position. The correct position for the selected element
is determined before moving to the next element in the array, and with each pass,
the unsorted part of the array is decreased by one element. However, unlike the
bubble sort, it selects the smallest unsorted value instead of the largest one.
As with the insertion sort, the sorted portion of the array is at the beginning
while in the bubble sort it is at the end.

Selection sort is NOT a stable sorting algorithm because equal elements are
re-arranged in the final sort order with relation to one another.

```C
#include <stdio.h>

void selectionSort(int arr[], int n)
{
   int i, j, min;
   int count=0;
   for(i = 0; i < n-1; i++)
   {
       min = i;
       for(j = i+1; j < n; j++)
       {
           if(arr[j] < arr[min])
           {
              min = j;
           }
        }
        int temp = arr[min];
        arr[min] = arr[i];
        arr[i] = temp;
        count++;
   }
   printf("The number of permutations is %d. \n", count);
}

void showArray(int arr[], int size)
{
    int i;
    for(i=0; i < size; i++)
        printf("%d ", arr[i]);
    printf("\n");
}

int main()
{
    int libraryNum[] = {124,235,456,123,756,476,285,998,379,108};
    int n = sizeof(libraryNum)/sizeof(libraryNum[0]);

    printf("Initial array: \n");
    showArray(libraryNum, n);
    selectionSort(libraryNum, n);
    printf("Sorted array: \n");
    showArray(libraryNum, n);
    return 0;
}
```

The result:

Initial array:
124 235 456 123 756 476 285 998 379 108
The number of permutations is 9.
Sorted array:
108 123 124 235 285 379 456 476 756 998def selection_sort(arr):
    for i in range(len(arr)):
        min = i
        for j in range(i + 1, len(arr)):
            if arr[min] > arr[j]:
                min = j
        arr[i], arr[min] = arr[min], arr[i]

library_num = [124,235,456,123,756,476,285,998,379,108]
print("Initial array:", library_num)
selection_sort(library_num)
print ("Sorted array:", library_num)

The result:

Initial array: [124, 235, 456, 123, 756, 476, 285, 998, 379, 108]
Sorted array: [108, 123, 124, 235, 285, 379, 456, 476, 756, 998]

```Python
def selection_sort(arr):
    for i in range(len(arr)):
        min = i
        for j in range(i + 1, len(arr)):
            if arr[min] > arr[j]:
                min = j
        arr[i], arr[min] = arr[min], arr[i]

library_num = [124,235,456,123,756,476,285,998,379,108]
print("Initial array:", library_num)
selection_sort(library_num)
print ("Sorted array:", library_num)
```

The result:

Initial array: [124, 235, 456, 123, 756, 476, 285, 998, 379, 108]
Sorted array: [108, 123, 124, 235, 285, 379, 456, 476, 756, 998]

You should choose the selection sort when:

- an array is not partially sorted, so even if an array is partially sorted, still
  each element is compared and there is no breaking out early
- an array to be sorted is relatively small
- a simple sorting implementation is desired
- there are limits on memory usage

### Heapsort

Heapsort is a comparison-based sorting technique based on the binary heap data
structure. This is similar to sorting by selection, where we first find the minimum
element and place the minimum element in the beginning. However, in this case, the
largest elements are usually placed in the nodes. We repeat the same process for
the rest of the elements. Heapsort combines the time efficiency of merge sort and
the storage efficiency of quicksort which will be discussed below.

You know that a complete binary tree is a binary tree in which every level, except
perhaps the last one, is completely filled, and all nodes are located as far left
as possible. A heap data structure is a binary tree with a specific structural
orientation, often known as a complete binary tree.

Heapsort is NOT a stable sorting algorithm because equal elements are rearranged
in the final sort order with relation to one another.

```C
#include <stdio.h>

 // Write a recursion function to find largest among root, left child, and right
 child
void heapify(int arr[], int n, int i) {
    int largest = i;
    int left = 2 * i + 1;
    int right = 2 * i + 2;

    if (left < n && arr[left] > arr[largest])
      largest = left;

    if (right < n && arr[right] > arr[largest])
      largest = right;

    if (largest != i) {// Swap and continue heapifying if root is not largest
        int temp = arr[i];
        arr[i] = arr[largest];
        arr[largest] = temp;
        heapify(arr, n, largest);
    }
  }

  void heapSort(int arr[], int n) {
    for (int i = n / 2 - 1; i >= 0; i--)// Build max heap
        heapify(arr, n, i);
    for (int i = n - 1; i >= 0; i--) {// Heap sort
        int temp = arr[0];
        arr[0] = arr[i];
        arr[i] = temp;
        heapify(arr, i, 0);// Heapify root element to get highest element at root
        again
    }
  }

void showArray(int arr[], int size)
{
    int i;
    for (i=0; i < size; i++)
        printf("%d ", arr[i]);
    printf("\n");
}

int main()
{
    int libraryNum[] = {124,235,456,123,756,476,285,998,379,108};
    int n = sizeof(libraryNum)/sizeof(libraryNum[0]);

    printf("Initial array: \n");
    showArray(libraryNum, n);
    heapSort(libraryNum, n);
    printf("Sorted array: \n");
    showArray(libraryNum, n);
    return 0;
}
```

The result:

Initial array:
124 235 456 123 756 476 285 998 379 108
Sorted array:
108 123 124 235 285 379 456 476 756 998

```Python
def heapify(arr, n, i):
      largest = i
      left = 2 * i + 1
      right = 2 * i + 2

      if left < n and arr[i] < arr[left]:
          largest = left

      if right < n and arr[largest] < arr[right]:
          largest = right

      if largest != i:
          arr[i], arr[largest] = arr[largest], arr[i]
          heapify(arr, n, largest)

def heap_sort(arr):
    for i in range(len(arr)//2,-1,-1):
        heapify(arr, len(arr), i)
    for i in range(len(arr)-1, 0, -1):
        arr[i], arr[0] = arr[0], arr[i]
        heapify(arr, i, 0)

library_num = [124,235,456,123,756,476,285,998,379,108]
print("Initial array:", library_num)
heap_sort(library_num)
print ("Sorted array:", library_num)
```

The result:

Initial array: [124, 235, 456, 123, 756, 476, 285, 998, 379, 108]
Sorted array: [108, 123, 124, 235, 285, 379, 456, 476, 756, 998]

You should choose the heapsort when:

- an array is partially sorted
- an array to be sorted is relatively small
- a simple sorting implementation is desired
- there are limits on memory usage

Above we have looked at linear algorithms that don't use extra memory but have
quadratic or nlogn complexity. Merge sort is an example of “divide and conquer”.

### Merge Sort

Merge sort is a sorting algorithm that orders lists (or other data structures
whose elements can only be accessed sequentially, such as streams) in a specific
order. To merge means to combine two (or more) sequences into one ordered sequence
by cyclically selecting the items currently available.

When sorting an array by merge, we split the array in half until each chunk is
one element long. Then these areas are returned to their place (merged) in the
correct order. For the algorithm to work, we must implement the operation of
recursively dividing an array into groups (Sort method) and merging in the correct
order (Merge method).

Merge sort is a stable sorting algorithm because equal elements are not rearranged
in the final sort order with relation to one another.

```C
#include <stdio.h>

 void merge(int items[], int left, int mean, int right) {
    int leftSize = mean - left + 1;
    int rightSize = right - mean;
    int leftArr[leftSize], rightArr[rightSize];
    for (int i = 0; i < leftSize; i++)
        leftArr[i] = items[left + i];
    for (int j = 0; j < rightSize; j++)
        rightArr[j] = items[mean + 1 + j];

  // Maintain current index of sub-arrays and main array
  int i = 0;
  int j = 0;
  int k = left;

  // Until we reach the end of either leftArr or rightArr, pick larger among
  // elements leftArr and rightArr and place them in the correct position at items[left..right]
  while(i < leftSize && j < rightSize) {
    if (leftArr[i] <= rightArr[j]) {
        items[k] = leftArr[i];
        i++;
        } else {
            items[k] = rightArr[j];
            j++;
            }
    k++;
  }
  while (i < leftSize) {
    items[k] = leftArr[i];
    i++;
    k++;
    }
    while (j < rightSize) {
        items[k] = rightArr[j];
        j++;
        k++;
        }
}

// Divide the array into two subarrays, sort them and merge them
void mergeSort(int arr[], int left, int right) {
    if (left < right) {
        int mean  = left + (right - left) / 2;
        mergeSort(arr, left, mean );
        mergeSort(arr, mean  + 1, right);
        merge(arr, left, mean , right);
        }
}

void showArray(int arr[], int size)
{
    int i;
    for (i=0; i < size; i++)
        printf("%d ", arr[i]);
    printf("\n");
}

int main()
{
    int libraryNum[] = {124,235,456,123,756,476,285,998,379,108};
    int n = sizeof(libraryNum)/sizeof(libraryNum[0]);

    printf("Initial array: \n");
    showArray(libraryNum, n);
    mergeSort(libraryNum, 0, n-1);
    printf("Sorted array: \n");
    showArray(libraryNum, n);
    return 0;
}
```

The result:

Initial array:
124 235 456 123 756 476 285 998 379 108
Sorted array:
108 123 124 235 285 379 456 476 756 998

```Python
def merge_sort(arr):
    if len(arr) > 1:
        mean = len(arr)//2
        left_arr = arr[:mean]
        right_arr = arr[mean:]
        merge_sort(left_arr)
        merge_sort(right_arr)

        i = j = k = 0
        while i < len(left_arr) and j < len(right_arr):
            if left_arr[i] < right_arr[j]:
                arr[k] = left_arr[i]
                i += 1
            else:
                arr[k] = right_arr[j]
                j += 1
            k += 1
        while i < len(left_arr):
            arr[k] = left_arr[i]
            i += 1
            k += 1

        while j < len(right_arr):
            arr[k] = right_arr[j]
            j += 1
            k += 1

library_num = [124,235,456,123,756,476,285,998,379,108]
print("Initial array:", library_num)
merge_sort(library_num)
print ("Sorted array:", library_num)
```

The result:

Initial array: [124, 235, 456, 123, 756, 476, 285, 998, 379, 108]
Sorted array: [108, 123, 124, 235, 285, 379, 456, 476, 756, 998]

You should choose the merge sort when:

- there is a need to implement external sorting
- an array is not partially sorted, so despite the fact that in the worst case
  scenario it will work faster than the linear one, in the best case scenario,
  its performance will be lower than that of the linear one
- there are no limits on memory usage

### Quicksort sort

Quicksort sort is one of the "divide and conquer" algorithms. It works by recursively
repeating the following steps:

- Select a key index and split an array into two parts by it. There are many ways
  to do this, random or rightmost (i.e. the last) element, for example.
- Move all elements greater than the key to the right side of the array, and all
  elements less than the key to the left side. The key element is now in the correct
  position - it is larger than any element on the left and smaller than any element
  on the right.
- Repeat the first two steps until the array is completely sorted.

Quicksort is not adaptive and not a stable sort.

Quicksort is significantly faster than other O(nlogn) algorithms, because its inner
loop can be efficiently implemented on most data structures, and in most real-world
data, it is possible to make design choices that minimize the probability of requiring
quadratic time.

```C
#include <stdio.h>

 int partition(int items[], int left, int right) {
    int key = items[right];
    int i = left - 1;
        for (int j = left; j < right; j++) {
            if (items[j] <= key) {
                i++;
                int temp = items[i];
                items[i] = items[j];
                items[j] = temp;
            }
        }
        int temp = items[i + 1];
        items[i + 1] = items[right];
        items[right] = temp;
        return (i + 1);
}

void quickSort(int arr[], int left, int right) {
    if (left < right) {
        int keyIndex = partition(arr, left, right);
        quickSort(arr, left, keyIndex - 1);// Sort the elements on the left of a
        key element
        quickSort(arr, keyIndex + 1, right);// Sort the elements on the right of
        a key element
        }
}

void showArray(int arr[], int size)
{
    int i;
    for (i=0; i < size; i++)
        printf("%d ", arr[i]);
    printf("\n");
}

int main()
{
    int libraryNum[] = {124,235,456,123,756,476,285,998,379,108};
    int n = sizeof(libraryNum)/sizeof(libraryNum[0]);

    printf("Initial array: \n");
    showArray(libraryNum, n);
    quickSort(libraryNum, 0, n-1);
    printf("Sorted array: \n");
    showArray(libraryNum, n);
    return 0;
}
```

The result:

Initial array:
124 235 456 123 756 476 285 998 379 108
Sorted array:
108 123 124 235 285 379 456 476 756 998

```Python
def partition(arr,left,right):
    i = ( left-1 )      # index of smaller element
    key = arr[right]    # a key element

    for j in range(left, right):
        if   arr[j] < key:
            i += 1
            arr[i],arr[j] = arr[j],arr[i]
    arr[i + 1],arr[right] = arr[right],arr[i + 1]
    return ( i+1 )

def quick_sort(arr,left,right):
    if left < right:
        key_index = partition(arr,left,right)
        quick_sort(arr,left,key_index - 1)
        quick_sort(arr,key_index + 1, right)

library_num = [124,235,456,123,756,476,285,998,379,108]
print("Initial array:", library_num)
quick_sort(library_num, 0, len(library_num) - 1)
print ("Sorted array:", library_num)
```

The result:

Initial array: [124, 235, 456, 123, 756, 476, 285, 998, 379, 108]
Sorted array: [108, 123, 124, 235, 285, 379, 456, 476, 756, 998]

You should choose the quicksort when:

- a fast sorting is desired
- there are no limits on memory usage or they are not very flexible

### Radix sort

Radix sort is a non-comparative sorting algorithm. It avoids comparison by creating
and distributing elements into buckets according to their radix. The array is
iterated over for several times, and the elements are rearranged depending on
which digit is in a certain bit. After processing the bits (all or almost all),
the array is ordered, and the bits can be processed in opposite directions - from
the least significant to the most significant, or vice versa.

There are 2 types of radix sort:

- Least Significat Digit Radix Sorts (LSD Radix sort)
  In the least significant digit radix sorts (LSD radix sort), sorting is based on
  the least significant digit. We move from the least significant digits to the
  most significant ones, and at each iteration, we distribute the array elements
  depending on which digit is contained in the digit (first, all the digits ending
  with 0, then ending with 1, ..., ending with 9). After the next distribution, we
  return the elements to the main array in the order in which the elements got into
  the classes during the next reallocation. A new sequence emerges. Then they are
  grouped by the next bit from the end, then by the next, etc. until all the digits
  are enumerated, from the lowest to the highest.

- Most Significant Digit Radix Sorts (MSD radix sort)
  In the most significant digit radix sorts (MSD radix sort), sorting is based on
  the most significant digit. We move from high-order bits to low-order ones, and
  at each iteration we distribute the array elements depending on which digit is
  contained in the bit (equal to 0, equal to 1, equal to 2, ... equal to 9). Each
  subgroup is processed separately, while radix sort is recursively applied to the
  next bit. MSD is somewhat more complex to implement than LSD, but it is also more
  efficient. Also, MSD, unlike LSD, is a robust algorithm.

To perform the radix sort, we use a **counting sort** as a subroutine. A counting
sort is an algorithm for sorting a collection of objects by keys (in our case, an
array by indexes) that counts the number of elements that each distinct key value
has. Its operation time linearly depends on the number of elements and the difference
between the maximum and minimum values of the keys; therefore, this sorting method
is used when all the elements to be sorted fall into a known, finite, and sufficiently
small range. The initial setup and first pass of the data for counting sort are
exactly the same as for the quicksort.

A counting sort is a stable sort. If, for example, we have a list of readers sorted
by last name, then a counting sort is used to sort by the number of books read, and
the final list will be sorted mainly by the number of books read; however, all
readers who have read the same number of books will still be sorted by last name.

LSD Radix sort

```C
#include <stdio.h>

int findMax(int arr[], int size) {
  int maxItem = arr[0];
  for (int i = 1; i < size; i++)
    if (arr[i] > maxItem)
      maxItem = arr[i];
  return maxItem;
}

void countingSort(int arr[], int size, int place) {
  int output[size + 1];
  int maxItem = (arr[0] / place) % 10;

  for (int i = 1; i < size; i++) {
    if (((arr[i] / place) % 10) > maxItem)
      maxItem = arr[i];
  }
  int count[maxItem + 1];

  for (int i = 0; i < maxItem; ++i)
    count[i] = 0;

  // Determine count of elements
  for (int i = 0; i < size; i++)
    count[(arr[i] / place) % 10]++;

  // Determine cummulative count
  for (int i = 1; i < 10; i++)
    count[i] += count[i - 1];

  // Place the elements in the correct place
  for (int i = size - 1; i >= 0; i--) {
    output[count[(arr[i] / place) % 10] - 1] = arr[i];
    count[(arr[i] / place) % 10]--;
  }

  for (int i = 0; i < size; i++)
    arr[i] = output[i];
}

void radixSort(int arr[], int size) {
  int maxItrm = findMax(arr, size);
  for (int place = 1; maxItrm / place > 0; place *= 10)
    countingSort(arr, size, place);
}

void showArray(int arr[], int size)
{
    int i;
    for (i=0; i < size; i++)
        printf("%d ", arr[i]);
    printf("\n");
}

int main()
{
    int libraryNum[] = {124,235,456,123,756,476,285,998,379,108};
    int n = sizeof(libraryNum)/sizeof(libraryNum[0]);

    printf("Initial array: \n");
    showArray(libraryNum, n);
    radixSort(libraryNum, n);
    printf("Sorted array: \n");
    showArray(libraryNum, n);
    return 0;
}
```

The result:

Initial array:
124 235 456 123 756 476 285 998 379 108
Sorted array:
108 123 124 235 285 379 456 476 756 998

```Python
def counting_sort(arr, place):
    size = len(arr)
    output = [0] * size
    count = [0] * 10

    # Determine count of elements
    for i in range(0, size):
        index = arr[i] // place
        count[index % 10] += 1

    # Determine cummulative count
    for i in range(1, 10):
        count[i] += count[i - 1]

    # Place the elements in the correct place
    i = size - 1
    while i >= 0:
        index = arr[i] // place
        output[count[index % 10] - 1] = arr[i]
        count[index % 10] -= 1
        i -= 1

    for i in range(0, size):
        arr[i] = output[i]

def radix_sort(arr):
    max_item = max(arr)
    place = 1
    while max_item // place > 0:
        counting_sort(arr, place)
        place *= 10

library_num = [124,235,456,123,756,476,285,998,379,108]
print("Initial array:", library_num)
radix_sort(library_num)
print ("Sorted array:", library_num)
```

The result:

Initial array: [124, 235, 456, 123, 756, 476, 285, 998, 379, 108]
Sorted array: [108, 123, 124, 235, 285, 379, 456, 476, 756, 998]

Task:

N people are taking part in the donut eating competition. To win, you need to eat
as many donuts as possible in 10 minutes. Display on the screen the result of 3
winners and the worst result. (Hint: The program allocates dynamic memory for an
array of n elements and requests the array from a keyboard. Try sorting the data
using different methods. The case when several participants ate the same number of
donuts should not be considered).

```C
#include <stdio.h>

int Menu();
void BubbleSort(int[], int);
void selectionSort(int[], int);
void InsertSort(int[], int);
void printArray(int[], int);

int main()
{
    int dounts[20];
    int size;

    printf("Enter the number of bidders:(more than 3): ");
    scanf("%d", &size);
    printf("\n");
    while (size < 3) {
        printf("The number of participants must be more than 3!\n");
        printf("Enter again.\n");
        scanf("%d", &size);
    }

    for (int i = 0; i < size; i++)
    {
        printf("Enter the number of donuts eaten by %d participant: ", i + 1);
        scanf("%d", &dounts[i]);
    }

    switch (Menu())
    {
        case 1:
            BubbleSort(dounts, size); break;
        case 2:
            InsertSort(dounts, size); break;
        case 3:
            selectionSort(dounts, size); break;
        default:
            printf("Incorrect choice.\n");
    }

    printArray(dounts, size);
    return 0;
}

void InsertSort(int array[], int size)
{
    int temp, j;
    for (int i = 1; i < size; i++)
    {
        temp = array[i];
        j = i - 1;
        while (array[j] < temp && j >= 0)
        {
            array[j + 1] = array[j];
            j -= 1;
        }
        array[j + 1] = temp;
    }
}

void BubbleSort(int array[], int size)
{
    int temp;
    for (int i = 0; i < size-1; i++) {
        for (int j = i; j < size; j++) {
            if (array[i] < array[j]) {
                temp = array[i];
                array[i] = array[j];
                array[j] = temp;
            }
        }
    }
}

void selectionSort(int array[], int size){
    int min, temp;
    for (int i = 0; i < size - 1; i++) {
        min = i;
        for (int j = i + 1; j < size; j++) {
            if (array[j] > array[min]) {
                min = j;
            }
        }
        temp = array[i];
        array[i] = array[min];
        array[min] = temp;
    }
}

void printArray(int array[], int size) {
    int flag = 0;
    int temp, i, how;
    for (i = 0; i < size && flag < 3; i++) {
        if (array[i] == array[i + 1]) {
            how = 1;
            temp = array[i];
            while (temp == array[i + 1]) {
                how++;
                ++i;
            }
            printf("%d participants took %d place with result - %d donuts.", how,
            ++flag, array[i]);
            printf("\n");
        }
        else {
            printf("The result of the participant who took %d place - %d donuts.\n",
            ++flag, array[i]);
        }
    }
    if ((i != size) && (size > 3)) {
        printf("The worst result corresponds to %d donuts.\n", array[size - 1]);
    }
    printf("\n");
}

int Menu() {
    int choice = 0;
    printf("\t1 - Outputting the result using Bubble sort.\n");
    printf("\t2 - Outputting the result using Insert sort.\n");
    printf("\t3 - Outputting the result using Selection sort.\n");
    scanf("%d", &choice);
    while (choice<1 || choice >3){
        printf("Incorrect choice. Enter again:");
        scanf("%d", &choice);
    }
    return choice;
}
```

Result:

Enter the number of bidders: (more than 3): 6

Enter the number of donuts eaten by 1 participant: 14
Enter the number of donuts eaten by 2 participant: 12
Enter the number of donuts eaten by 3 participant: 16
Enter the number of donuts eaten by 4 participant: 10
Enter the number of donuts eaten by 5 participant: 12
Enter the number of donuts eaten by 6 participant: 14
        1 - Outputting the result using Bubble sort.
        2 - Outputting the result using Insert sort.
        3 - Outputting the result using Selection sort.
2
The result of the participant who took 1 place - 16 donuts.
2 participants took 2 place with result - 14 donuts.
2 participants took 3 place with result - 12 donuts.
The worst result corresponds to 10 donuts.

```Python
def bubble_sort(nums):
    swapped = True
    while swapped:
        swapped = False
        for i in range(len(nums) - 1):
            if nums[i] > nums[i + 1]:
                nums[i], nums[i + 1] = nums[i + 1], nums[i]
                swapped = True


def selection_sort(nums):
    for i in range(len(nums)):
        lowest_value_index = i
        for j in range(i + 1, len(nums)):
            if nums[j] < nums[lowest_value_index]:
                lowest_value_index = j
        nums[i], nums[lowest_value_index] = nums[lowest_value_index], nums[i]


def insertion_sort(nums):
    for i in range(1, len(nums)):
        item_to_insert = nums[i]
        j = i - 1
        while j >= 0 and nums[j] > item_to_insert:
            nums[j + 1] = nums[j]
            j -= 1
        nums[j + 1] = item_to_insert


bidders_num = int(input("Enter the number of bidders: "))
results = []
for n in range(bidders_num):
    results.append(int(input("Enter the number of donuts eaten by participant {}:
    ".format(n+1))))

sort_types = {
    1: bubble_sort,
    2: selection_sort,
    3: insertion_sort,
}

results = list(set(results))

sort_type = int(input("Enter sort type:\n"
                      "1 - Outputting the result using Bubble sort\n"
                      "2 - Outputting the result using Sort by selection method\n"
                      "3 - Outputting the result using Insert sort\n"))

sort_types[sort_type](results)
if len(results) > 2:
    print("First place went to the participant who ate {} donuts".format(results[-1]))
    print("Second place went to the participant who ate {} donuts".format(results[-2]))
    print("Third place went to the participant who ate {} donuts".format(results[-3]))
    print("The worst result corresponds to {} donuts".format(results[0]))
else:
    print("You've entered less than 3 unique results")
```

Result

Enter the number of bidders: 6
Enter the number of donuts eaten by participant 1: 14
Enter the number of donuts eaten by participant 2: 12
Enter the number of donuts eaten by participant 3: 16
Enter the number of donuts eaten by participant 4: 10
Enter the number of donuts eaten by participant 5: 12
Enter the number of donuts eaten by participant 6: 14
Enter sort type:
1 - Outputting the result using Bubble sort
2 - Outputting the result using Sort by selection method
3 - Outputting the result using Insert sort
1
First place went to the participant who ate 16 donuts
Second place went to the participant who ate 14 donuts
Third place went to the participant who ate 12 donuts
The worst result corresponds to 10 donuts

Task 2

To reverse a word, push the given word to stack (letter by letter) and then, pop
letters from the stack.

```C
#include <stdio.h>
#include <stdlib.h>

typedef struct item {
    char data;
    struct item *next;
} Item;

void Push(void);
void Display(void);
Item* top = NULL; //stack pointer

int main() {
    int n;
    printf("Enter the number of letters in the word\n");
    scanf("%d",&n);
    printf("Enter the word letter by letter\n");
    for(int i=0;i<n*2;i++)
    Push();
    printf("Reverse the word\n");
    Display();
    return 0;
}

void Push(void) {
    Item* p;
    p = (Item *)malloc(sizeof(Item));  //dynamic memory allocation
    scanf("%c", &p->data);

    p->next = top;
    top = p;
}

void Display(void)
{
   Item* p = top;
   if (p == NULL) printf("Stack is empty");
    else
    while (p != NULL) {
    printf("%c", p->data);
    p = p->next;
 }
}
```

```Python
word = input("Please enter the word or string: ")
stack = []
for letter in word:
    stack.append(letter)
reversed_word = ''
while stack:
    reversed_word += stack.pop()
print("Reversed: {}".format(reversed_word))
```
