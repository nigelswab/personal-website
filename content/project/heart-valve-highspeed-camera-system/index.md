---
title: "High-Speed Camera and Lighting System"
subtitle: "Vivitro Labs - Mechanical Engineering Co-op"
# Style sets the style of the banner and uses hugo-story styling
style: "style2 orient-right content-align-center image-position-center fullscreen
        color1 invert onload-image-fade-in onload-content-fade-right"
summary: >-
    High-speed video is an integral part of prosthetic heart valve durability
    testing, especially given the updates in <a href="https://www.iso.org/standard/77033.html">ISO 5840-1:2021</a> 
    that place greater emphasis on leaflet kinematics. As such, 
    one of my responsibilities while on co-op at <a href="https://vivitrolabs.com/">Vivitro Labs</a> 
    was to design and specify a high-speed camera system for a new Accelerated 
    Wear Tester (AWT) that could be efficiently transferred between testing units 
    with consistent valve framing and image quality By the end of my co-op term, 
    I had specified a lens for aortic valves, designed and tested multiple 
    camera mounting and lighting prototypes, and refined camera and 
    light mounting designs.
feature_image: "featured.png"
authors: []
tags: [featured, co-op, design, testing]
categories: []
date: 2020-12-31
start_date: "October 2020"
finish_date: "December 2020"

# Optional external URL for project (replaces project detail page).
external_link: ""

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
#   slides: ""
---

# Overview
{{< fancy_pics loc="right sm"
               caption="Early Accelerated Wear Tester Prototype"
               content="(details blurred to retain confidentiality)"
               src="Results/front-view-thin.png" >}}

High-speed video is an integral part of prosthetic heart valve durability
testing, especially given the updates in {{< rawhtml >}}<a href="https://www.iso.org/standard/77033.html" target="_blank">ISO 5840-1:2021</a>{{< /rawhtml >}} 
that place greater emphasis on leaflet kinematics. As such, 
one of my responsibilities while on co-op at {{< rawhtml >}}<a href="https://vivitrolabs.com/" target="_blank">Vivitro Labs</a>{{< /rawhtml >}} 
was to design and specify a high-speed camera system for a new Accelerated 
Wear Tester (AWT) that could be efficiently transferred between testing units 
with consistent valve framing and image quality. By the end of my co-op term, 
I had specified a lens for aortic valves, designed and tested multiple 
camera mounting and lighting prototypes, and refined camera and 
light mounting designs. Although done in parallel, this project can 
be broken into two main components:
* **Camera System** - encompasses the specification of a lens 
and the design of mounting for an {{< rawhtml >}}<a href="https://www.aostechnologies.com/fileadmin/user_upload/PDFs/Process_Monitoring/AOS_Promon_U1000_en_2017_web.PDF" target="_blank">AOS PROMON U1000</a>{{< /rawhtml >}}
high-speed video camera. **{{< rawhtml >}}<a href="Work Term 4 Final Report - Camera Mount Design.pdf" target="_blank">(Full report on camera mounting here)</a>{{< /rawhtml >}}**
* **Lighting System** - includes the specification and layout
of LEDs, collaboration on a PCB, and the design of mounting.

# Background
Medical devices can be vital to treating patients with 
cardiovascular disease; any failure can have life-altering 
consequences. Vivitro Labs is a company dedicated to reducing the risk 
to patients by developing cardiovascular device testing equipment, 
offering laboratory testing, and providing consulting services.
While working at Vivitro as a Mechanical Engineering Co-op, my time 
was primarily spent contributing to the development of a new prosthetic 
heart valve durability tester.

## Prosthetic Heart Valve Durability Testing
{{< div class="row justify-content-center" >}}
    {{< div class="col-9 align-self-start" >}}
