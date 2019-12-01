### Algorithm：每周至少做一个 leetcode 的算法题
There are two sorted arrays nums1 and nums2 of size m and n respectively.

Find the median of the two sorted arrays. The overall run time complexity should be O(log (m+n)).

You may assume nums1 and nums2 cannot be both empty.
~~~java
class Solution {
    public double findMedianSortedArrays(int[] nums1, int[] nums2) {
        int m = nums1.length;
        int n = nums2.length;
        if(m > n){
            int[] tmp= nums1;
            nums1 = nums2;
            nums2 = tmp;
            m = nums1.length;
            n = nums2.length;
        }
        int imin = 0;int imax = m; int half = (m+n+1)/2;
        while(imin<=imax){
            int i = (imin + imax )/2;
            int j = half - i;
            if(i<imax && nums2[j-1] > nums1[i]){
                imin = i + 1;
            }else if(i > imin && nums1[i-1] > nums2[j]){
                imin = i - 1;
            }else {
                int maxLeft = 0;
                if(i == 0){
                    maxLeft = nums2[j-1];
                }else if(j == 0){
                    maxLeft = nums1[i-1];
                }else{
                    maxLeft = Math.max(nums1[i-1], nums2[j-1]);
                }
                if(m+n /2 ==1) return (double)maxLeft;

                int minRight = 0;
                if(i == m){
                    minRight = nums2[j];
                }else if(j == n){
                    minRight = nums1[i];
                }else{
                    minRight = Math.min(nums1[i], nums2[j]);
                }
                return (double) (minRight + maxLeft) /2;
            }
        }
        return 0.0;
}
~~~

### Review：阅读并点评至少一篇英文技术文章


### Tip：学习至少一个技术技巧

##### 学习了一下 Visual Studio code  工具，很轻便，支持很多插件，还在摸索中


### Share：分享一篇有观点和思考的技术文章
##### 最近在看《深入理解计算机系统》

