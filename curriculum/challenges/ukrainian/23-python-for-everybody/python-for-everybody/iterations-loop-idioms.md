---
id: 5e7b9f070b6c005b0e76f05e
title: 'Цикли: ідіоми циклів'
challengeType: 11
videoId: AelGAcoMXbI
bilibiliIds:
  aid: 334491369
  bvid: BV1tw411R7Mm
  cid: 376530765
dashedName: iterations-loop-idioms
---

# --questions--

## --text--

Нижче наведено код, який знаходить найменше значення у списку значень. Один з рядків містить помилку, яка не дозволяє коду працювати правильно. Який це рядок?

```python
smallest = None
print("Before:", smallest)
for itervar in [3, 41, 12, 9, 74, 15]:
    if smallest is None or itervar < smallest:
        smallest = itervar
        break
    print("Loop:", itervar, smallest)
print("Smallest:", smallest)
```

## --answers--

3

---

4

---

6

---

7

## --video-solution--

3

