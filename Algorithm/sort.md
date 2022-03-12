# 정렬 알고리즘

## Selection Sort

`i`번째 리스트의 값과 `i` 뒤에 있는 모든 값 중 제일 작은 것을 골라 서로 바꿈.

시간 복잡도: `O(n^2)`

### 파이썬 구현

```python
def selection_sort(list):
    l = list
    for i in range(len(l) - 1):
        minNum = l[i]
        index = i
        for j in range(i + 1, len(list)):
            if l[j] < minNum:
                minNum = l[j]
                index = j

        a = l[index]
        l[index] = l[i]
        l[i] = a

    return l
```

## Bubble Sort

`i`번째 리스트 값과 `i + 1`번째 리스트 값을 비교하여 i + 1번째 값이 더 작다면 서로 바꿈.

시간 복잡도: `O(n^2)`

> Selection Sort보다 리스트 교환량이 적어 더욱 연산량이 많다.

### 파이썬 구현

```python
def bubble_sort(list):
    l = list
    for i in range(len(l) - 1):
        for j in range(len(l) - 1):
            if l[j + 1] < l[j]:
                a = l[j + 1]
                l[j + 1] = l[j]
                l[j] = a

    return l
```

## Merge Sort

리스트를 1개가 될 떄 까지 반으로 자른 후, 리스트를 2개 씩 정렬해 감.

시간 복잡도: `O(nlogn)`

### 파이썬 구현

```python
def merge_sort(list):
    if(len(list) <= 1):
        return list

    mid = len(list) // 2
    list_one = merge_sort(list[:mid])
    list_two = merge_sort(list[mid:])

    i = j = 0
    merged_list = []
    while i < len(list_one) and j < len(list_two):
        if list_one[i] <= list_two[j]:
            merged_list.append(list_one[i])
            i += 1

        else:
            merged_list.append(list_two[j])
            j += 1

    merged_list += list_one[i:]
    merged_list += list_two[j:]

    return merged_list
```
