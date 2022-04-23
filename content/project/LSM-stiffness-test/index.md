---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "LSM Stiffness Test - Recirculating Bearing Stiffness for Specs"
subtitle: "Zaber Technologies - Test Engineering Co-op"
# Style sets the style of the banner and uses hugo-story styling
style: "style2 orient-center content-align-center image-position-center fullscreen
        color1 invert onload-image-fade-in onload-content-fade-right"
summary: "
<ul>
<li> The updated LSM design with recirculating bearings was tested for stiffness in pitch,roll, and yaw</li>
<li> 5 stages were tested and all surpassed the recommended new specifications of 150 Nm/°</li>
<li> All stiffness testing results show there should be no issues increasing stiffness specifications to 150 Nm/°</li>
<li> I suspect 150 Nm/° may be fairly conservative for properly torqued stage top bolts, especially in pitch</li>
</ul>"
authors: []
tags: [co-op, testing, data-analysis]
categories: []
date: "2021-03-13"

start_date: "March 2021"
finish_date: "April 2021"

# Optional external URL for project (replaces project detail page).
external_link: ""
feature_image: "featured.jpg"

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
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

# Dev/R-LSM/2021-03-13 - Recirculating Bearing Stiffness for Specs

| **Product**            | R-LSM      |
|------------------------|------------|
| **Test Attributes**    | Stiffness  |
| **Tester**             | Nigel      |
| **Plan Reviewed by**   | Nathan P   |
| **Report Reviewed by** | Nathan P   |
| **Test Date**          | 2021/04/21 |

## Abstract
_______________________________________

- The updated LSM design with recirculating bearings was tested for stiffness in pitch,roll, and yaw
{{< fancy_pics loc="right sm"
               caption="<a href='https://www.zaber.com/products/linear-stages/X-LSM' target='_blank'>X-LSM025B</a>"
               content="The previous generation LSM's used cam follower bearings, as shown here"
               src="media/yaw.jpg" >}}  
- 5 stages were tested and all surpassed the recommended new specifications of 150 Nm/°
- All stiffness testing results show there should be no issues increasing stiffness specifications to 150 Nm/°
    -   However, I suspect 150 Nm/° may be fairly conservative for properly torqued stage top bolts, especially in pitch

## Background
_______________________________________
-   The LSM has been redesigned with recirculating bearings
-   The installed rails are not from our new supplier (that should in theory be better)
    -   We are using the "best bad rail" we have with the expectation that the new rail will be as good or better
    -   When we get the production rail, we will exchange the rails in two stages and quickly retest them to confirm the specs from the old batch of rail are still valid.
