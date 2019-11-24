### Algorithm：每周至少做一个 leetcode 的算法题

Given a string, find the length of the longest substring without repeating characters.

Example 1:

Input: "abcabcbb"
Output: 3 
Explanation: The answer is "abc", with the length of 3. 
Example 2:

Input: "bbbbb"
Output: 1
Explanation: The answer is "b", with the length of 1.
Example 3:

Input: "pwwkew"
Output: 3
Explanation: The answer is "wke", with the length of 3. 
             Note that the answer must be a substring, "pwke" is a subsequence and not a substring.
       
~~~java
class Solution {
    public int lengthOfLongestSubstring(String s) {
        HashSet<Character> set = new HashSet();
        int n = s.length();
        int i=0,j=0,ans = 0;
        while (i<n && j<n){
            if (!set.contains(s.charAt(j))){
                set.add(s.charAt(j++));
                ans = Math.max(ans,j-i);
            }else{
                set.remove(s.charAt(i++));
            }
            
        }
        return ans;
    }
}
~~~      
 
### Review：阅读并点评至少一篇英文技术文章


### Tip：学习至少一个技术技巧

#### 学习了一下markdown的语法的时序图

时序图里面的概念

+ 标题
+ `-`表示实线
+ `--`表示虚线
+ `>`表示箭头
+ `Note over xxx` 表示在xxx时间线上增加备注
+ `Note right of xxx` 表示在xxx时间线右侧增加备注
+ `Note left of xxx` 表示在对象时间线左侧增加备注


### Share：分享一篇有观点和思考的技术文章

