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
grep -m (used `man grep` in terminal then searched through the options) <be>
- This command displays the first specified number amount of lines in the file with your specified keyword.
```
// -m example 1
dpoedyasmara@Daniels-MacBook-Pro docsearch % grep -m 3 health technical/biomed/1468-6708-3-1.txt
        Many healthy older adults report gradual weight gain
        most robust health as we age. It has been suggested that
        quality of life or years of healthy life (YHL) in the
```
- This example searches through the `technical/biomed/1468-6708-3-1.txt` file for the first 3 instances of "health" and prints out these lines.
```
// -m example 2
dpoedyasmara@Daniels-MacBook-Pro docsearch % grep -m 3 cholesterol technical/biomed/1468-6708-3-7.txt
        surrogate endpoints such as cholesterol levels and
          blood-pressure reduction and effects on cholesterol.
```
- This command searches for the first 3 instances of "cholesterol" in `technical/biomed/1468-6708-3-7.txt` however it only displays 2 lines because there are less than 3 instances.
<br>

grep -c (used `man grep` in terminal then searched through the options) <br>
- This command returns the number of instances of the specified keyword in the file.
```
// -c example 1
dpoedyasmara@Daniels-MacBook-Pro docsearch % grep -c adult technical/biomed/1468-6708-3-7.txt 
0
```
- This example displays what is returned when there are no instances of the word. 
```
// -c example 2
dpoedyasmara@Daniels-MacBook-Pro docsearch % grep -c blood technical/biomed/1468-6708-3-7.txt
12
```
- This example returned 12, telling us that there are 12 instances of "blood" in the file `technical/biomed/1468-6708-3-7.txt`
<br>