-   While these stages are 99.5% production ready, anything fishy should be noted
-   Mark has recommended updated specifications of 150 Nm/° here: [<u>https://iwiki.izaber.com/Dev/R-LSM/Recirculating_Bearing_Design#2021-05-07_Published_Stiffness_Specs</u>](https://iwiki.izaber.com/Dev/R-LSM/Recirculating_Bearing_Design#2021-05-07_Published_Stiffness_Specs)
-   Previous stiffness tests have been done with the new design consistently showing high stiffness:
    -   [<u>https://iwiki.izaber.com/Dev/R-LSM/2020-07-28\_-\_Recirculating_Stiffness</u>](https://iwiki.izaber.com/Dev/R-LSM/2020-07-28_-_Recirculating_Stiffness)
    -   [<u>https://iwiki.izaber.com/Dev/R-LSM/2020-11-16\_-\_Recirculating_Bearing_Stiffness</u>](https://iwiki.izaber.com/Dev/R-LSM/2020-11-16_-_Recirculating_Bearing_Stiffness)
    -   [<u>https://iwiki.izaber.com/Dev/R-LSM/2021-01-05\_-\_High_Pre-Load_Recirculating_Stiffness</u>](https://iwiki.izaber.com/Dev/R-LSM/2021-01-05_-_High_Pre-Load_Recirculating_Stiffness)
    -   [<u>https://iwiki.izaber.com/Dev/R-LSM/2021-01-27\_-\_Loaded_Recirc_Mid-Lifetime_Stiffness</u>](https://iwiki.izaber.com/Dev/R-LSM/2021-01-27_-_Loaded_Recirc_Mid-Lifetime_Stiffness)

## Purpose
_______________________________________

-   Establish specs for the new LSM design with recirculating bearings

## Method
_______________________________________
### Equipment

| **Test Equipment**  |                                  |
|---------------------|----------------------------------|
| Devices:            | See below                        |
| Load cell           | Omega 250 lb with U6 Labjack DAQ |
| Measurement Device: | Heidenhain                       |
| Forcing Stage:      | A-LST0250A                       |

|                               | **LSM200B**      | **LSM200B**       | **LSM200B**      | **X-LSM200A**     | **X-LSM200A**    |
|-------------------------------|------------------|-------------------|------------------|-------------------|------------------|
| **Motor/Controller Assembly** | M-3PO            | TT-40             | TC-14            | WAC-47            | T3-M4            |
| **Base Assembly**             | R5-D4            | ZZ-4Z             | T3-H8            | R2-KT             | HK-47            |
| **Lead Screw**                | C-21             | 0-0-0             | 2-1B             | FA-4              | GH-7             |
| **Device Name**               | M-3PO R5-D4 C-21 | TT-40 ZZ-4Z 0-0-0 | TC-14 T3-H8 2-1B | WAC-47 R2-KT FA-4 | T3-M4 HK-47 GH-7 |
| **Serial Number**             | 4000000029       | 4000000030        | 4000000031       | 4000000032        | 4000000034       |

### Settings

| **Test Settings**    |     |
|----------------------|-----|
| Repetitions:         | 3   |
| Max Torque (Nm):     | 3   |
| Move Increment (µm): | 15  |


### Code

-   [<u>torsional_stiffness.py</u>](https://gitlab.izaber.com/testing/general_testing_scripts/blob/master/stiffness/torsional_stiffness.py)
-   [<u>Default_Stiffness_Config.yaml</u>](https://gitlab.izaber.com/testing/general_testing_scripts/blob/master/stiffness/Default_Stiffness_Config.yaml)

### Procedure
**Note:** *I was unable to export this section from the wiki*
{{< div class="row justify-content-center" >}}
    {{< div class="col-8 col-lg-4" >}}
{{< fancy_pics loc="fit"
               caption="Pitch Stiffness Setup"
               content=""
               src="media/pitch.jpg" >}}
    {{< divclose >}}
    {{< div class="col-8 col-lg-4" >}}
{{< fancy_pics loc="fit"
               caption="Roll Stiffness Setup"
               content=""
               src="media/roll.jpg" >}}
    {{< divclose >}}
    {{< div class="col-8 col-lg-4" >}}
{{< fancy_pics loc="fit"
               caption="Yaw Stiffness Setup"
               content=""
               src="media/yaw.jpg" >}}
    {{< divclose >}}
{{< divclose >}}

## Results and Analysis
_______________________________________

-   All stages exceeded 150 Nm/° in pitch, roll, and stiffness
-   It was found that some stage tops had lower than spec torque on the bolts
    -   Not all stage top bolts were checked for torque, therefore some results may be artificially low
    -   Only the bolded results below were found after stage top bolts were torque to the specified 0.6 Nm

| **Device Serial**  | **Pitch \[Nm/°\]** | **Roll \[Nm/°\]** | **Yaw \[Nm/°\]** |
|--------------------|--------------------|-------------------|------------------|
| **4000000029**     | 230.4              | 202.5             | 167.1            |
| **4000000030**     | 228                | 181.2             | 232.7            |
| **4000000031**     | 218.9              | 177.3             | 187              |
| **4000000032**     | **234.3**          | **156.5**         | **199.2**        |
| **4000000034**     | 234.9              | 166.9             | **213.9**        |
| **Statistics**     |                    |                   |                  |
| **MAX**            | 234.9              | 202.5             | 232.7            |
| **MIN**            | 218.9              | 156.5             | 167.1            |
| **Average**        | 229.3              | 176.88            | 199.98           |
| **Std. Deviation** | 5.79               | 15.4              | 22.4             |

{{< div class="row justify-content-center" >}}
    {{< div class="col-8 col-lg-6" >}}
{{< fancy_pics loc="fit"
               caption="Pitch Stiffness"
               content=""
               src="media/image1.gif" >}}
    {{< divclose >}}
    {{< div class="col-8 col-lg-6" >}}
{{< fancy_pics loc="fit"
               caption="Roll Stiffness"
               content=""
               src="media/image2.gif" >}}
    {{< divclose >}}
    {{< div class="col-8 col-lg-6" >}}
{{< fancy_pics loc="fit"
               caption="Yaw Stiffness"
               content=""
               src="media/image3.gif" >}}
    {{< divclose >}}
{{< divclose >}}

## Conclusion
_______________________________________
-   All stages surpassed the recommended stiffness of 150 Nm/°
-   These results, along with previous testing, suggest that 150 Nm/° stiffness would be a reasonable spec for pitch, roll, and yaw

## Evaluation and Recommendations
_______________________________________

-   As noted, a couple of the stages were found to have stage top bolts below specified torque
    -   Only the stages that had initial results significantly lower than expected had their bolts re-torqued
-   Once final production models are being tested, it may be worth re-evaluating stiffness specs
    -   I suspect that 150 Nm/° would be on the conservative side for properly torqued stage tops, especially in pitch
-   For future stiffness tests, it's recommended that we use the laser cut breadboard blocks I made to consistently reposition the loading stage assembly (See below)
    - This saved me a lot of time once implemented due to the repetitive nature of testing 5 stages with 3 loading orientations
    - This has been added to the procedures
{{< div class="row justify-content-center" >}}
    {{< div class="col-8 col-lg-6" >}}
{{< fancy_pics loc="fit"
               caption="Laser Cut Breadboard Blocks"
               content=""
               src="media/image4.jpeg" >}}
    {{< divclose >}}