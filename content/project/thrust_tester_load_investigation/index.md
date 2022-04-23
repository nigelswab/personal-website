---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Thrust Tester Load Investigation"
subtitle: ""
# Style sets the style of the banner and uses hugo-story styling
style: "style2 orient-left content-align-center image-position-center fullscreen
        color1 invert onload-image-fade-in onload-content-fade-right"
summary: "
<ul>
<li>While improving our thrust testing setup, we decided to evaluate how peak thrust for a given test speed is determined</li>
<li>It was found that an average thrust from a successful pass provides a more representative peak thrust value than the minimum thrust from a successful pass given cyclical thrust fluctuations</li>
<ul><li>It was also found that the LRT Thrust Tester provided less thrust fluctuation than the LST Thrust tester, essentially eliminating larger thrust oscillations</li></ul>
<li>It's recommended that the testing team continue to log high speed thrust passes to gather more data and investigate any odd fluctuations further</li>
</ul>
"
authors: []
tags: [co-op, testing, data-analysis]
categories: []
date: "2021-08-06"

start_date: "August 2021"
finish_date: "August 2021"

# Optional external URL for project (replaces project detail page).
external_link: ""

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
feature_image: "featured.jpg"
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Custom links (optional).
#   Uncomment and edit lines below to show custom links.
# links:
# - name: Follow
#   url: https://twitter.com
#   icon_pack: fab
#   icon: twitter

url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""
---
**Disclaimer:** *This was internal documentation that has been converted
from Zaber's internalwiki. Some information may have been removed, and
references to other wiki pages are not publicly available. This 
page may also contain some odd formatting.*

# Dev/R-Test and Fixture/LRT Thrust Speed/2021-08-06 - Thrust Speed High Speed Load Logging Investigation

| **Product**            | R-Test and Fixture |
|------------------------|--------------------|
| **Test Attributes**    | Thrust             |
| **Tester**             | Nigel              |
| **Plan Reviewed by**   | Nathan P           |
| **Report Reviewed by** | Nathan P           |
| **Test Date**          | 2021-08-06         |

## Abstract
_______________________________________
-   While improving our thrust testing setup, we decided to evaluate how peak thrust for a given test speed is determined
-   It was found that an average thrust from a successful pass provides a more representative peak thrust value than the minimum thrust from a successful pass given cyclical thrust fluctuations
    -   It was also found that the LRT Thrust Tester provided less thrust fluctuation than the LST Thrust tester, essentially eliminating larger thrust oscillations
-   It's recommended that the testing team continue to log high speed thrust passes to gather more data and investigate any odd fluctuations further

## Background
_______________________________________
-   We are currently in the process of improving our thrust speed tester/setup
-   Currently, the maximum thrust for a given speed is determined by taking the minimum load recorded in a successful thrust pass
    -   However, this may not be an ideal way of determining a stages thrust capacity at a given speed
    -   Therefore, the standard thrust speed script was modified to create "high speed logs" of the recorded load cell reading and elapsed time throughout the loop in the "move_and_detect_stall" method
        -   Results of the highest recorded successful pass, and the stalling pass, will be published in Resulty
        -   Depending on results, future modifications to the script may be made to include the ability to record high speed logs of either successful or stalling passes based on the settings defined by the config file
-   The LRT thrust tester has been modified to resemble the LST thrust tester (converted to peripheral) and now uses the same Python script
    -   LRT's should provide improved thrust testing capacity (speed, load, and travel) over the LST's
    -   It may be interesting to evaluate if there is any difference between load variation on the LRT vs. the LST thrust tester

## Purpose
_______________________________________
To gather data and evaluate the determination of maximum thrust in our thrust_speed.py scripts

## Method
_______________________________________
### Equipment

<table>
<colgroup>
<col style="width: 39%" />
<col style="width: 60%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>Test Equipment</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Devices:</td>
<td><ul>
<li>
X-LSM200B-E03 - 55350
</li>
<li>
X-LSQ150D-E01 - 60493
</li>
<li>
X-LSQ600A-E01 - 50144
</li>
</ul></td>
</tr>
<tr class="even">
<td>Firmware</td>
<td><ul>
<li>
LSM - 6.32.1601
</li>
<li>
LSQ - 7.22.10079
</li>
</ul></td>
</tr>
<tr class="odd">
<td>Load Cell:</td>
<td>250 lbs</td>
</tr>
<tr class="even">
<td>Spring Assembly #:</td>
<td><ul>
<li>
LSM200B: # 3 - 120 N
</li>
<li>
LSQ150D: # 3 - 120 N
</li>
<li>
LSQ600A: #1 - 817 N
</li>
</ul></td>
</tr>
<tr class="odd">
<td>Power Supply:</td>
<td>White BK Precision</td>
</tr>
</tbody>
</table>

### Settings

