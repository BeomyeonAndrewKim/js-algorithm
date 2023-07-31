N개의 자연수가 입력되면 각 자연수의 자릿수의 합을 구하고, 그 합이 최대인 자연수를 출력 하는 프로그램을 작성하세요. 자릿수의 합이 같은 경우 원래 숫자가 큰 숫자를 답으로 합니다. 만약 235 와 1234가 동시에 답이 될 수 있다면 1234를 답으로 출력해야 합니다.
▣ 입력설명
첫 줄에 자연수의 개수 N(3<=N<=100)이 주어지고, 그 다음 줄에 N개의 자연수가 주어진다. 각 자연수의 크기는 10,000,000를 넘지 않는다.
▣ 출력설명
자릿수의 합이 최대인 자연수를 출력한다.
▣ 입력예제 1
7
128 460 603 40 521 137 123
▣ 출력예제 1 137

```javascript
function solution(n, k, card) {
  let answer;
  let tmp = new Set();

  for(let i = 0; i<n; i++) {
    for(let j =i+1; j<n;j++) {
      for(let k = j+1; k<n;k++) {
        tmp.add(card[i] + card[j] + card[k]);
      }
    }
  }
  let a= Array.from(tmp).sort((a,b) => b-a);
  answer = a[k-1];
  return answer;
};

const arr = [13, 15, 34, 23, 45, 65, 33, 11, 26, 42]

console.log(solution(10, 3, arr));
```