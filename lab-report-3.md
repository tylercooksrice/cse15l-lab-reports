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
![Image](inputs.png)

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

1. grep -c
```
$ grep -c "that" chapter-1.txt
172
```
This command is showing the number of times "that" apppears in this text file and can be useful because the command would show 
the amount of times a word would appear in a specfic file.

```
$ grep -c "the" *.txt
chapter-1.txt:313
chapter-10.txt:336
chapter-11.txt:533
chapter-12.txt:804
chapter-13.1.txt:643
chapter-13.2.txt:467
chapter-13.3.txt:639
chapter-13.4.txt:1070
chapter-13.5.txt:1435
chapter-2.txt:526
chapter-3.txt:1831
chapter-5.txt:635
chapter-6.txt:1046
chapter-7.txt:861
chapter-8.txt:622
chapter-9.txt:1195
preface.txt:68
```
This command is showing the number of times "the" appears in all the text files in the 911report directory in the technical directory.
In addition, this command is useful because the command shows the recurrences of a specific word in all the text files within a directory.

2. grep -b
```
grep -b "Americans" chapter-2.txt
1115:            He claimed it was more important for Muslims to kill Americans than to kill other
1508:                in the world today and the worst terrorists are the Americans. Nothing could stop
4325:                shall-with the grace of Allah-prevail over the Americans." He went on to warn that
5336:                Americans-win thousands of followers and some degree of approval from millions more?
5536:                his message are largely unknown to many Americans. Seizing on symbols of Islam's
13517:                Americans have wondered, "Why do 'they' hate us?" Some also ask, "What can we do to
13850:                involving Muslims. Thus Americans are blamed when Israelis fight with Palestinians,
24682:            "All Americans must recognize that the face of terror is not the true face of Islam,"
44066:                Americans. The perpetrators are reported to have belonged to a group from southern
45177:                for training the Saudi National Guard. Five Americans and two officials from India
46016:                Americans were killed, and 372 were wounded. The operation was carried out
75813:                carried out the operations to hit Americans in Somalia." The report provided
77743:                enemies of Islam and to expel the Americans from the Gulf region. Two weeks after
79773:                Americans and 201 others, almost all Kenyans. About 5,000 people were injured. The
79970:                Americans. Interviewed later about the deaths of the Africans, Bin Ladin answered
80069:                that "when it becomes apparent that it would be impossible to repel these Americans
80564:                the Americans to liberate the holy places "is considered a crime,"he said,"let
```
This command shows the lines within a file that has the word "Americans" and lists the line number of the word found, which is useful as 
the command would help the user locate the line within the file to find the location of the line that contains the word given.
```
$ grep -b chapter-1.txt *
grep: 911report: Is a directory
grep: biomed: Is a directory
grep: government: Is a directory
grep: plos: Is a directory
```
This command shows which file within a directory is a directory and is useful because sometimes the user would not be able to see what other
directories exist within a directory.

