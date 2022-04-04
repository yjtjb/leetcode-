# leetcode-

## 关于数组的练习
### * leetcode704
简单的二分查找，记住用while就行
```java
while(left<=right){
            int mid=(left+right)/2;
            if(nums[mid]==target)
            return mid;
            if(nums[mid]>target)
            right=mid-1;
            if(nums[mid]<target)
            left=mid+1;
        }
```
