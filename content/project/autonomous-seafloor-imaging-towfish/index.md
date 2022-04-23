---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Autonomous Seafloor Imaging Towfish"
subtitle: "MECH 400 - Senior Design Project"
summary: >-
    During the Spring semester of 2021, four mechanical engineering 
    students and I partnered with <a href="https://bluerobotics.com">
    Blue Robotics</a>, for our capstone project. This project encompassed 
    the development of the first prototype of a seafloor imaging towfish 
    that Blue Robotics has continued developing into a marketable product.
    Despite logistical complications caused by COVID-19, the team managed to 
    build and test three prototypes in 98 days. The final prototype, the 
    <em>BlueFish</em>, met the client's requirements, though several areas of 
    improvement and refinement were identified.
authors: []
tags: [featured, school, programming, python, design, mechatronics, C, 
        electrical, teamwork]
categories: []
date: 2021-04-30

start_date: "January 2021"
finish_date: "April 2021"

style: "style2 orient-center content-align-center image-position-center fullscreen
        color1 invert onload-image-fade-in onload-content-fade-right"
feature_image: "featured.jpg"

# Optional external URL for project (replaces project detail page).
external_link: ""

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "Final Prototype - \"BlueFish\""
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

# Overview 
{{< fancy_pics loc="left sm" 
               caption=""
               content="<a href='https://bluerobotics.com'>Blue Robotics</a>"
               src="https://bluerobotics.com/wp-content/uploads/2014/09/br-logo-trans-blue-trans.png" >}}

During the Spring semester of 2021, four mechanical engineering 
students and I partnered with {{< rawhtml >}}<a href="https://bluerobotics.com">
Blue Robotics</a> {{< /rawhtml >}}, for our capstone project. This project encompassed 
the development of the first prototype of a seafloor imaging towfish 
that Blue Robotics has continued developing into a marketable product.
Despite logistical complications caused by COVID-19, the team managed to 
build and test three prototypes in 98 days. The final prototype, the 
*BlueFish*, met the client's requirements, though several areas of 
improvement and refinement were identified.

**{{< rawhtml >}}<a href="Final Report - MECH 400.pdf" target="_blank">
Click here to see the full report.</a>{{< /rawhtml >}}**

# The Problem
{{< div class="row justify-content-center justify-md-content-center mb-lg-n3" >}}
    {{< div class="col-12 col-lg-7" >}}
Towfish are becoming more common in the hobby, science, and industrial
communities and are used for many purposes, including pipeline monitoring, 
seafloor exploration or mapping, water quality monitoring, national defence,
and more. Mounting a camera or imaging sonar to a towfish, as done in this 
project, improves image quality over a vessel mounted system since 
towfish are unaffected by waves on the surface. Adding depth and altitude 
control to the towfish further increases stability and image quality while
enabling varying degrees of resolution. Currently, towfish with dynamic depth 
control do not exist on the market and alternatives are not affordable.
    {{< divclose >}}
    {{< div class="col-8 col-lg-5 py-3 mt-lg-n4 px-lg-4" >}}
{{< fancy_pics loc="fit" 
               caption="BlueFry I with the Final BlueFish Prototype"
               content="The first BlueFish prototype, named BlueFry I, was designed to fit in a Mazda Miata with the BlueBoat."
               src="proto_comparison.jpg" >}}
    {{< divclose >}}
{{< divclose >}}

## Objectives
{{< div class="row justify-content-center justify-md-content-center mb-lg-n3" >}}
    {{< div class="col-12 col-lg-7 order-lg-2" >}}
Several objectives were identified early in the project and given 
varying weights of importance after consulting with our client, 
Blue Robotics. Some of these objectives included:
* Depth control - ± 0.25 m
* Response Frequency - < 0.5 Hz
* Pitch Control - ±3°
* Roll Control - ±3°
* Altitude - 1-10 m from the sea/lake floor
* Depth rating - 100 m
* Bill of Materials - $320-$400 (USD)