<table>
<colgroup>
<col style="width: 49%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>Test Settings</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Closed Loop:</td>
<td>Enabled</td>
</tr>
<tr class="even">
<td>Run current:</td>
<td>default</td>
</tr>
<tr class="odd">
<td>Test Voltage (V):</td>
<td>48 V</td>
</tr>
<tr class="even">
<td>Thrust limit (N):</td>
<td>Spring Maximum</td>
</tr>
<tr class="odd">
<td>Speed range (mm/s):</td>
<td><ul>
<li>
<p>LSM: 2 - 100</p>
</li>
</ul>
<ul>
<li>
<p>LSQ150D: 2 - 100</p>
</li>
<li>
<p>LSQ600A: 2 - 53</p>
</li>
</ul></td>
</tr>
<tr class="even">
<td>Number of data points:</td>
<td>10</td>
</tr>
<tr class="odd">
<td>Starting Force:</td>
<td>5 N</td>
</tr>
<tr class="even">
<td>Fine Force Increment:</td>
<td>1 N</td>
</tr>
</tbody>
</table>

### Code

-   [<u>thrust_speed.py</u>](https://gitlab.izaber.com/testing/general_testing_scripts/blob/master/torque_and_thrust/LST_tester/thrust_speed.py)
    -   Initial testing done/based off of LRT_thrust_high_speed branch with the commit hash of 78b8084b9a308a551bac0a268c6cc60abc716baf
-   [<u>Default LST Thrust Speed Config.yaml</u>](https://gitlab.izaber.com/testing/general_testing_scripts/blob/master/torque_and_thrust/LST_tester/Default%20LST%20Thrust%20Speed%20Config.yaml)

### Procedure
**Note:** *I was unable to export this section from the wiki*

{{< fancy_pics loc="fit"
               caption="Test Setup"
               content=""
               src="media/image1.jpeg" >}}

## Results and Analysis
_______________________________________
-   To view the raw data from this report, search this page's heading (Dev/R-Test and Fixture/LRT Thrust Speed/2021-08-06 - Thrust Speed High Speed Load Logging Investigation) in Resulty

### Initial Testing

-   Initial testing showed cyclical fluctuations around a fairly consistent thrust value at each speed.
    -   It was noted that these fluctuations were larger than desired, especially for the LSM, spurring further investigation
-   It was also found that the recording speed through a thrust pass was too slow (0.2-0.4 seconds between readings)
    -   As a result, the thrust_speed.py script was re-worked to increase reading speed
    -   A normalized\* thrust column was also added to aid with future comparisons/evaluations
        -   Thrust was normalized by dividing each recorded thrust value by that passes average thrust value (not actual normalization)
    -   Position of the stage was also added to the recorded value to aid with comparisons and evaluations

#### Details and Plots for Initial Testing

-   Initial tests with the LST Thrust Tester show that load varies fairly significantly throughout a run, but tends to vary around a fairly consistent level
    -   This means that an average of the pass, especially at lower speeds, is likely a better representation of the stages capabilities
    -   This also means that it may be worth investigating methods to smooth/dampen the load variation throughout a pass
        -   Too much fluctuation in load may cause premature stalls and result in lower representative results
-   Initial testing also showed that stalls happened primarily at the start of the pass
    -   These were all stage stalls, not load cell readings out of the threshold
    -   This could be due to stalling during acceleration (in which case, acceleration can be decreased to attain sustained thrust)
    -   This could also be due to simply overloading the stage, causing it to stall right away as it's limit has been reached
-   Subsequent testing was done with 5 data/speed points to reduce testing time and data "spam" in Resulty
-   It's also notable that time between measurements is 0.2-0.4 seconds, which is much longer than ideal (as seen in LSQ150D testing)
    -   This could lead to inaccurate or inconsistent measurements
    -   This could also pose a problem for preventing damage to stages and load cells when stage stall detection is delayed
    -   **The script was updated/optimized for recording speed, as detailed in [<u>Dev/R-Test and Fixture/LRT Thrust Speed#2021-08-09 - Move and Detect Stall Optimization</u>](https://iwiki.izaber.com/Dev/R-Test_and_Fixture/LRT_Thrust_Speed#2021-08-09_-_Move_and_Detect_Stall_Optimization)**
    -   The faster script was used for all testing after the initial LSQ150D testing
-   It's likely reasonable to return the average load from a thrust pass that hasn't stalled (instead of the minimum value)

<br>

### Cyclical Fluctuation Investigation - LST Thrust Tester

-   Tests were run with the updated thrust_speed.py script (with improved recording speed, normalized thrust values, and stage position readings)
-   It was found that the oscillations in thrust strongly correlate with stage position for the LSM200B and LSQ600A
    -   However, the larger oscillation's frequency (relative to position) don't seem to directly correlate with stage pitch
    -   Interestingly, the LSQ150D also showed a larger frequency at low speeds that wasn't seen at any other speed or stage

**LST Thrust Tester Speed Comparison**
_______________________________________

{{< div class="row justify-content-center" >}}
    {{< div class="col-8 col-lg-6" >}}
{{< fancy_pics loc="fit"
               caption="LSM200B"
               content=""
               src="media/image2.gif" >}}
    {{< divclose >}}
    {{< div class="col-8 col-lg-6" >}}
{{< fancy_pics loc="fit"
               caption="LSQ150D"
               content=""
               src="media/image3.gif" >}}
    {{< divclose >}}
    {{< div class="col-8 col-lg-6" >}}
{{< fancy_pics loc="fit"
               caption="LSQ600A"
               content=""
               src="media/image4.gif" >}}
    {{< divclose >}}
{{< divclose >}}

-   As can be seen below, it appears that the LSM200B and LSQ600A have a similar oscillations relative to stage position

    -   This suggests that the thrust tester may be the cause of these oscillation

{{< fancy_pics loc="fit"
               caption="LST Thrust Tester Stage Comparison"
               content=""
               src="media/image5.gif" >}}

-   It was also confirmed that the springs did not have a large effect on oscillations:

{{< fancy_pics loc="fit"
               caption="Spring Assembly Comparison"
               content=""
               src="media/image6.gif" >}}

<br>

### Cyclical Fluctuation Investigation - LRT Thrust Tester

-   When these tests were repeated on the LRT thrust tester, a noticeable improvement in thrust fluctuation can be seen on the LSM (with only ±\~2% thrust vs. ±\~7%)
    -   Larger oscillations on the LSQ's seem to also be removed/reduced, but with much less magnitude than the LSM
    -   The total span of thrust fluctuation actually remains fairly similar for the two LSQ's, with a slight improvement on the LSQ150D
-   This further suggests that the larger oscillations seen previously were a result of the LST Thrust Tester
-   However, there does seem to be some odd random fluctuation occurring on the LSQ600A, causing a larger span of thrust fluctuation at lower speeds relative to the LST thrust tester
    -   A follow-up (mini) investigation can be seen further below

**LRT Thrust Tester Speed Comparison**
_______________________________________
{{< div class="row justify-content-center" >}}
    {{< div class="col-8 col-lg-6" >}}
{{< fancy_pics loc="fit"
               caption="LSM200B"
               content=""
               src="media/image7.gif" >}}
    {{< divclose >}}
    {{< div class="col-8 col-lg-6" >}}
{{< fancy_pics loc="fit"
               caption="LSQ150D"
               content=""
               src="media/image8.gif" >}}
    {{< divclose >}}
    {{< div class="col-8 col-lg-6" >}}
{{< fancy_pics loc="fit"
               caption="LSQ600A"
               content=""
               src="media/image9.gif" >}}
    {{< divclose >}}
{{< divclose >}}


-   When comparing stages, there were no common frequencies were noticeable, suggesting that the LRT Thrust Tester does not introduce significant thrust fluctuation into the test results

    -   Interestingly, thrust fluctuation frequency with respect to position seemed to be inversely correlated to leadscrew pitch

    -   Honestly not sure what would be causing the fluctuations

{{< fancy_pics loc="fit"
               caption="LRT Thrust Tester Stage Comparison"
               content=""
               src="media/image13.gif" >}}

<br>

### Random Fluctuation in LSQ600A - Mini Investigation

-   I initially speculated that the odd fluctuation in thrust seen on the LRT Thrust Tester when testing the LSQ600A is caused by the thrust tester
    -   This is only really based on the fact that nothing similar was present in the other stages tested on the LRT thrust tester
    -   However, the load is much higher for the LSQ600A, which may make a large difference
-   Thinking that it may be due to how the stage was mounted on the breadboard, I repeated the test with two mounting methods/mounting block positions

| **Method 1**                                                  |                                                         **Method 2**     |
|---------------------------------------------------------------|--------------------------------------------------------------------------|
|{{< fancy_pics loc="fit" caption="" src="media/image14.jpeg" >}}|{{< fancy_pics loc="fit" caption="" content="" src="media/image15.jpeg" >}}|

-   However, it was found to have little to no effect on the results.

{{< fancy_pics loc="fit"
               caption="Mounting Method Comparison"
               content=""
               src="media/image16.gif" >}}

-   Unfortunately, that brings me to the end of my co-op term, so further investigation will likely be needed
    -   I would suggest that the testing team periodically records and analyses the high speed thrust logging while doing thrust tests in the future to gather more data
-   I have started a full travel test with LRT Thrust Tester position being recorded as well for more insight

## Conclusion
_______________________________________
-   It was found that using the average thrust from a successful pass likely provides a more representative peak thrust value for a stage than the lowest recorded thrust value
    -   Changes in the script should be implemented to reflect this
-   It was also found that the LST thrust tester seemed to be introducing some larger cyclical thrust fluctuations
    -   However, on the LRT thrust tester, there are only smaller fluctuations that are likely a combination of LRT thrust tester and test stage velocity stability.

## Evaluation and Recommendations
_______________________________________
-   High speed thrust passes should continue to be logged and monitored to gather more data
    -   This may also provide insight on thrust
