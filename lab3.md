# CSE 15L Lab Report 3
## `find` command
**`find file type -iname "path"`**
This finds the path without considering uppercase or lowercase. It prevents you from typing extra uppercase letters. 


Example 1: 
```
weiting@Emilys-MacBook-Air docsearch % find technical/government/Media -type f
 -iname "fa*"
technical/government/Media/families_saved.txt
technical/government/Media/Farm_workers.txt
```
This returns the files in Media that consists "fa" in it. 


Example 2: 
```
weiting@Emilys-MacBook-Air docsearch % find technical/government/Media -type f -iname "*ge*"
technical/government/Media/Federal_agency.txt
technical/government/Media/Targeting_Domestic_Violence.txt
technical/government/Media/City_Council_Budget.txt
technical/government/Media/Law_Award_from_College.txt
technical/government/Media/agency_expands.txt
technical/government/Media/FY_04_Budget_Outlook.txt
technical/government/Media/Funds_Shortage.txt
technical/government/Media/BergenCountyRecord.txt
technical/government/Media/Court_Keeps_Judge_From.txt
technical/government/Media/Avoids_Budget_Cut.txt
technical/government/Media/Assuring_Underprivileged.txt
technical/government/Media/Service_Agency.txt
technical/government/Media/Hard_to_Get.txt
technical/government/Media/Major_Changes.txt
technical/government/Media/Program_Lodges.txt
technical/government/Media/Entities_Merge.txt
technical/government/Media/A_Perk_of_Age.txt
technical/government/Media/Greedy_Generous.txt
technical/government/Media/Aid_Gets_7_Million.txt
```
This returns the files in Media that consists "ge" in it. 