{{< rawhtml >}}<a href="https://1drv.ms/b/s!Anbv5JHlV1c6ix87h9RuKmEtARKZ" target="_blank">
Full requirements and objectives documentation here.</a>{{< /rawhtml >}}
    {{< divclose >}}
    {{< div class="col-8 col-lg-5 order-lg-1 px-lg-4" >}}
{{< fancy_pics loc="fit" 
               caption="BlueFry I with a BlueBoat Prototype"
               content="The first BlueFish prototype, named BlueFry I, was designed to fit in a Mazda Miata with the BlueBoat. This was done to ensure that end users could easily transport the equipment without needing to disassemble either product without a large vehicle."
               src="proto_1_with_blueboat.jpg" >}}
    {{< divclose >}}
{{< divclose >}}


## My Role
{{< div class="row justify-content-center justify-md-content-center " >}}
    {{< div class="col-12 col-lg-7" >}}
Throughout the project, major tasks were often split between two members with 
one member taking primary responsibility for the completion of the task and 
a second member providing support.

* Notable Primary Responsibilities:
  * I/O identification and specification
  * Communications between laptop, Raspberry Pi, and Arduino Uno
  * Electrical prototyping (breadboard prototypes, soldering, test jigs, etc.)
  * Electronics packaging
  * Electronics tray design and manufacturing
  * Graphical User Interface (GUI)
* Notable Secondary Responsibilities: 
  * Control system programming and troubleshooting
  * Circuit design and power requirements
  * Engineering drawings 
  * Actuator transmission design
  * Final testing and PID tuning
  {{< divclose >}}
  {{< div class="col-8 col-lg-5 px-lg-3" >}}
{{< fancy_pics loc="fit" 
               caption="Me and BlueFish"
               content=""
               src="blue_and_me.PNG" >}}
    {{< divclose >}}
  {{< divclose >}}

# The Designs
{{< fancy_pics loc="fit"
               caption="Final BlueFish Model (Exploded View)"
               content=""
               src="exploded-view.PNG" >}}

Early in the project, one of my primary responsibilities was the specification of 
the electrical components and their interfaces. It was decided that for the purposes of
this project, it would be best to use an Arduino Uno for the control logic of the 
BlueFish while data logging and communication to the BlueBoat or laptop would
be done through a Raspberry Pi 3b+. Several sensors, lights, and actuators were also 
specified, many of which were designed and made by Blue Robotics. Collectively, this 
assembly was referred to as the *FishGuts* 

{{< div class="row justify-content-center align-items-center" >}}
    {{< div class="col-8 col-md-6" >}}
{{< fancy_pics loc="fit"
               caption="Rough Wire Diagram"
               content="A rough wiring diagram was made to establish a wire coloring scheme and serve as a visual aid when prototyping."
               src="designs/wire_diagram.png" >}}
    {{< divclose >}}
    {{< div class="col-8 col-md-6" >}}
{{< fancy_pics loc="fit"
               caption="Final Wire Schematics"
               content="After finalizing the electrical component specification and power requirement calculations, a wiring schematic was made."
               src="designs/wire_schematics.png" >}}
    {{< divclose >}}
{{< divclose >}}

Before designing and manufacturing the electronics tray, several prototype iterations
were made to test and troubleshoot the electrical system. This step also allowed me 
to practice my soldering skills as each prototype iteration progressed.

