## 🧩 Problem : 01  
## **Problem Name : Majority Element**

---

### 📌 Problem Description  
Given an array of integers, find the **majority element**.  
The majority element is the element that appears **more than ⌊n / 2⌋ times** in the array.

---

### 💡 Algorithm  
1. Initialize `candidate = 0` and `count = 0`
2. Traverse the array:
   - If `count == 0`, assign current element as `candidate`
   - If current element equals `candidate`, increment `count`
   - Otherwise, decrement `count`
3. After traversal, `candidate` contains the majority element

---

### ⏱️ Complexity Analysis  
- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(1)`

---

## 💻 Code 1 : Without Pointer Object
```c
#include <stdio.h>

int main() {
    int n;
    printf("Enter array size: ");
    scanf("%d",&n);

    int arr[n];
    printf("Enter array elements:\n");
    for(int i=0;i<n;i++){
        scanf("%d",&arr[i]);
    }

    int candidate=0,count=0;

    for(int i=0;i<n;i++){
        if(count==0){
            candidate=arr[i];
            count=1;
        }
        else if(arr[i]==candidate){
            count++;
        }
        else{
            count--;
        }
    }

    printf("Majority Element: %d\n",candidate);
    return 0;
}
