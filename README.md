# leetcode-

## 关于数组的练习
### * leetcode704 35 
简单的二分查找，记住用用left+（right-left）>>1来代替（left+right）/2,还有左右left的格式
```java
while(left<=right){
            int mid=left+(rihgt-left)>>1;
            if(nums[mid]==target)
            return mid;
            if(nums[mid]>target)
            right=mid-1;
            if(nums[mid]<target)
            left=mid+1;
        }
```
### * leetcode 69
求x的平方根是可以用二分查找的,并且注意符号位的问题，不能用long res=mid*mid，而是直接用（long）mid*mid与x进行比较
```java
while(l<=r){
            int mid=l+((r-l)>>1);
            if((long)mid*mid==x)
            return mid;
            if((long)mid*mid>x)
            r=mid-1;
            if((long)mid*mid<x)
            l=mid+1;
        }
```
### * leetcode27 26
删除重复元素用快慢指针做
```java
for(int fast=0;fast<nums.length;fast++){
            if(nums[fast]!=val){
                nums[slow++]=nums[fast];
            }
        }
```
### * leetcode 844
利用一个特殊变量skip来表示是不是需要跳过，来用双指针，用来进行两个东西进行判断的操作

### * leetcode 209
`给定一个含有 n 个正整数的数组和一个正整数 target 。
找出该数组中满足其和 ≥ target 的长度最小的 连续子数组 [numsl, numsl+1, ..., numsr-1, numsr] ，并返回其长度。如果不存在符合条件的子数组，返回 0 。
`
这题主要用快慢指针也可以用滑动窗口做。
