### Question

##### 가장 긴 목걸이를 구하라!

> 주어진 `A`는 숫자가 나열되어있는 배열이다.
> index는 목걸이의 첫 번째 구슬 번호이고 A[index]는 목걸이의 그 다음 구슬 번호이다.
> A[0] = 5
> A[1] = 4
> A[2] = 0
> A[3] = 3
> A[4] = 1
> A[5] = 6
> A[6] = 2
> 구슬 번호를 잇다 보면 최종적으로 첫 번째 구슬 번호로 돌아오는데 이어진 구슬 번호 한 세트가 하나의 목걸이다.
> ex) [0, 5, 6, 2], [1, 4], [3]
> 가장 긴 목걸이의 길이를 반환하는 `solution`함수를 구하라.

### My solution

```javascript
function solution(A) {
  const beadsCount = [];
  A.forEach((el, index, arr) => {
    const beads = [index];
    makeBeads(beads, arr, el, beadsCount);
  });

  function makeBeads(beads, arr, el, beadsCount) {
    if (beads[0] === arr[el]) {
      beads.push(el);
      beadsCount.push(beads.length);
    } else {
      beads.push(el);
      makeBeads(beads, arr, arr[el], beadsCount);
    }
  }
  return Math.max(...beadsCount);
}

solution([5, 4, 0, 3, 1, 6, 2]);
```