This command is found in this [Link](https://www.youtube.com/watch?v=KCVaNb_zOuw).
I looked up "find command-line options" on youtube. 

**`find file -name file-name -type d/f`**
This finds the directories in the specific directory that consists a certain name. It not only helps you find files but also directories too. 


Example 1: 
```
weiting@Emilys-MacBook-Air docsearch % find technical -name biomed -type d
technical/biomed
```
There's a directory named biomed in the techinical directory so it returns this directory. 

Example 2: 
```
weiting@Emilys-MacBook-Air docsearch % find technical -name biomed -type f
```
There's no "file" named biomed in this directory so it returns nothing.

This command is found in this [Link](https://www.youtube.com/watch?v=skTiK_6DdqU).
I looked up "find command-line options" on youtube. 


**`find directory -type filetype -mmin +time`**
This returns the files modified within a certain period of time. It helps you find files that are modified around a certain time. 

Example 1: 
```
weiting@Emilys-MacBook-Air docsearch % find . -type f -mmin +1 -mmin -5
```
It didn't return anything because non of the files were modified more than 1 minute ago but less than 5 minutes ago. 

Example 2:
```
weiting@Emilys-MacBook-Air docsearch % find . -type f -mtime -10
./find-results.txt
./count-txts.sh
./biomed-sizes.txt
./.git/objects/02/eedd72994ffb39aa23d64205f2719c131636fe
./.git/objects/b3/a5d9e617964de69c1182f9e9f39cc28454b57c
./.git/objects/bc/57964156eee9dcd314f519bc392808b80e3dce
./.git/objects/c8/8ce76017d970ae70a554206e467e45af937859
./.git/objects/1f/b07518f4181fbbf1332117c50c414815a3a770
./.git/objects/19/1c52c38c714c1411f268d3164771cc5a0f12fa
./.git/objects/72/f00a2fbdfbea4b624e110982416286390b6e03
./.git/objects/09/c6544185b496f44014f9d5faebaaa22e3ae864
./.git/objects/08/e4c5d696d4cace3733a8e0178b31f7d71a5f53
./.git/objects/de/6b86e83d1f32a681a0a6d48bfef8d5c9e4f6d7
./.git/objects/e6/9de29bb2d1d6434b8b29ae775ad8c2e48c5391
./.git/logs/HEAD
./.git/logs/refs/heads/main
./.git/logs/refs/remotes/origin/HEAD
./.git/logs/refs/remotes/origin/main
./.git/logs/refs/remotes/upstream/HEAD
./.git/refs/heads/main
./.git/refs/remotes/origin/HEAD
./.git/refs/remotes/origin/main
./.git/refs/remotes/upstream/HEAD
./.git/index
./.git/COMMIT_EDITMSG
./.git/FETCH_HEAD
./grep-results.txt
./test.sh
./start.sh
./technical/find-results.txt
./technical/grep-results.txt
./plos-sizes.txt
```
These files were modified less than 10 days ago.

This command is found in this [Link](https://www.youtube.com/watch?v=KCVaNb_zOuw).
I looked up "find command-line options" on youtube. 

**`find files | xargs wc`**
This finds the files in a directory and takes in each argument and counts the number of lines, words, and characters in each files.
It's useful because you don't need to type that many commands. 

Example 1: 
```
weiting@Emilys-MacBook-Air docsearch % find technical/government/About_LSC | x
args wc
wc: technical/government/About_LSC: read: Is a directory
     139    1061    7083 technical/government/About_LSC/LegalServCorp_v_VelazquezSyllabus.txt
    1131    7162   47991 technical/government/About_LSC/Progress_report.txt
    1480   10196   67527 technical/government/About_LSC/Strategic_report.txt
     400    3025   20130 technical/government/About_LSC/Comments_on_semiannual.txt
     758    6431   41409 technical/government/About_LSC/Special_report_to_congress.txt
     331    1961   13558 technical/government/About_LSC/CONFIG_STANDARDS.txt
    3798   34774  223414 technical/government/About_LSC/commission_report.txt
     469    4467   28121 technical/government/About_LSC/LegalServCorp_v_VelazquezDissent.txt
     606    5398   34008 technical/government/About_LSC/ONTARIO_LEGAL_AID_SERIES.txt
     462    4231   27109 technical/government/About_LSC/LegalServCorp_v_VelazquezOpinion.txt
     566    3401   23451 technical/government/About_LSC/diversity_priorities.txt
     344    2761   17770 technical/government/About_LSC/reporting_system.txt
    3270   22995  152067 technical/government/About_LSC/State_Planning_Report.txt
     285    2075   13682 technical/government/About_LSC/Protocol_Regarding_Access.txt
     130     964    6118 technical/government/About_LSC/ODonnell_et_al_v_LSCdecision.txt
     367    1989   13828 technical/government/About_LSC/conference_highlights.txt
     556    4504   29963 technical/government/About_LSC/State_Planning_Special_Report.txt
   15092  117395  767229 total
```

Example 2: 
```
weiting@Emilys-MacBook-Air docsearch % find technical/biomed -name "*3.txt" | xargs wc
     562    3749   29678 technical/biomed/1471-2350-4-3.txt
     364    2430   19344 technical/biomed/1471-2156-2-3.txt
     686    4516   35409 technical/biomed/1472-6882-3-3.txt
     480    3913   27937 technical/biomed/1471-2407-2-3.txt
     339    2096   16843 technical/biomed/rr73.txt
     897    6041   48482 technical/biomed/1472-6807-2-3.txt
     772    5893   43442 technical/biomed/1471-2121-3-13.txt
     830    6283   46406 technical/biomed/1471-2229-2-3.txt
     973    7299   57158 technical/biomed/gb-2002-3-9-research0043.txt
     564    3550   27970 technical/biomed/1471-2091-2-13.txt
     410    3430   24168 technical/biomed/1472-6785-1-3.txt
     591    4328   32793 technical/biomed/ar93.txt
     350    2640   19181 technical/biomed/bcr583.txt
     949    7007   55102 technical/biomed/1477-7827-1-13.txt
     461    3444   25697 technical/biomed/1472-6750-1-13.txt
     414    2857   22501 technical/biomed/1472-6920-1-3.txt
     367    2761   20492 technical/biomed/1476-0711-2-3.txt
    1424    7522   63280 technical/biomed/gb-2003-4-7-r43.txt
     471    3326   25964 technical/biomed/1471-2474-2-3.txt
     574    4591   33886 technical/biomed/1471-2415-3-3.txt
     347    1795   14626 technical/biomed/1472-6769-1-3.txt
     428    2704   22668 technical/biomed/cc3.txt
     477    3599   26713 technical/biomed/1475-9276-1-3.txt
     360    2509   19639 technical/biomed/1471-230X-2-23.txt
     274    2036   15141 technical/biomed/1471-2229-3-3.txt
     298    2173   16482 technical/biomed/cc1843.txt
     446    3709   25954 technical/biomed/1471-2431-3-3.txt
    1016    7421   55468 technical/biomed/1471-213X-3-3.txt
     687    5014   39297 technical/biomed/1471-2407-3-3.txt
     549    4140   31625 technical/biomed/1471-2164-4-23.txt
     675    5274   39354 technical/biomed/1471-213X-1-3.txt
     457    2775   21552 technical/biomed/1471-2156-3-3.txt
     621    4565   34691 technical/biomed/1471-2466-2-3.txt
     682    4418   33145 technical/biomed/1478-7954-1-3.txt
     364    2851   20162 technical/biomed/1471-2229-1-3.txt
     494    3495   26286 technical/biomed/1476-069X-1-3.txt
     470    3364   25132 technical/biomed/1471-2164-3-13.txt
     402    2984   20593 technical/biomed/1471-2474-3-3.txt
     346    2743   19761 technical/biomed/1472-6920-2-3.txt
     290    1871   14731 technical/biomed/ar383.txt
     594    4045   32679 technical/biomed/1472-6815-2-3.txt
     536    3916   30360 technical/biomed/cc103.txt
    1614   11081   88698 technical/biomed/gb-2002-3-12-research0083.txt
     719    3835   31355 technical/biomed/1471-2180-3-13.txt
     542    3555   29911 technical/biomed/1471-2458-2-3.txt
     611    4109   32569 technical/biomed/cc303.txt
     227    1654   12557 technical/biomed/cc713.txt
     387    2738   21061 technical/biomed/1471-230X-3-3.txt
     536    3807   29768 technical/biomed/1476-072X-2-3.txt
     800    6060   46108 technical/biomed/1471-2172-2-3.txt
     605    4616   33815 technical/biomed/1471-2091-3-23.txt
     726    5249   39369 technical/biomed/1477-7827-1-43.txt
     367    2665   19066 technical/biomed/1472-6750-2-13.txt
     611    4637   35079 technical/biomed/1471-2202-3-3.txt
     302    2073   15618 technical/biomed/1476-4598-2-3.txt
     648    3604   27708 technical/biomed/1472-6874-2-13.txt
     641    5416   37814 technical/biomed/1471-2105-4-13.txt
     255    1717   12826 technical/biomed/1471-5945-3-3.txt
     537    4002   29139 technical/biomed/1471-2091-3-13.txt
     794    5641   43955 technical/biomed/bcr273.txt
     524    2554   20694 technical/biomed/1471-2164-3-23.txt
     611    3981   30646 technical/biomed/1471-2180-1-33.txt
     400    3219   22954 technical/biomed/1471-5945-1-3.txt
     563    3918   31098 technical/biomed/1471-2407-2-33.txt
     803    5352   41339 technical/biomed/1471-2199-3-3.txt
     370    2633   20388 technical/biomed/1472-6963-3-13.txt
     562    4222   32319 technical/biomed/1471-2164-4-13.txt
     642    4560   35587 technical/biomed/1471-5945-2-13.txt
     352    2949   20230 technical/biomed/1471-2407-2-23.txt
     432    3293   23790 technical/biomed/1475-2867-3-3.txt
     382    2683   20943 technical/biomed/1472-6793-3-3.txt
     599    4105   32602 technical/biomed/1471-2164-3-33.txt
     351    2405   17695 technical/biomed/1475-925X-2-3.txt
     585    4107   30804 technical/biomed/bcr303.txt
     573    4169   30792 technical/biomed/1471-2105-3-23.txt
     337    2523   19700 technical/biomed/gb-2002-3-5-research0023.txt
     204    1526   11287 technical/biomed/cc973.txt
     137     799    6297 technical/biomed/1471-2334-3-13.txt
     364    2699   20447 technical/biomed/1471-2199-2-3.txt
     420    2901   21898 technical/biomed/1476-4598-1-3.txt
     616    4530   35797 technical/biomed/1477-7827-1-23.txt
    1209    5760   47668 technical/biomed/1471-2105-3-3.txt
     546    3858   30961 technical/biomed/1471-2202-2-3.txt
     408    3057   23183 technical/biomed/1476-511X-2-3.txt
     708    4895   37156 technical/biomed/1471-2121-4-3.txt
     678    4044   31808 technical/biomed/gb-2002-3-10-research0053.txt
     979    6248   45044 technical/biomed/1471-2148-3-3.txt
     702    4539   36535 technical/biomed/1471-213X-1-13.txt
     626    3748   28019 technical/biomed/gb-2000-1-2-research0003.txt
     458    3192   24615 technical/biomed/1471-2474-3-23.txt
     306    2106   16141 technical/biomed/1471-2210-3-3.txt
     296    2166   16882 technical/biomed/1468-6708-3-3.txt
     405    3186   23825 technical/biomed/cc343.txt
     484    3735   28483 technical/biomed/1471-2296-3-3.txt
     745    4092   32938 technical/biomed/1471-2202-4-3.txt
     466    3146   25094 technical/biomed/gb-2001-2-12-research0053.txt
     551    3668   28049 technical/biomed/1471-2180-2-13.txt
     462    3015   23484 technical/biomed/1471-2407-1-13.txt
     416    3076   23526 technical/biomed/1478-1336-1-3.txt
     542    3786   28252 technical/biomed/1471-2210-1-3.txt
     397    2807   21318 technical/biomed/1476-9433-1-3.txt
     397    2970   21797 technical/biomed/1471-2334-1-13.txt
     248    1794   14165 technical/biomed/1471-2121-2-3.txt
   56069  389552 2984458 total
```
I found this command here [Link](https://ucsd-cse15l-s23.github.io/week/week4/) cause it was taught in class. 