{{< div class="row justify-content-center align-items-center" >}}
    {{< div class="col-8 col-lg-4 px-n5" >}}
{{< fancy_pics loc="fit"
               caption="FishGuts Prototype 1"
               content="This prototype was largely made to test communication between all the electrical components (sensors, Arduino Uno, Raspberry Pi."
               src="designs/fishguts_proto_1.jpg" >}}
    {{< divclose >}}
    {{< div class="col-8 col-lg-4 px-n5" >}}
{{< fancy_pics loc="fit"
               caption="FishGuts Prototype 2"
               content="In the second prototype, a small breadboard was attached to the Arduino Uno and wiring for the final prototype was beginning to be thought of while integration of all the electrical components was continuing to be worked on."
               src="designs/fishguts_proto_2.jpg" >}}
    {{< divclose >}}
    {{< div class="col-8 col-lg-4 px-n5" >}}
{{< fancy_pics loc="fit"
               caption="FishGuts Prototype 3"
               content="This prototype was made to begin dry testing of a near-complete electrical system. This included pitching and tilting the test jig to test the response of the motors to the jig's change in orientation."
               src="designs/fishguts_proto_3.jpg" >}}
    {{< divclose >}}
{{< divclose >}}

Next, an electronics tray was designed and manufactured before assembling into the
final BlueFish prototype. Several smaller components, such as the voltage converter,
were not included in the CAD modal, but were allocated space during the design process,
along with wire routing. As can be seen, the final assembly required tight packaging.

{{< div class="row justify-content-center align-items-center" >}}
    {{< div class="col-8 col-md-6" >}}
{{< fancy_pics loc="fit"
               caption="E-Tray Model Top"
               content=""
               src="designs/e-tray_model_1.png" >}}
    {{< divclose >}}
    {{< div class="col-8 col-md-6" >}}
{{< fancy_pics loc="fit"
               caption="E-Tray Model Bottom"
               content=""
               src="designs/e-tray_model_2.png" >}}
    {{< divclose >}}
    {{< div class="col-8 col-md-6" >}}
{{< fancy_pics loc="fit"
               caption="E-Tray Top"
               content=""
               src="designs/final_etray_proto.jpg" >}}
    {{< divclose >}}
    {{< div class="col-8 col-md-6" >}}
{{< fancy_pics loc="fit"
               caption="E-Tray Model Bottom"
               content=""
               src="designs/final_etray_proto_2.jpg" >}}
    {{< divclose >}}
{{< divclose >}}



Lastly, I designed a GUI with PyQT5 so that users may communicate with 
the BlueFish and monitor data readings live. This was also made so that 
our group could quickly modify PID settings when testing and tuning 
the device. However, time constraints and a limitation of the python 
plotting library used prevented me from completing a working version
of the live plotting feature. Nonetheless, the GUI worked well and 
allowed us to update the PID settings and retrieve data without having
to extract the Blue Fish.

{{< div class="row justify-content-center align-items-center" >}}
    {{< div class="col-8" >}}
{{< fancy_pics loc="fit"
               caption="BlueCommand GUI - Settings Tab"
               content="This tab allowed users to customize the log file naming and make notes about the test before pushing settings to th BlueFish (which also subsequently created a new CSV file for data logging)."
               src="designs/blue_command_gui_settings.png" >}}
    {{< divclose >}}
    {{< div class="col-8" >}}
{{< fancy_pics loc="fit"
               caption="BlueCommand GUI - Data Plotting Tab"
               content="While developing this feature, I was unaware that the python plotting library, matplotlib, required the figure to be created/updated in the main thread of the program. Upon finding this out during a test run, it was decided that live plotting was not enough of a priority to spend time refactoring this feature's code."
               src="designs/blue_command_gui_data_plot.png" >}}
    {{< divclose >}}
{{< divclose >}}

# The Results

{{< div class="row justify-content-center align-items-center" >}}
    {{< div class="col-8 col-lg-4" >}}
Throughout the project, several experiments were done to test everything 
from the hydrodynamic stability to individual sensor validation. For major
milestone tests, such as hydrodynamic testing, waterproof validation tests, 
and depth control tests, we created the {{< rawhtml >}}<a href="https://1drv.ms/u/s!Anbv5JHlV1c6i1dmcOnqw854dTxI?e=lMlNE7" target="_blank">
test plans and reports found here</a> {{< /rawhtml >}}.