grep -r (used `man grep` in terminal then searched through the options) <br>
- This command searches each file in the directory recursively.
```
// -r example 1
dpoedyasmara@Daniels-MacBook-Pro docsearch % grep -r preface technical/911report
technical/911report/chapter-13.3.txt:                For its preface, the Plan quoted a memo Tenet had sent to the CIA's senior
technical/911report/chapter-3.txt:                prefaced the directions with a message:"From the American President down to the
```
- This example shows how the word "preface" appeared in the files `technical/911report/chapter-13.3.txt` and `technical/911report/chapter-3.txt`, then prints the line it appears in.
```
// -r example 2
dpoedyasmara@Daniels-MacBook-Pro docsearch % grep -r mature technical/plos    
technical/plos/journal.pbio.0020419.txt:        Over the twenty years since the RNA Tie Club, molecular biology had matured. Francis
technical/plos/pmed.0020098.txt:        flaws. They do not take family history of premature coronary artery disease into account;
technical/plos/pmed.0020103.txt:          expression of Nkx6.1 or islet amyloid polypeptide, markers of mature pancreatic β-cells
technical/plos/pmed.0020103.txt:          + cells at stage 4 are post-mitotic, like mature pancreatic β-cells.
technical/plos/pmed.0020103.txt:        distinct from mature pancreatic islet β-cells; in other words, the insulin
technical/plos/pmed.0020103.txt:        + cells derived by our methods are not mature β-cells. For example,
technical/plos/pmed.0020103.txt:        as IPC insulin synthesis and stimulus–secretion coupling, the hallmark functions of mature
technical/plos/journal.pbio.0020187.txt:        implausible (though that conclusion may be premature, as I will summarise below), so it's
technical/plos/journal.pbio.0020150.txt:        premature use of fMRI in these contexts].”
technical/plos/journal.pbio.0020232.txt:        represent the completely mature form of the differentiated skeletal muscle cell). Their
technical/plos/pmed.0010029.txt:        years lost to premature death and disability.
technical/plos/pmed.0020061.txt:        extensive testing by manufacturers, including tests in immature animals. Unfortunately,
technical/plos/pmed.0020061.txt:        system discourages industry from conducting testing in immature animals because the
technical/plos/journal.pbio.0030131.txt:        muscle cells and myoblasts (immature muscle cells), and then collect the cells that are
technical/plos/journal.pbio.0030131.txt:        cells resident within the heart. Thus, the isolation of an immature cell from a heart does
technical/plos/pmed.0020198.txt:        Smoking is the single largest preventable cause of disease and premature death,
technical/plos/journal.pbio.0030050.txt:        Nde1 causes neurons to mature prematurely. This stops them dividing so
technical/plos/pmed.0010058.txt:        long-term complications, including kidney failure, blindness, nerve damage, and premature
technical/plos/pmed.0020212.txt:        However, it is not premature to inform patients that this work is advancing and that it
technical/plos/pmed.0020160.txt:        in public policy. Linked to poverty, decreased productivity, and premature death, tobacco
technical/plos/journal.pbio.0030056.txt:        Such requirements have allowed work on aDNA to move on and mature. Now, it's possible to
technical/plos/pmed.0020201.txt:        expression, surface antigens, and immunocytochemistry typical of the mature tissues. For
technical/plos/pmed.0020189.txt:        history of premature coronary artery disease is a major but underused risk factor. The
technical/plos/pmed.0010052.txt:        stopped prematurely [19]. Selective serotonin reuptake inhibitors are currently embroiled
technical/plos/journal.pbio.0030065.txt:        nomenclature as a mature service. It is only a matter of time and effort before we are able
technical/plos/pmed.0020018.txt:          Typical maturation and half-life of mature cellular holoAPP were observed, as was
technical/plos/pmed.0020018.txt:          of either drug, except that the fractional content of cellular mature holoAPP was
technical/plos/pmed.0020018.txt:          approximately 2-fold greater in the presence of drug (i.e., at 15 or 75 min chase, mature
technical/plos/pmed.0020018.txt:          APP in the presence of statin was approximately 310% of the level of immature APP at 
technical/plos/pmed.0020018.txt:          immature APP at 
technical/plos/pmed.0020018.txt:          elevated levels of intracellular mature holoAPP and causes retarded conversion of mature
technical/plos/pmed.0020018.txt:          excluding maturation toxicity as a mechanism underlying the altered levels of mature
technical/plos/journal.pbio.0020073.txt:        the field of nanotechnology matures.
technical/plos/pmed.0020182.txt:        are available in less than 15 min from the time of blood collection. In a mature
technical/plos/journal.pbio.0020161.txt:        particular, some scientists seemed concerned that their mature and respected system for
technical/plos/journal.pbio.0020028.txt:        “Compounds were pushed into the clinic prematurely.” Sirna began as the biotech startup
technical/plos/pmed.0020278.txt:        himself); the failure of primate studies to improve risks for birth defects and premature
technical/plos/pmed.0020268.txt:        pathogenic parasitized erythrocytes, sequestered in the capillaries and containing mature
technical/plos/pmed.0020268.txt:        with current thinking that sequestration of erythrocytes containing the mature forms of the
technical/plos/journal.pbio.0020206.txt:        ‘Retrotransposition’ describes the integration of reverse transcribed mature RNAs at
technical/plos/journal.pbio.0020206.txt:        functionality of a duplicated gene: for example, by introducing a premature stop codon or a
technical/plos/pmed.0010036.txt:        both the first and second STIs and then withdrew, and AC-05 restarted therapy prematurely
technical/plos/pmed.0020123.txt:            family history of premature CHD—were not captured in either data source. Also, neither
technical/plos/journal.pbio.0020013.txt:        in premature substrate release (Eytan et al. 1993; Lam et al. 1997; Thrower et al. 2000;
technical/plos/pmed.0020068.txt:        mature adult myofibers: by hormonal influences (e.g., thyroid hormone), but most
```
- This example shows us that this command will display every line containing that word even if there are multiple instances in a single file. It is seen that there were 5 instances of "mature" in the file `technical/plos/pmed.0020103.txt` so there were 5 lines printed for this file.
