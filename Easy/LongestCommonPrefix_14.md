14. Longest Common Prefix

Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string `""`.

**Example 1:**

**Input:** strs = ["flower","flow","flight"]
**Output:** "fl"

**Example 2:**

**Input:** strs = ["dog","racecar","car"]
**Output:** ""
**Explanation:** There is no common prefix among the input strings.

**Constraints:**

-   `1 <= strs.length <= 200`
-   `0 <= strs[i].length <= 200`
-   `strs[i]` consists of only lowercase English letters.
```typescript
function longestCommonPrefix(strs: string[]): string {

let sorted = strs.sort((a, b) => a.length - b.length);

let elem = sorted[0];

let shifted = sorted.filter(item => item !== elem)

if (!strs.length) return '';

for(let i=0;i <= sorted[0].length;i++){

if(shifted.every(x=>x.startsWith(elem)))return elem

else if(!shifted.every(x=>x.substring(0, 1).includes(elem.substring(0, 1))))return ""

else if(elem.length>=0) elem = elem.substring(0,elem.length-1);

else return ""

}

};

```