Durability testing is one of the most inherently expensive and time-consuming 
processes of heart valve development. Testing must adhere to ISO 5840 and 17025
testing standards and demonstrate that prosthetics will remain functional for 
200-400 million cycles under specific operational conditions. The use of 
Accelerated Wear Testers (AWT's) reduces the time and cost of these tests.

Although Vivitro currently sells an AWT, the HiCycle, design limitations
and advances in the market have led them to begin developing a new AWT 
with cycling speeds 300-2100 BPM, or 5-35 Hz. While capable of higher speeds, 
cycle frequency is often limited by the valve; at least 95% of the cycles must
have defined pressure differentials consistent with normotensive conditions for
at least 5% of the cycle's duration, and leaflet kinematics must be 
consistent with those observed in the hydrodynamic assessment.
    {{< divclose >}}
    {{< div class="col-lg-3 col-4 align-self-center mt-lg-n5 px-lg-5" >}}
{{< fancy_pics loc="fit" 
               caption="General Heart Valve Durability Testing Procedure" 
               content="Hydrodynamic Assessment is done with more physiologically accurate speeds and conditions using equipment like Vivitro's Pulse Duplicator."
               src="durability_testing.svg" >}}
    {{< divclose >}}
{{< divclose >}}

# The Problem
{{< div class="row justify-content-center justify-md-content-center mb-n3 mb-lg-n5" >}}
    {{< div class="col-12 col-lg-7" >}}
High-speed video is an important part of durability testing; footage of 
the heart valve must be regularly compared to footage taken in more 
physiologically accurate conditions when tuning an AWT, inspecting for 
damage, and observing the effects of wear. Therefore, providing a quick, consistent, and painless way to set up 
and record high-speed video on the new AWT was an important part of 
producing a compelling value proposition and positive user experience.
    {{< divclose >}}
    {{< div class="col-8 col-lg-5 py-3 mt-lg-n5" >}}
{{< fancy_pics loc="fit" 
               caption="Preliminary Accelerated Wear Tester Model"
               content="The base configuration of the AWT comprises of six physical testing units, one high-speed camera, a controller, and a data acquisition box. This base configuration can also be customized to include more controllers and testing units as requested."
               src="Preliminary AWT Base Configuration.png" >}}
    {{< divclose >}}
{{< divclose >}}

## Objectives
{{< div class="row justify-content-middle mt-n3 mb-n4" >}}
    {{< div class="col-lg-4 order-lg-0 col-6 order-2 px-lg-5 text-center offset-lg-0 offset-3 align-self-center mt-n3" >}}
{{< video src="silicon_valve_slo_loop.mp4" controls="false" autoplay="true" loop="true" muted="true" width="100%">}}
Silicon industrial valve (1/8{{< rawhtml >}}<sup>th</sup>{{< /rawhtml >}} speed @ 60FPS)
    {{< divclose >}}
    {{< div class="col-lg-4 order-lg-1 col-sm-6 col-12 order-0" >}}
    {{< rawhtml >}}
      <h3 style="text-align: center; ">Camera System</h3><hr>
      <ul style="margin-right: 0.5rem; margin-top: 0.5rem">
        <li> Take less than one minute to remove and install between units</li>
        <li> Consistently locate the camera relative to the valve</li>
        <li> Cost less than 500 USD for small production runs of around 10 units (excluding camera and camera lens)</li>
        <li> Capture the full width and depth of any aortic <em>or</em> mitral valve with one lens </li>
      </ul>
    {{< /rawhtml >}}
    {{< divclose >}}
    {{<div class="col-lg-4 order-lg-2 col-sm-6 col-12 order-1" >}}
    {{< rawhtml >}}
      <h3 style="text-align: center">Light System</h3><hr>
      <ul style="margin-left: 0.5rem; margin-top: 0.5rem">
        <li> Sufficient light to illuminate a prosthetic heart valve when recording video at 817-1000 FPS</li>
        <li> Take less than 30 seconds to remove from a unit </li>
        <li> Illuminate the valve evenly with minimal shadows</li>
      </ul>
    {{< /rawhtml >}}
    {{< divclose >}}
{{< divclose >}}

{{< rawhtml >}}
<h3>Additional Considerations</h3><hr>
<ul style="margin-top: 0.5rem;">
    <li>One of the primary design objectives of the new AWT is to provide exceptional valve visibility</li>
    <li>Corrosive saline solution spills are common and expected throughout durability testing</li>
    <li>Most users will be working with latex gloves on in a small laboratory setting</li>
</ul>
{{< /rawhtml >}}

# The Designs
After defining the design objectives and constraints, I created concept 
models using Solidworks while specifying a suitable lens for aortic valves.
Since Vivitro also runs a testing lab, I was able to gain valuable 
feedback and insight from end users throughout the design process.

## Camera System
{{< div class="row justify-content-center align-items-center mb-n3" >}}
    {{< div class="col-6 col-lg-4 px-lg-4 order-5 mt-lg-n5" >}}
{{< fancy_pics loc="fit"
               caption="<a href='https://www.aostechnologies.com/fileadmin/user_upload/PDFs/Process_Monitoring/AOS_Promon_U1000_en_2017_web.PDF' target='_blank'>AOS PROMON U1000</a>"
               content="Before I joined Vivitro, the PROMON U1000 high-speed camera was specified for the new AWT."
               src="https://www.aostechnologies.com/fileadmin/user_upload/Bilder/Process_Monitoring/AOS_PROMON_U750.png" >}}
    {{< divclose >}}
    {{< div class="col-12 col-lg-8 mt-lg-n5" >}}
The specification of a camera lens and the design of the camera mounting 
were done in parallel since they were collectively responsible for ensuring
that high-speed video of the prosthetic valves could be properly framed and
recorded.
    {{< divclose >}}
{{< divclose >}}

### Camera Lens
{{< div class="row justify-content-center justify-md-content-center mt-n2 mb-n2" >}}
    {{< div class="col-12 col-lg-7" >}}
    {{< div class="row mb-n3" >}}
        {{< div class="col-12" >}}
Several factors related to the camera, camera mounting, and prosthetic
valves had to be considered when specifying a lens, including:  
        {{< divclose >}}
        {{< div class="col-4 my-n2" >}}
* Object Distance 
* Camera Resolution 
        {{< divclose >}}
        {{< div class="col-4 mt-2" >}}
* F-stop/Aperture
* Focal Length
        {{< divclose >}}
        {{< div class="col-4 mt-2" >}}
* Depth of Field
* Width of Field
        {{< divclose >}}
   {{< divclose >}}
It was found that lenses capable of capturing both aortic and mitral 
valves were large and expensive. Since most customers tend to 
specialize in one of aortic or mitral valves, it was decided that a 
separate lens would be specified for each valve.

{{< rawhtml >}}<br><b><a href='Camera Lens Determination - NS.pdf' target='_blank'>Click here for documentation on the aortic lens specification process.</a></b>{{< /rawhtml >}}
    {{< divclose >}}
    {{< div class="col-8 col-lg-5" >}}
{{< fancy_pics loc="fit" 
               caption="<a href='https://vst.co.jp/en/machine-vision-lenses-en/vs-lda-series/' target='_blank'>VS-LDA20</a>"
               content="The VS-LDA20 was chosen as the specified aortic valve lens. While remaining relatively inexpensive, this 20 mm focal length lens provided enough adjustability to capture the full width and depth of field for all aortic valves when used in combination with the camera mount's vertical adjustability"
               src="camera_lens.PNG" >}}
    {{< divclose >}}
{{< divclose >}}

### Camera Mounting
While specifying lenses, I generated several design concepts with 
SolidWorks and reviewed them with the R&D and lab testing teams. 
A number of these concepts can be seen below, including one with
three variations:
{{< div class="row justify-content-center mb-lg-n3" >}}
    {{< div class="col-8 col-lg-4" >}}
{{< fancy_pics loc="fit" 
               caption="Concept 1 - Pillow Block" 
               content="An aluminum rod is clamped by two pillow blocks that are mounted to the AWT's lower valve chamber. This concept was developed so that the camera could also be mounted below the valve, an objective was removed after a discussion with lab staff revealed how infrequently this was needed."
               src="mounting_concepts/Concept 1.png" >}}
    {{< divclose >}}
    {{< div class="col-8 col-lg-4" >}}
{{< fancy_pics loc="fit" 
               caption="Concept 2A - Top Mounted (18mm)" 
               content="This concept features <a href='https://www.elesa-ganter.com/en/www/Tube-Clamp-Connectors--Base-plate-connector-clamps--GN162' target='_blank'>base plate connector clamps</a> mounted to each testing unit and an 18 mm rod that slots into each unit's back chamber. The intent behind this approach was for users to simply undo the base clamp and move the rod and camera together."
               src="mounting_concepts/Concept 2a.png" >}}
    {{< divclose >}}
    {{< div class="col-8 col-lg-4" >}}
{{< fancy_pics loc="fit" 
               caption="Concept 2B -Top Mounted (20mm)" 
               content="A combination of concern for mounting rigidity when exposed to the AWT's vibrations, and the existence of a camera mounting bracket at Vivitro compatible with 20 mm rods led me to design a variation of 2A with <a href='https://www.elesa-ganter.com/en/www/products/tube-clamp-connectors--1/Tube-Clamp-Connectors--Base-plate-connector-clamps--GN163#sortby=0&facetvalue=' target='_blank'>this base connector clamp</a> and a 20 mm rod."
               src="mounting_concepts/Concept 2b.png" >}}
    {{< divclose >}}    
    {{< div class="col-8 col-lg-4" >}}
{{< fancy_pics loc="fit" 
               caption="Concept 2C - Back Mounted (18mm)" 
               content="This version of Concept 2 opts for a <a href='https://www.elesa.com/en/elesab2bstoreca/catalogue-cat-076-sales/tube-connectors-us--1/tube-connectors-for-linear-actuators-us--1/Connecting-clamps--Connecting-clamps-with-mounting-base--GN1451#sortby=0&facetvalue=' target='_blank'>flanged connector clamp</a> mounted to the rear of the back chamber, but is functionally similar to concepts 2A and 2B. This design was created to offer an option that could be used with Vivitro's <a href='https://vivitrolabs.com/product/pulse-duplicator/' target='_blank'>Pulse Duplicator</a>with minor modifications."
               src="mounting_concepts/Concept 2c.png" >}}
    {{< divclose >}}
    {{< div class="col-8 col-lg-4" >}}
{{< fancy_pics loc="fit" 
               caption="Concept 3 - Automated Stage" 
               content="By employing an automated stage, this option presents an ideal user experience. However, this concept was likely prohibitively expensive and difficult to execute in a way that allows the same level of modularity that the new AWT architecture will offer."
               src="mounting_concepts/Concept 3.png" >}}
    {{< divclose >}}
{{< divclose >}}

After several design reviews and concept iterations, it was decided 
that each variation of Concept 2 would be refined and made 
into prototypes for testing. Additionally, feedback from a Test 
Engineer on vertical camera adjustment led me to introduce a {{< rawhtml >}}
<a href="https://www.novoflex.de/en/products-637/macro/extension-bellows/universal-bellows-bal-f/CASTEL-MINI_II_en.html" target="_blank">Novoflex focusing rack</a>{{< /rawhtml >}}
as the primary method of adjusting the camera's height.
Lastly, I found the approximate natural frequency of the camera system,
camera and Novoflex included, using hand calculations and a Solidworks simulation.

{{< div class="row justify-content-center pt-2" >}}
    {{< div class="col-8 col-md-6 col-lg-4" >}}
{{< fancy_pics loc="fit" 
               caption="<a href='https://www.novoflex.de/en/products-637/macro/extension-bellows/universal-bellows-bal-f/CASTEL-MINI_II_en.html' target='_blank'>Novoflex CASTEL-MINI II Focusing Rack</a>" 
               content="This manual focusing rack allows for easy and consistent camera height alteration that cover the full range of adjustment needed for most aortic valve sizes with the lens specified above."
               src="mounting_concepts/novoflex_focus_rack.png" >}}
    {{< divclose >}}
    {{< div class="col-8 col-md-6 col-lg-4" >}}
{{< fancy_pics loc="fit" 
               caption="Refined Concept 2A Model" 
               content="As can be seen, the Novoflex focusing rack was integrated and a bracket that clamps onto the rod was designed."
               src="mounting_concepts/Concept 2 Refined.png" >}}
    {{< divclose >}}
{{< divclose >}}
{{< div class="row justify-content-center pt-2" >}}
    {{< div class="col-8 col-lg-6" >}}
{{< fancy_pics loc="fit md" 
               caption="Concept 2A SolidWorks Simulation" 
               content="The undamped natural frequency of the camera system was calculated to be ~117 Hz, while the SolidWorks simulation resulted in ~119 Hz (camera and Novoflex mass lumped into the bracket's weight)."
               src="mounting_concepts/SW_vib_sim.png" >}}
    {{< divclose >}}
{{< divclose >}}

## Lighting System
{{< div class="row justify-content-center mb-n2 mt-lg-n1" >}}
    {{< div class="col-6 col-md-6 col-lg-4 mt-lg-n4 order-5 px-lg-5 " >}}
{{< fancy_pics loc="fit"
               caption="<a href='https://www.digikey.ca/en/product-highlight/c/cree/xm-l2-leds' target='_blank'>Cree XLamp XM-L2 LED</a>"
               content="This LED was choosen for its high luminosity and thermal efficiency."
               src="light_concepts/LED.png" >}}
    {{< divclose >}}
    {{< div class="col-12 col-md-6 col-lg-8" >}}
Each frame's exposure time is extremely short when recording high-speed video; 
the higher the frame-rate, the more light
required to capture clear images. To ensure the AWT had
sufficient lighting for video recording at 1000 FPS, an 
electrical engineering co-op student and I collaborated on the design 
and implementation of a lighting system. 
    {{< divclose >}}
{{< divclose >}}

### Light Mounting
Working together on form factor, the other co-op student designed the PCB 
while I primarily focused on its mounting. Much like with camera
mounting, a number of concepts were generated and reviewed. 

{{< div class="row justify-content-center mb-lg-n3" >}}
    {{< div class="col-8 col-md-6 col-lg-4" >}}
{{< fancy_pics loc="fit" 
               caption="Concept 1 - Simple Ring" 
               content="Attaching to a bracket for modularity, this concept was kept relatively simple to allow for the majority of machining to take place in one operation on a lathe. This concept was made out of aluminum and was inteded to act as a heat sink for the PCB."
               src="light_concepts/light_concept_1_43.png" >}}
    {{< divclose >}}
    {{< div class="col-8 col-md-6 col-lg-4" >}}
{{< fancy_pics loc="fit" 
               caption="Concept 2 - Camera System Mounted" 
               content="Clamping onto the camera mounting rod, this concept was designed to be vacuum cast out of acetyl and moved between testing units with the high-speed camera."
               src="light_concepts/light_concept_2_43.png" >}}
    {{< divclose >}}
    {{< div class="col-8 col-md-6 col-lg-4 " >}}
{{< fancy_pics loc="fit" 
               caption="Concept 3 - Valve Chamber Mounted" 
               content="Resting on the top of the angled valve chamber, this concept was designed to be vacuum cast out of acytal much like Concept 2. However, this design was made with the intent of outfitting a light to each testing unit."
               src="light_concepts/light_concept_3_43.png" >}}
    {{< divclose >}}
{{< divclose >}}

While concept 1 was designed to be made using conventional machining methods, 
concepts 2 and 3 were originally designed for 3D printing. However,
once it was decided that concepts 2 and 3 would be made for testing, the
designs were modified to be compatible with conventional machining methods
and vacuum casting at production scale.

### Heat Management 
{{< div class="row justify-content-center mt-n2" >}}
    {{< div class="col-6 col-lg-3 order-5 mt-3 mt-lg-n4" >}}
{{< fancy_pics loc="fit"
               caption="Light Ring PCB Model"
               content="This PCB was made with 6 and 12 LED variations."
               src="light_concepts/light_pcb_render_iso.png" >}}
    {{< divclose >}}
    {{< div class="col-12 col-lg-9" >}}
Given the intensity of the light being generated, the electrical 
engineering co-op and I also worked on design considerations for
managing the heat created by the LED's. We used thermal pad kickouts 
in conjunction with an aluminum backing board to help distribute and
dissipate heat. Additionally, the light mounting included cutouts that
expose the PCB backing to the air to aid with heat dissipation. However, 
to reduce the potential for burns, these cutouts were made too small for 
fingers to fit through.
    {{< divclose >}}
{{< divclose >}}


# The Results
Prototypes of each camera mounting concept, along with each light
mounting, were successfully manufactured and assembled.
{{< div class="row justify-content-center mb-lg-n3" >}}
    {{< div class="col-8 col-lg-4" >}}
{{< fancy_pics loc="fit" 
               caption="AWT Prototype with Light Mount Concept 2" 
               content="<br>Camera Mounting: Concept 2A <br>Light Mounting: Concept 2"
               src="Results/proto-extend.png" >}}
    {{< divclose >}}
    {{< div class="col-8 col-lg-4" >}}
{{< fancy_pics loc="fit" 
               caption="Light Mounting Prototypes" 
               content="<br>Concept 2 (left) and Concept 3 (Right)"
               src="Results/light_mount_prototypes.jpg" >}}
    {{< divclose >}}
    {{< div class="col-8 col-lg-4" >}}
{{< fancy_pics loc="fit" 
               caption="AWT with Light Mount Concept 3"
               content="<br>Camera Mounting: Concept 2A <br>Light Mounting: Concept 3"
               src="featured.png" >}}
    {{< divclose >}}    
{{< divclose >}}    


## Field Width and Depth of Field
To confirm that the camera lens, focusing rack, and lighting were 
collectively capable of capturing the full range of aortic valve 
sizes, a test marker was designed and 3D printed with the largest and
smallest expected diameters and depths of prosthetic aortic valves. As can 
be seen by the frames taken from a high-speed video recording below, 
the camera mounting system provides sufficient adjustability to capture the 
full range of aortic valves.

{{< fancy_pics loc="fit" 
               caption="Field Width and Depth of Field Test Results" 
               content="The AOS focusing tool overlay highlights details deemed to be in-focus. As can be seen, both the high points (the edges of each ring), and the base are within focus, confirming that there's sufficient depth of field."
               src="Results/field_and_focus_test.svg" >}}

Since prosthetic mitral valve dimensions tend to vary less than those 
of aortic valves, it was determined that the camera mounting system 
provided sufficient adjustability to also accommodate most mitral valves, 
given a properly specified lens.

## Camera Transfer Speed and Frame Repeatability
Testing of the camera mounting system's transfer speed 
and frame repeatability was done in parallel. 
- It was found that it took an average of 42 seconds over five
tests to remove and re-install the camera. 
- It was also found that the camera mounting system reliably 
located the camera relative to the test valve, as shown below.

{{< fancy_pics loc="fit"
               caption="Frame Location Repeatability Test Results" 
               content="The red marker remained on the same pixels for all repeatability testing.  Since there is only one prototype unit, the potential for tolerance stack-up between components could not be tested, however, the maximum offset due to this was calculated to be 1 mm, or 0.05% of a small aortic valve’s diameter. Therefore, it was determined that tolerance stack-up is not a large concern, especially relative to the tolerances on the valve holders."
               src="Results/repeatability_test.svg" >}}
{{< rawhtml >}} <br> {{< /rawhtml >}}

## Image Stability 
To test the stiffness/stability of the camera mounting system, the AWT 
was set to frequencies between 10 and 35 Hz in 5 Hz steps. Since the 
AWT’s natural frequency was found to be 22Hz, this frequency was 
also tested. Given time constraints, I was unable to quantify the amplitude of
vibrations captured in high-speed video. Therefore, qualitative notes
were taken and summarized below. All configurations failed to provide adequate 
stability throughout the expected operational range.

|Excitation Frequency (Hz)|Standard 18 mm Configuration|18mm Rod with Pulse Duplicator Bracket|20 mm Rod with Pulse Duplicator Bracket|
|:----|:----|:----|:----|
|10|Stable|Stable|Stable|
|15|Fairly stable|Fairly stable|Fairly stable|
|20|Somewhat stable|Somewhat stable|Somewhat stable|
|22|Small vibration noticeable|Small vibration noticeable|Somewhat stable|
|25|Vibration noticeable|Vibration noticeable|Small vibration noticeable|
|30|Significant vibration noticeable|Significant vibration noticeable|Vibration Visible|
|35|Significant vibration noticeable|Significant vibration noticeable|Significant vibration noticeable|


## Cost

When ordering prototype parts, quotes for a low-production run of 10 
AWT's with the base configuration of six testing units were acquired.
While the final cost is well below the goal of $500, it's worth noting 
that the camera mounting adapter and rod designs will be 
simplified for the final product, further reducing costs.

|Part|Cost (USD)|
|:----|:----|
|Novoflex CASTEL-Mini II Focusing Rack| $   200.00|
|GN 162-B18-2-BL - Flanged Bracket| $   17.56| 
|AWT – High Speed Camera Mounting Plate| $   35.35|
|AWT – High Speed Camera Mount Adapter| $   75.09| 
|AWT – Camera Mounting Rod – 18mm| $   64.62|
|**Total**| **$   392.61**|


## Lighting
Testing was then done to ensure the light ring could provide sufficient
light to properly illuminate a dark test valve at 1000 FPS and f-stop 16.
Additionally, temperatures were monitored to ensure the PCB remains
sufficiently cool while operating with its maximum light output. 

{{< div class="row justify-content-center" >}}
    {{< div class="col-8 col-md-6 col-lg-4" >}}
{{< fancy_pics loc="fit" 
               caption="Bovine Tissue Aortic Valve - 12 LED Ring" 
               content="Both 6 and 12 LED light rings provided sufficient light (with no shadows) to view prosthetic valve details with the least favorable camera setup for light. "
               src="Results/lighting.png" >}}
    {{< divclose >}}
    {{< div class="col-8 col-md-6 col-lg-4" >}}
{{< fancy_pics loc="fit" 
               caption="IR Camera Readings" 
               content="Peak temperatures were monitored using a FLIR IR camera. Notice that while the PCB backing is quite hot, the mounting remains cool enough to comfortably handle."
               src="Results/light_ring_heat.jpg" >}}
    {{< divclose >}}
    {{< divclose >}}
{{< div class="row justify-content-center mb-lg-n3" >}}
    {{< div class="col-8 col-md-6 col-lg-4" >}}
{{< fancy_pics loc="fit" 
               caption="" 
               content="After 30 minutes of operation in a room ~22.8 °C, temperatures appeared to stabilize around 109 °C."
               src="Results/pcb_heating.png" >}}
    {{< divclose >}}
    {{< div class="col-8 col-md-6 col-lg-4" >}}
{{< fancy_pics loc="fit" 
               caption="" 
               content="After the light was turned off, the PCB's temperature rapidly declined, reaching ambient temperature in around 15 minutes."
               src="Results/pcb_cooling.png" >}}
    {{< divclose >}}
{{< divclose >}}

As can be seen above, while PCB temperatures remained low enough to avoid 
damaging the acetyl mounts, they still rose fairly high. However, 
the light output tested is rarely required for even high-speed video capture, 
thus it is unlikely that the peak temperatures seen will even be approached 
in normal operation. Nonetheless, it was advised that a timer be programmed to
turn off the lights when operating at high output for over 10-15 minutes
to reduce the risk of a fire or AWT damage.

# Conclusion and Recommendations 
Following the testing of the camera and lighting systems, along with 
the first AWT prototype, I worked with another engineer to introduce 
several modifications to the design of all three. The major changes to
the camera and light mounting are summarized below:
* Updates to the design of the AWT significantly reduced the required
camera mounting rod length, improving image stability. 
  * This also meant that the same camera mounting prototype could be 
  used to test camera stability. 
  * The 18 mm rod variant of Concept 2 was chosen and its mounting 
  location on the AWT was centered.
* It was decided that each AWT testing unit will come with a dedicated 
light, so the Concept 3 (chamber mounted) design was refined.
  * Updates to the AWT's valve chamber allowed the light ring mount to be 
  simplified to a ring with three locating nubs and a flat.
  * Black acetyl was chosen in response to the amount of light that bled 
  through the white acetyl prototypes.

{{< div class="row justify-content-center align-items-center" >}}
    {{< div class="col-8 col-md-6 col-lg-4" >}}
{{< fancy_pics loc="fit" 
               caption="Refined Camera Mounting Prototype Model" 
               content="Some vertical adjustability beyond the Novoflex focusing rack left to allow for easy handling and modularity."
               src="mounting_concepts/Concept 2.1.png" >}}
    {{< divclose >}}
    {{< div class="col-8 col-md-6 col-lg-4" >}}
{{< fancy_pics loc="fit" 
               caption="Refined Light Mount Prototype Model" 
               content="It was decided that each testing unit should get a light, thus the chamber mounted concept (Concept 3) was refined and modified to interface with the updated AWT valve chamber."
               src="light_concepts/light_concept_4_model.PNG" >}}
    {{< divclose >}}
    {{< div class="col-8 col-md-6 col-lg-3" >}}
{{< fancy_pics loc="fit" 
               caption="Refined Light Mount Prototype" 
               content="The refined light mount was made after I left Vivitro. However, I was told it worked well."
               src="light_concepts/light_concept_4.png" >}}
    {{< divclose >}}
{{< divclose >}}

Within the last week of my co-op, we successfully submitted drawings to a 
manufacturer to be made over the holiday break. Additionally, before leaving, 
I calculated and suggested a target spring rate for vibration isolating feet 
to reduce the amplitude of vibrations observed by the AWT when in operation, 
especially at 22 Hz.

**{{< rawhtml >}}<a href="Work Term 4 Final Report - Camera Mount Design.pdf" target="_blank">Full report on camera mounting here</a>{{< /rawhtml >}}**