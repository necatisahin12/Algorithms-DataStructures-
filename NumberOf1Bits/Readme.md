 
 
# Number of 1 Bits!

Question
--

Write a function that takes an unsigned integer and returns the number of '1' bits it has (also known as the [Hamming weight](http://en.wikipedia.org/wiki/Hamming_weight)).

**Example 1:**

**Input:** n = 00000000000000000000000000001011
**Output:** 3
**Explanation:** The input binary string **00000000000000000000000000001011** has a total of three '1' bits.

Answer
--

```java
public int hammingWeight(int n) {
        int count=0;
        for(int i=0;i<32;i++){
        if(((n>>i)&1)==1){
                count++;
            }  
        }
        return count;        
    } 
```
           
     
   
Explanation
--

**BruteForce**

1.Convert to binary
2.Checked whether it is set or not. 

Lets think in brute force , we have to convert 11 to binary ,

Integer.toBinaryString(11)  ==1011 
or

``` java
public  static  void toBinary(int decimal){
 int binary[] = new  int[40];
 int index = 0;
 while(decimal > 0){
 binary[index++] = decimal%2;
 decimal = decimal/2;
 }
 for(int i = index-1;i >= 0;i--){
  System.out.print(binary[i]);
  }
  System.out.println();//new line
  }
  ```
 
 
```java
 public int hammingWeight(int n) {
        int count=0;
        String nBinaryString = Integer.toBinaryString(n);
        char [] carr =nBinaryString.toCharArray();
        for(int i=0;i<carr.length;i++){
        if(carr[i]=='1'){
            count++;
        }
        }
        return count;   
    }
   ```
    

  
  **Best Approach**
  
1.Check n&1 ==1
2. Slide n
  
Checking each bit in a number:

Each bit in the number is checked whether it is set or not. The number is bitwise AND with powers of 2, so if the result is not equal to zero, we come to know that the particular bit in the position is set.

1.Check n&1 ==1

Truth table 



**Time Complexity:** O(1)

   
 ``` java      
      public int hammingWeight(int n) {
        int count=0;
        for(int i=0;i<32;i++){
        if(((n>>i)&1)==1){
                count++;
            }  
        }
        return count;        
    }
```
![Screenshot_3](https://user-images.githubusercontent.com/34276366/116012320-854e2a00-a632-11eb-9e33-744f2a244371.png)



![two-input-and-gate-truth-table](https://user-images.githubusercontent.com/34276366/116000730-0dfca400-a5fa-11eb-9a6a-75464c3a1692.jpg)
