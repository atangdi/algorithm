# 数据中的重复数字
> 在一个长度为 n 的数组里的所有数字都在 0 到 n-1 的范围内。数组中某些数字是重复的，但不知道有几个数字是重复的，也不知道每个数字重复几次。请找出数组中任意一个重复的数字。
> 
> Input: {2, 3, 1, 0, 2, 5}  
> Output: 2

# 解题思路

## 解法一
 先对数组进行排序，然后判断相邻位置的数字是否相同，如果存在就对duplication赋值返回，否则就继续比较
 
 ``` java
public class Solution{

    public boolean duplicate(int[] numbers, int length, int[] duplication){

    Arrays.sort(numbers);
    for(int i =0 ; i <length-1; i++ ){
        if(numbers[i] == number[i+1]){
            duplication[0] = numbers[i];
            return true;
        }
    }
    return false;
    }

}
 ```
 时间复杂度 O(nlogn) 空间：O(1)

 ## 解法二

 数组的长度为n 切所有数字都在0到 n-1范围内，我们可以将每次遇到的数进行归位，当某一个数发现自己的位置被相同的数占用了，则出现重复了。
 ``` java
 public class Solution{
     public boolean duplicate(int[] nums, int length, int [] duplication){
         if( null == nums || length == 0) {
             return false;
         }

        for(int i = 0; i < length ; i++){
            while(nums[i] != i){
                if(nums[i] == nums[nums[i]]){
                    duplication[0] = num[i];
                    return true;
                }
                int temp = nums[i];
                nums[i] = nums[nums[i]];
                num[nums[i]] = temp;
            }
        }
        return
     }
 }
 ```

