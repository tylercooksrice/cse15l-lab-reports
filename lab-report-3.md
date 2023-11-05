### Lab Report 3 ###


**Part 1**

*Fail inducing input*

```
import static org.junit.Assert.*;
import org.junit.*;

public class ArrayTests {
	@Test 
	public void testReverseInPlace1() {
    int[] input1 = { 3, 2, 5 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 5, 2, 3 }, input1);
	}
```

*Non-fail inducing input*
```
import static org.junit.Assert.*;
import org.junit.*;

public class ArrayTests {
  @Test 
	public void testReverseInPlace2() {
    int[] input1 = { };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{  }, input1);
	}
```

*Output of running tests*
![Image](input.png)

*before bug fix*
```
public class ArrayExamples {
  // Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
    
  }
```

*after bug fix*
```
public class ArrayExamples {
  // Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length / 2; i += 1) {
      int temp = arr[i]; // swap numbers
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = temp;
    }
  }
```

**Part 2**
---





