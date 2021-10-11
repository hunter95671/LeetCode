## 题目描述

在有序数组中找出两个数，使得和为给定的数 S。如果有多对数字的和等于 S，输出两个数的乘积最小的。

## 算法流程：

初始化： 双指针 i , j 分别指向数组 nums 的左右两端 （俗称对撞双指针）。
循环搜索： 当双指针相遇时跳出；

   计算和 s=nums[i]+nums[j]；
    若 s>targets ，则指针 j 向左移动，即执行 j=j−1 ；
    若 s<targets ，则指针 i 向右移动，即执行 i=i+1 ；
    若 s=targets ，立即返回数组 [nums[i], nums[j]]；

返回空数组，代表无和为 target 的数字组合。

## 代码：

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        int i = 0, j = nums.length - 1;
        while(i < j) {
            int s = nums[i] + nums[j];
            if(s < target) i++;
            else if(s > target) j--;
            else return new int[] { nums[i], nums[j] };
        }
        return new int[0];
    }
}
```

