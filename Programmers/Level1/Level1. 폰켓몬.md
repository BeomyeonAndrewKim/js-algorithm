[Daily Algorithm_JavaScript] Level1.폰켓몬

### Question

#### Source https://school.programmers.co.kr/learn/courses/30/lessons/1845

### My solution

```javascript
function solution(nums) {
    const maxSelection = nums.length / 2;
    
    const elemSize = new Set(nums).size;
    
    return elemSize > maxSelection ? maxSelection : elemSize;
}
```


### Tio
```js
function solution(nums) {
    var answer = 0;
    const set = new Set(nums);
    const half = parseInt(nums.length / 2, 10);
    if (set.size > half) return half;
    else return set.size;
}
```