3. grep -r
```
$ grep -r 'tower' 911report
911report/chapter-1.txt:    All on board, along with an unknown number of people in the tower, were killed instantly.
911report/chapter-1.txt:    All on board, along with an unknown number of people in the tower, were killed instantly.
911report/chapter-1.txt:    Reagan National controllers then vectored an unarmed National Guard C- 130H cargo aircraft, which had just taken off en route to Minnesota, to identify and follow the suspicious aircraft. The C-130H pilot spotted it, identified it as a Boeing 757, attempted to follow its path, and at 9:38, seconds after impact, reported to the control tower:"looks like that aircraft crashed into the Pentagon sir."
911report/chapter-1.txt:    FAA: That was another-it was evidently another aircraft that hit the tower. That's the latest report we have.
911report/chapter-1.txt:    The President and the Vice President The President was seated in a classroom when, at 9:05, Andrew Card whispered to him: "A second plane hit the second tower. America is under attack." The President told us his instinct was to project calm, not to have the country see an excited reaction at a moment of crisis. The press was standing behind the children; he saw their phones and pagers start to ring. The President felt 
he should project strength and calm until he could better understand what was happening.
911report/chapter-1.txt:    At 9:33, the tower supervisor at Reagan National Airport picked up a hotline to the Secret Service and told the Service's operations center that "an aircraft [is] coming at you and not talking with us." This was the first specific report to the Secret Service of a direct threat to the White House. No move was made to evacuate the Vice President at this time. As the officer who took the call explained, "[I was] about to push the alert button when the tower advised that the aircraft was turning south and approaching Reagan National Airport."
911report/chapter-13.2.txt:                were told by Boston Center that the second tower had been struck. At 9:12:54, the
911report/chapter-13.2.txt:            236. The 113th Wing first learned from the FAA tower at Andrews that the Secret
911report/chapter-13.2.txt:                Service wanted fighters airborne. The FAA tower had been contacted by personnel at
911report/chapter-13.5.txt:                outside of each tower was covered by a frame of 14-inch-wide steel columns; the
911report/chapter-13.5.txt:                and 82nd floors in both towers. For the doors being closed but unlocked, see Port
911report/chapter-13.5.txt:            6. For the towers' loss of power and the other effects, see New York City report,
911report/chapter-13.5.txt:                after the impact, see Commission analysis of conditions on tower floors and advice
911report/chapter-13.5.txt:                received by civilians in the towers based on (1) calls to NYPD 911 from or
911report/chapter-13.5.txt:                concerning people in the towers on September 11, 2001, and (2) transcripts of
911report/chapter-13.5.txt:                recorded calls to the Port Authority police desk from people in the towers on
911report/chapter-13.5.txt:                towers, see FDNY interview, transcript 8, Chief, Oct. 23, 2001; Port Authority
911report/chapter-13.5.txt:            201. Ironically, had the towers remained up longer, scores more first responders
911report/chapter-13.5.txt:                more PAPD officers on Church and Vesey were preparing to enter the towers.
911report/chapter-13.5.txt:                the two towers. In addition, it is possible that several of the eight companies for
911report/chapter-13.5.txt:            13. The collapse of the World Trade Center towers on the morning of September 11
911report/chapter-3.txt:                towers of the World Trade Center. This was not a suicide attack. The terrorists
911report/chapter-9.txt:                towers had 110 stories, were about 1,350 feet high, and were square; each wall
911report/chapter-9.txt:                occupied the towers, and 40,000 people passed through the complex.
911report/chapter-9.txt:            Each tower contained three central stairwells, which ran essentially from top to
911report/chapter-9.txt:            The towers lost power and communications capability. Generators had to be shut down
911report/chapter-9.txt:                of the towers' occupants via the stairwells took more than four hours.
911report/chapter-9.txt:                    tower.
911report/chapter-9.txt:                lobby of each tower at all times. He or she would be responsible for communicating
911report/chapter-9.txt:                people trapped above a fire in the towers.
911report/chapter-9.txt:                be placed instead in the lobby fire safety desk of each of the towers, making FDNY
911report/chapter-9.txt:                other tower. Some believed an incident had occurred in their building; others were
911report/chapter-9.txt:                tower, and stairwell A was reported to have been almost empty. Stairwell B was also
911report/chapter-9.txt:                point in the morning. But just before the tower collapsed, a team of NYPD ESU
911report/chapter-9.txt:                Tower lobby huddled to discuss strategy for the operations in the two towers. Of
911report/chapter-9.txt:                channel was functioning and being used by units in that tower. The senior chief in
911report/chapter-9.txt:                indirect ways to enter that tower, most often through the Marriott Hotel, or simply
911report/chapter-9.txt:                tower was possible. One senior chief did articulate his concern that upper floors
911report/chapter-9.txt:                tactical channel that the ESU teams climbing in the towers would use.
911report/chapter-9.txt:                towers, and on Liberty Street.
911report/chapter-9.txt:                roof of either tower. At about 9:30, one of the helicopters present advised that a
911report/chapter-9.txt:                helicopter never attempted to hover directly over the tower. Another helicopter did
911report/chapter-9.txt:                building. Prior to 9:59, no NYPD helicopter pilot predicted that either tower would
911report/chapter-9.txt:                tower's lobby, at the FDNY overall command post, and, at least for some period of
911report/chapter-9.txt:                thousands of civilians in evacuating the towers, even as incident commanders from
911report/chapter-9.txt:                had exited the tower. The civilians who were nearing the bottom of stairwell C were
911report/chapter-9.txt:                    tower.
911report/chapter-9.txt:                leave, as this tower could fall as well. The units then proceeded to exit onto West
911report/chapter-9.txt:                and the other ESU unit preparing to enter the tower. The ESU team on the 31st floor
911report/chapter-9.txt:                impact zone were able to evacuate the towers.
911report/chapter-9.txt:                general evacuation time for the towers dropped from more than four hours in 1993 to
911report/chapter-9.txt:                hazardous in some areas outside the towers.
911report/chapter-9.txt:                towers, civilians who were able to reach the stairs and descend were also stymied by
911report/chapter-9.txt:                information for individuals at and above the impact zone of the towers. The FDNY
911report/chapter-9.txt:                ordered both towers fully evacuated by 8:57, but this guidance was not conveyed to
911report/chapter-9.txt:                    tower.
911report/chapter-9.txt:                magnitude of 9/11. In addition, its mission that day lay largely outside the towers
911report/chapter-9.txt:                climbing in the towers, the vast majority of NYPD personnel were staged outside,
911report/chapter-9.txt:                after the tower's collapse, a helicopter pilot radioed that news. This transmission
911report/chapter-9.txt:                the fall of either tower before the South Tower collapsed, and no NYPD personnel
```
This command searches for towers in all the files in the directory and is useful to find all the words that match up within 
a directory and in which file.
```
$ grep -r 'tower' 911report/chapter-1.txt
    All on board, along with an unknown number of people in the tower, were killed instantly.
    All on board, along with an unknown number of people in the tower, were killed instantly.
    Reagan National controllers then vectored an unarmed National Guard C- 130H cargo aircraft, which had just taken off en route to Minnesota, to identify and follow the suspicious aircraft. The C-130H pilot spotted it, identified it as a Boeing 757, attempted to follow its path, and at 9:38, seconds after impact, reported to the control tower:"looks like that aircraft crashed into the Pentagon sir."
    FAA: That was another-it was evidently another aircraft that hit the tower. That's the latest report we have.
    The President and the Vice President The President was seated in a classroom when, at 9:05, Andrew Card whispered to him: "A second plane hit the second tower. America is under attack." The President told us his instinct 
was to project calm, not to have the country see an excited reaction at a moment of crisis. The press was standing behind the children; he saw their phones and pagers start to ring. The President felt he should project strength and calm until he could better understand what was happening.
    At 9:33, the tower supervisor at Reagan National Airport picked up a hotline to the Secret Service and told the Service's operations center that "an aircraft [is] coming at you and not talking with us." This was the first specific report to the Secret Service of a direct threat to the White House. No move was made to evacuate the Vice President at this time. As the officer who took the call explained, "[I was] about to push the alert button when the tower advised that the aircraft was turning south and approaching Reagan National Airport."
```
This command shows all the lines within a file that has the 'tower' within it and could be useful in finding specfic words in the file and their sentence.

4. grep 
```

```

```

```



