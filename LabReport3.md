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
![Image](LabReport3-symptom.jpg) <br>
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
<br>

This fix addresses the issue in the code because the original method assigns values from the newly created `newArray` into the original `arr`, then it returns the original variable `arr`. This causes the method to always return an array full of zeros due to the default int value in integer arrays being zero. The method was changed by instead assigning `arr` values to `newArray` then returning `newArray` to reverse the array.

Part 2 - Researching Commands : grep command
---
grep -m (prompted ChatGPT with "grep command options" - It outputted 12 different commands you can use grep with) <br>
```
// -m example 1
dpoedyasmara@Daniels-MacBook-Pro docsearch % grep -m 3 health technical/biomed/1468-6708-3-1.txt
        Many healthy older adults report gradual weight gain
        most robust health as we age. It has been suggested that
        quality of life or years of healthy life (YHL) in the
```
```
// -m example 2
dpoedyasmara@Daniels-MacBook-Pro docsearch % grep -m 3 blood technical/biomed/1468-6708-3-7.txt
          as a first-line blood pressure agent for patients with
          Willebrand factor commensurate with blood pressure, but
          blood-pressure reduction and effects on cholesterol.
```

grep -c (prompted ChatGPT with "grep command options" - It outputted 12 different commands you can use grep with) <br>
```
// -c example 1
dpoedyasmara@Daniels-MacBook-Pro docsearch % grep -c cell technical/biomed/1468-6708-3-1.txt
4
```
```
// -c example 2
dpoedyasmara@Daniels-MacBook-Pro docsearch % grep -c blood technical/biomed/1468-6708-3-7.txt
12
```
grep -r (prompted ChatGPT with "grep command options" - It outputted 12 different commands you can use grep with) <br>
```
// -r example 1
dpoedyasmara@Daniels-MacBook-Pro docsearch % grep -r preface technical/911report
technical/911report/chapter-13.3.txt:                For its preface, the Plan quoted a memo Tenet had sent to the CIA's senior
technical/911report/chapter-3.txt:                prefaced the directions with a message:"From the American President down to the
```
```
// -r example 2
dpoedyasmara@Daniels-MacBook-Pro docsearch % grep -r astute technical/plos     
technical/plos/journal.pbio.0020071.txt:        convincing readers of the reality and cogency of evolution and evolution theory by astutely
technical/plos/pmed.0010034.txt:        yielded insights that revolutionized the field of endocrinology. More recently, the astute
```
