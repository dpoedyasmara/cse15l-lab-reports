Part 1 - Bugs : Lab 4 method `reversed` bug
---
```
// input that induces a failure
@Test 
public void testReversedFail() {
  int[] input = {5,6,7};
  assertArrayEquals(new int[]{7,6,5}, ArrayExamples.reversed(input));
}
```
```
// input that doesn't induce a failure
@Test
public void testReversedNoFail() {
  int[] input = {0,0,0};
  assertArrayEquals(new int[]{0,0,0}, ArrayExamples.reversed(input));
}
```
Symptom Output
![Image](ChatServer_Code(smaller).png) <br>
```
// bugged method before
static int[] reversed(int[] arr) {
  int[] newArray = new int[arr.length];
  for(int i = 0; i < arr.length; i += 1) {
    arr[i] = newArray[arr.length - i - 1];
  }
  return arr;
}
```
```
// fixed method
static int[] reversed(int[] arr) {
  int[] newArray = new int[arr.length];
  for(int i = 0; i < arr.length; i += 1) {
  newArray[i] = arr[arr.length - i - 1];
  }
  return newArray;
}

```

Part 2 - Researching Commands : grep command
---
grep -c
grep -m
grep -r