Although we intended to do more testing and PID tuning with the final
assembly, logistical problems delayed the completion of the last 
BlueFish build and the availability of testing equipment. That being said, 
from preliminary testing, results look promising. The following videos show 
dry testing of the tilt correction and a wet test of the final BlueFish 
prototype. 
    {{< divclose >}}    
    {{< div class="col-8 col-lg-4" >}}
{{< video src="results/dry_tilt_test.mp4" 
          controls="true" 
          autoplay="false" 
          loop="true" 
          muted="true" 
          width="80%">}}
    {{< divclose >}}
    {{< div class="col-8 col-lg-4" >}}
{{< video src="results/dock_test.mp4" 
          controls="true" 
          autoplay="false" 
          loop="true" 
          muted="true" 
          width="80%">}}
    {{< divclose >}}
{{< divclose >}}

As shown above, final testing unfortunately only took place off of a 
dock, rather than with a boat. We were thus unable to get the BlueFish 
into a steady-state mode for extended periods of time. However, 
the graphs below show that in the brief steady-state conditions that
were observable (~7-20 seconds elapsed time), the BlueFish was relatively 
stable given how little PID tuning done during testing.

{{< div class="row justify-content-center align-items-center" >}}
    {{< div class="col-8 col-md-5" >}}
{{< fancy_pics loc="fit"
               caption="Depth"
               content="With a target depth of 0.5 meters below surface level, it can be seen that the BlueFish successfully dives from 0.3 m and retains an error of about ±0.1 m in depth. Given this was done with no PID tuning, this result was promising given the potential room for improvement with more control system development."
               src="results/depth.png" >}}
    {{< divclose >}}
    {{< div class="col-8 col-md-5" >}}
{{< fancy_pics loc="fit"
               caption="Roll"
               content="Roll remained between -1 and -5 degrees. The observed offset was theorized to be due to the method of towing the BlueFish from the edge of a dock, introducing a slight roll moment. However, without tuning the PID, the BlueFish still manages to obtain the ±3° of roll targeted in the objectives (neglecting the offset)." 
               src="results/roll.png" >}}
    {{< divclose >}}
    {{< div class="col-8 col-md-5" >}}
{{< fancy_pics loc="fit"
               caption="Pitch"
               content="In rough steady-state, the BlueFish maintained a pitch between -1° and 4°, suggesting that the BlueFish met the original design objectives. However, it's likely that proper buoyancy and PID tuning with a more consistent input speed (such as a boat) would provide improved results." 
               src="results/pitch.png" >}}
    {{< divclose >}}
{{< divclose >}}

# Conclusion and Recommendations 
Overall, the project was successful in creating a functional BlueFish 
prototype, along with documentation of its design, analysis, and testing. 
It was also found that the prototype met the client's requirements. However, 
testing showed that there is plenty of room for further refinement of the
mechatronic system and mechanical designs. Nonetheless, our team completed an 
initial prototype that was deemed worthy of continued development towards a 
marketable product.

## Future Work
While early results were promising, much more testing needs to be done on
the BlueFish, especially at more representative depths while being towed 
by a boat. However, several areas of improvement were identified:
* The 3D printed nosecone and tail designs need to be modified to a split
design suitable for vacuum casting.
  * With this split, mounting of several components, like the lights and camera,
  can be significantly simplified.
  * Collectively, these changes will lower the final bill of materials cost
* The Arduino could be replaced by a Pixhawk flight controller to better
integrate with the rest of Blue Robotics' existing software and development 
architecture.
* Significant work should be done to tune the PID settings of the BlueFish as
we were unable to spend time doing so during testing.
* The implementation of live data plotting should be modified to run in the 
main thread of the BlueCommand GUI.
* Camera integration needs to be finished to create photomosaics of the seafloor.
* The BlueCommand software still presents some bugs which need to be corrected,
along with some small quality-of-life improvements.

**{{< rawhtml >}}<a href="Final Report - MECH 400.pdf" target="_blank">Click here to see the full final report on this project, 
including more details on future work.</a>{{< /rawhtml >}}**

