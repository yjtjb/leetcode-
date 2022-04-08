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

### * leetcode 76 （重做） 4.8
对于其他要按顺序查找的子串，可以用map储存后，再减少的方式进行滑动窗口的判断
### * leetcode 904 (重做) 4.8
类似的滑动窗口的框架
```java
for(int j=0;j<n;j++){
//窗口的维护工作

while(){
//结果的更新
//左边窗口的移动动作
}
}
```

### * leetcode 59 55
对于螺旋输出或者输入矩阵可以采用left right top bottom这四个变量来限制他的输入输出，同时加入val在for中，判断熟不熟数字都输出完了
```java
while(val>0){
            for(int i=left;i<=right&&val>0;i++){
                result.add(matrix[top][i]);
                val--;
            }
            top++;
            for(int i=top;i<=bottom&&val>0;i++){
                result.add(matrix[i][right]);
                val--;
            }
            right--;
            for(int i=right;i>=left&&val>0;i--){
                result.add(matrix[bottom][i]);
                val--;
            }
            bottom--;
            for(int i=bottom;i>=top&&val>0;i--){
                result.add(matrix[i][left]);
                val--;
            }
            left++;
        }
```

数组更新完成
## 关于回溯的练习
