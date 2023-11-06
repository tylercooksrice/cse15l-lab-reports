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

4. grep -rl
```
$ grep -rl "people"
911report/chapter-1.txt
911report/chapter-10.txt
911report/chapter-11.txt
911report/chapter-12.txt
911report/chapter-13.1.txt
911report/chapter-13.2.txt
911report/chapter-13.3.txt
911report/chapter-13.4.txt
911report/chapter-13.5.txt
911report/chapter-2.txt
911report/chapter-3.txt
911report/chapter-5.txt
911report/chapter-6.txt
911report/chapter-7.txt
911report/chapter-8.txt
911report/chapter-9.txt
911report/preface.txt
biomed/1468-6708-3-1.txt
biomed/1468-6708-3-4.txt
biomed/1468-6708-3-7.txt
biomed/1471-2105-2-9.txt
biomed/1471-2105-3-16.txt
biomed/1471-2148-2-15.txt
biomed/1471-2156-2-1.txt
biomed/1471-2172-2-10.txt
biomed/1471-2180-1-31.txt
biomed/1471-2202-4-3.txt
biomed/1471-2210-1-10.txt
biomed/1471-2253-2-4.txt
biomed/1471-2288-2-4.txt
biomed/1471-2288-3-9.txt
biomed/1471-2296-3-19.txt
biomed/1471-2296-3-3.txt
biomed/1471-230X-2-17.txt
biomed/1471-2334-1-10.txt
biomed/1471-2334-2-24.txt
biomed/1471-2350-2-12.txt
biomed/1471-2350-2-2.txt
biomed/1471-2350-3-9.txt
biomed/1471-2407-1-13.txt
biomed/1471-2407-3-18.txt
biomed/1471-2407-3-5.txt
biomed/1471-2458-2-16.txt
biomed/1471-2458-2-25.txt
biomed/1471-2458-2-6.txt
biomed/1471-2458-3-11.txt
biomed/1471-2458-3-2.txt
biomed/1471-2458-3-20.txt
biomed/1471-2458-3-5.txt
biomed/1471-2466-2-4.txt
biomed/1472-6815-2-3.txt
biomed/1472-684X-1-5.txt
biomed/1472-6882-1-10.txt
biomed/1472-6882-1-7.txt
biomed/1472-6882-2-5.txt
biomed/1472-6882-3-1.txt
biomed/1472-6904-2-5.txt
biomed/1472-6947-3-5.txt
biomed/1472-6947-3-8.txt
biomed/1472-6963-1-11.txt
biomed/1472-6963-1-8.txt
biomed/1472-6963-3-1.txt
biomed/1472-6963-3-13.txt
biomed/1472-6963-3-6.txt
biomed/1475-2875-1-14.txt
biomed/1475-2875-2-10.txt
biomed/1475-2883-2-11.txt
biomed/1475-2891-2-1.txt
biomed/1475-925X-2-11.txt
biomed/1475-9276-1-3.txt
biomed/1476-069X-2-2.txt
biomed/1476-069X-2-4.txt
biomed/1476-069X-2-9.txt
biomed/1476-072X-2-3.txt
biomed/1476-072X-2-4.txt
biomed/1476-511X-2-3.txt
biomed/1477-7525-1-9.txt
biomed/ar387.txt
biomed/ar750.txt
biomed/bcr567.txt
biomed/cc1529.txt
biomed/cc713.txt
biomed/gb-2002-3-12-research0082.txt
biomed/gb-2002-3-9-research0046.txt
government/About_LSC/Comments_on_semiannual.txt
government/About_LSC/commission_report.txt
government/About_LSC/conference_highlights.txt
government/About_LSC/CONFIG_STANDARDS.txt
government/About_LSC/diversity_priorities.txt
government/About_LSC/LegalServCorp_v_VelazquezOpinion.txt
government/About_LSC/ODonnell_et_al_v_LSCdecision.txt
government/About_LSC/ONTARIO_LEGAL_AID_SERIES.txt
government/About_LSC/Progress_report.txt
government/About_LSC/reporting_system.txt
government/About_LSC/Special_report_to_congress.txt
government/About_LSC/State_Planning_Report.txt
government/About_LSC/State_Planning_Special_Report.txt
government/About_LSC/Strategic_report.txt
government/Alcohol_Problems/DraftRecom-PDF.txt
government/Alcohol_Problems/Session3-PDF.txt
government/Alcohol_Problems/Session4-PDF.txt
government/Env_Prot_Agen/final.txt
government/Env_Prot_Agen/jeffordslieberm.txt
government/Env_Prot_Agen/ro_clear_skies_book.txt
government/Env_Prot_Agen/tech_adden.txt
government/Env_Prot_Agen/tech_sectiong.txt
government/Gen_Account_Office/ai00134.txt
government/Gen_Account_Office/ai9868.txt
government/Gen_Account_Office/d01145g.txt
government/Gen_Account_Office/d01376g.txt
government/Gen_Account_Office/d01591sp.txt
government/Gen_Account_Office/d0269g.txt
government/Gen_Account_Office/d02701.txt
government/Gen_Account_Office/d03232sp.txt
government/Gen_Account_Office/d03273g.txt
government/Gen_Account_Office/d03419sp.txt
government/Gen_Account_Office/gg96118.txt
government/Gen_Account_Office/GovernmentAuditingStandards_yb2002ed.txt
government/Gen_Account_Office/im814.txt
government/Gen_Account_Office/InternalControl_ai00021p.txt
government/Gen_Account_Office/June30-2000_gg00135r.txt
government/Gen_Account_Office/May1998_ai98068.txt
government/Gen_Account_Office/Oct15-2001_d0224.txt
government/Gen_Account_Office/og96022.txt
government/Gen_Account_Office/og97038.txt
government/Gen_Account_Office/og97039.txt
government/Gen_Account_Office/og98041.txt
government/Gen_Account_Office/Paper_Walker11-2002_acpro122.txt
government/Gen_Account_Office/pe1019.txt
government/Gen_Account_Office/Sept14-2002_d011070.txt
government/Gen_Account_Office/Sept27-2002_d02966.txt
government/Gen_Account_Office/Statements_Feb28-1997_volume.txt
government/Gen_Account_Office/Testimony_cg00010t.txt
government/Gen_Account_Office/Testimony_d01609t.txt
government/Gen_Account_Office/Testimony_Jul15-2002_d02940t.txt
government/Gen_Account_Office/Testimony_Jul17-2002_d02957t.txt
government/Media/5_Legal_Groups.txt
government/Media/agency_expands.txt
government/Media/Aid_Gets_7_Million.txt
government/Media/All_May_Have_Justice.txt
government/Media/Anthem_Payout.txt
government/Media/Assuring_Underprivileged.txt
government/Media/Attorney_gives_his_time.txt
government/Media/Avoids_Budget_Cut.txt
government/Media/A_helping_hand.txt
government/Media/A_Perk_of_Age.txt
government/Media/balance_scales_of_justice.txt
government/Media/Barnes_new_job.txt
government/Media/Barnes_Volunteers.txt
government/Media/Barr_sharpening_ax.txt
government/Media/Boone_legal_service.txt
government/Media/Bridging_legal_aid_gap.txt
government/Media/BusinessWire.txt
government/Media/Butler_Co_attorneys.txt
government/Media/CommercialAppealMemphis2.txt
government/Media/Commercial_Appeal.txt
government/Media/Coup_Reshapes_Legal_Aid.txt
government/Media/Crains_New_York_Business.txt
government/Media/defend_yourself.txt
government/Media/Disaster_center.txt
government/Media/Do-it-yourself_divorce.txt
government/Media/Domestic_violence_aid.txt
government/Media/Domestic_Violence_Ruling.txt
government/Media/Donald_Hilliker.txt
government/Media/Entities_Merge.txt
government/Media/Eviction_law.txt
government/Media/Farm_workers.txt
government/Media/Federal_agency.txt
government/Media/Few_who_need.txt
government/Media/Fire_Victims_Sue.txt
government/Media/Firm_to_the_Poor_Needs_Help.txt
government/Media/FortWorthStarTelegram.txt
government/Media/Free_Legal_Assistance.txt
government/Media/Free_legal_service.txt
government/Media/Funding_cuts_force.txt
government/Media/Funds_Shortage.txt
government/Media/Ginny_Kilgore.txt
government/Media/Good_guys_reward.txt
government/Media/grants_fail_to_come.txt
government/Media/Greedy_Generous.txt
government/Media/GreensburgDailyNews.txt
government/Media/Hard_to_Get.txt
government/Media/Helping_Out.txt
government/Media/help_rent-to-own_tenants.txt
government/Media/Higher_court.txt
government/Media/IOLTA_INTEREST_RATE.txt
government/Media/Justice_for_all.txt
government/Media/Kiosks_for_court_forms.txt
government/Media/Law-school_grads.txt
government/Media/Law_Award_from_College.txt
government/Media/Law_Schools.txt
government/Media/Legal-aid_chief.txt
government/Media/Legal_Aid_attorney.txt
government/Media/Legal_Aid_campaign.txt
government/Media/Legal_Aid_in_Clay_County.txt
government/Media/Legal_Aid_looks_to_legislators.txt
government/Media/Legal_Aid_Society.txt
government/Media/Legal_hotline.txt
government/Media/Legal_services_for_poor.txt
government/Media/Legal_system_fails_poor.txt
government/Media/less_legal_aid.txt
government/Media/Library_Lawyers.txt
government/Media/Lindsays_legacy.txt
government/Media/Local_Attorneys.txt
government/Media/Lockyer_Warns.txt
government/Media/Low-income_children.txt
government/Media/Major_Changes.txt
government/Media/man_on_national_team.txt
government/Media/Marylands_Legal_Aid.txt
government/Media/New_funding_sources.txt
government/Media/New_Online_Resources.txt
government/Media/NJ_Legal_Services.txt
government/Media/Nonprofit_Buys.txt
government/Media/not_accessible_to_disabled.txt
government/Media/Oregon_Poor.txt
government/Media/Owning_a_Piece.txt
government/Media/Paralegal_Honored.txt
government/Media/Poor_Lacking_Legal_Aid.txt
government/Media/Poverty_Lawyers.txt
government/Media/predatory_loans.txt
government/Media/Pro-bono_road_show.txt
government/Media/Program_Lodges.txt
government/Media/pro_bono_efforts.txt
government/Media/Pro_Bono_Services.txt
government/Media/Raising_the_Bar.txt
government/Media/Rental_rules.txt
government/Media/Retirement_Has_Its_Appeal.txt
government/Media/RoanokeTimes.txt
government/Media/Self-Help_Website.txt
government/Media/Service_Agency.txt
government/Media/Supporting_Legal_Center.txt
government/Media/Survey.txt
government/Media/Targeting_Domestic_Violence.txt
government/Media/Terrorist_Attack.txt
government/Media/Texas_Lawyer.txt
government/Media/Texas_Supreme_Court.txt
government/Media/The_Bend_Bulletin.txt
government/Media/The_Columbian.txt
government/Media/The_State_of_Pro_Bono.txt
government/Media/Too_Crucial_to_Take_Cut.txt
government/Media/Towson_Attorney.txt
government/Media/Understanding.txt
government/Media/Unusual_Woodburn.txt
government/Media/Using_Tech_Tools.txt
government/Media/Valley_Needing_Legal_Services.txt
government/Media/Volunteers_Step_Up.txt
government/Media/Weak_economy.txt
government/Media/Wilmington_lawyer.txt
government/Media/Wingates_winds.txt
government/Media/Workers_aid_center.txt
government/Media/Working_for_Free.txt
government/Post_Rate_Comm/Cohenetal_DeliveryCost.txt
government/Post_Rate_Comm/Cohenetal_RuralDelivery.txt
government/Post_Rate_Comm/Gleiman_gca2000.txt
government/Post_Rate_Comm/Mitchell_6-17-Mit.txt
government/Post_Rate_Comm/Mitchell_RMVancouver.txt
government/Post_Rate_Comm/ReportToCongress2002WEB.txt
plos/journal.pbio.0020012.txt
plos/journal.pbio.0020028.txt
plos/journal.pbio.0020040.txt
plos/journal.pbio.0020046.txt
plos/journal.pbio.0020047.txt
plos/journal.pbio.0020052.txt
plos/journal.pbio.0020053.txt
plos/journal.pbio.0020054.txt
plos/journal.pbio.0020063.txt
plos/journal.pbio.0020064.txt
plos/journal.pbio.0020071.txt
plos/journal.pbio.0020101.txt
plos/journal.pbio.0020112.txt
plos/journal.pbio.0020116.txt
plos/journal.pbio.0020121.txt
plos/journal.pbio.0020140.txt
plos/journal.pbio.0020145.txt
plos/journal.pbio.0020146.txt
plos/journal.pbio.0020148.txt
plos/journal.pbio.0020150.txt
plos/journal.pbio.0020156.txt
plos/journal.pbio.0020161.txt
plos/journal.pbio.0020164.txt
plos/journal.pbio.0020183.txt
plos/journal.pbio.0020187.txt
plos/journal.pbio.0020190.txt
plos/journal.pbio.0020214.txt
plos/journal.pbio.0020232.txt
plos/journal.pbio.0020262.txt
plos/journal.pbio.0020263.txt
plos/journal.pbio.0020272.txt
plos/journal.pbio.0020306.txt
plos/journal.pbio.0020310.txt
plos/journal.pbio.0020311.txt
plos/journal.pbio.0020347.txt
plos/journal.pbio.0020348.txt
plos/journal.pbio.0020353.txt
plos/journal.pbio.0020404.txt
plos/journal.pbio.0020439.txt
plos/journal.pbio.0020440.txt
plos/journal.pbio.0030024.txt
plos/journal.pbio.0030032.txt
plos/journal.pbio.0030050.txt
plos/journal.pbio.0030051.txt
plos/journal.pbio.0030056.txt
plos/journal.pbio.0030097.txt
plos/journal.pbio.0030105.txt
plos/journal.pbio.0030129.txt
plos/pmed.0010008.txt
plos/pmed.0010010.txt
plos/pmed.0010022.txt
plos/pmed.0010023.txt
plos/pmed.0010024.txt
plos/pmed.0010029.txt
plos/pmed.0010039.txt
plos/pmed.0010042.txt
plos/pmed.0010052.txt
plos/pmed.0010056.txt
plos/pmed.0010058.txt
plos/pmed.0010068.txt
plos/pmed.0020002.txt
plos/pmed.0020005.txt
plos/pmed.0020007.txt
plos/pmed.0020016.txt
plos/pmed.0020020.txt
plos/pmed.0020023.txt
plos/pmed.0020024.txt
plos/pmed.0020036.txt
plos/pmed.0020039.txt
plos/pmed.0020040.txt
plos/pmed.0020045.txt
plos/pmed.0020050.txt
plos/pmed.0020059.txt
plos/pmed.0020062.txt
plos/pmed.0020067.txt
plos/pmed.0020068.txt
plos/pmed.0020071.txt
plos/pmed.0020090.txt
plos/pmed.0020098.txt
plos/pmed.0020099.txt
plos/pmed.0020104.txt
plos/pmed.0020116.txt
plos/pmed.0020117.txt
plos/pmed.0020123.txt
plos/pmed.0020140.txt
plos/pmed.0020146.txt
plos/pmed.0020160.txt
plos/pmed.0020181.txt
plos/pmed.0020182.txt
plos/pmed.0020189.txt
plos/pmed.0020194.txt
plos/pmed.0020196.txt
plos/pmed.0020198.txt
plos/pmed.0020200.txt
plos/pmed.0020208.txt
plos/pmed.0020209.txt
plos/pmed.0020210.txt
plos/pmed.0020216.txt
plos/pmed.0020231.txt
plos/pmed.0020232.txt
plos/pmed.0020237.txt
plos/pmed.0020238.txt
plos/pmed.0020246.txt
plos/pmed.0020247.txt
plos/pmed.0020249.txt
plos/pmed.0020272.txt
plos/pmed.0020278.txt
```
This command shows all the files in the directory of technical that has the word "people" in it. This command can be useful because it shows all the files in the
directory that has the word "people" in it, which can be helpful in locating the files that have "people."

```
$ grep -rl "tower" chapter-1.txt
chapter-1.txt
```
This command for the file displays if this word is in the file or not. It is useful because sometimes the text file has alot of words, so by using this command,
we are able to see if this file has that word or not.


