# H-Index

> [프로그래머스 코딩테스트 연습 > 정렬 > H-Index](https://programmers.co.kr/learn/courses/30/lessons/42747)
> 출처: 프로그래머스 코딩 테스트 연습, https://programmers.co.kr/learn/challenges

- Level2
- 정렬 (출제 빈도: 높음, 평균 점수: 높음)

## 해결 과정

논문 Array를 높은수부터 정렬한다.
최대 H - Index 는 논문의 갯수까지이므로
논문 갯수와 인용된 논문의 수를 index 와 비교하여 H index를 찾는다.
index 를 찾지 못했으면 모두 같은 수이므로 count 를 return 한다.

## 코드 1

```Swift
func solution(_ citations:[Int]) -> Int {
    let sortedCit = [Int](citations.sorted().reversed())

    for i in (0..<sortedCit.count) {
        if i >= sortedCit[i] {
            return i
        }
    }
    return sortedCit.count
}
```