## 🚀 THE 20-DAY FORGE AVIONICS FLIGHT PLAN

Project Target: 2,500 Coins for the Framework Laptop

Tracking Tool: Laptop Screenshot Capture / Desktop Timelapse Recorder

Design Environment: EasyEDA Pro (PC Desktop App) & Onshape (Browser)

Strict Project Constraints: Circular/Slim form-factor matching a standard 24.1mm BT-50 body tube (PCB size restricted to 22mm x 75mm).

-------

## 📅 THE EXACT DAILY BREAKDOWN
### WEEK 1: Schematic Mastery & Library Engineering

## Oct 4 (Sunday) | ⏱️ 19:00 - 23:00 (4.0 Hours)

* Project Phase: Environment Configuration & Component Placement
* Task List:
* Boot up your screen recorder / time-tracking software.
   * Open EasyEDA Pro; initialize project Forge_Rocket_Avionics.
   * Search, audit, and place primary footprints: Raspberry Pi Pico (or Seeed Xiao RP2040), BMP280 Barometric Sensor, and MPU6050 6-Axis Motion Sensor.
* Deliverable: Project canvas saved with decoupled microcontrollers and core sensors placed.

## Oct 5 (Monday - Long School Day) | ⏱️ 20:00 - 22:30 (2.5 Hours)

* Project Phase: Primary I2C Data Bus Routing
* Task List:
* Wire the common digital communication rails.
   * Route Pico GP4 (SDA) to BMP280 SDA and MPU6050 SDA.
   * Route Pico GP5 (SCL) to BMP280 SCL and MPU6050 SCL.
   * Set up pull-up resistors (4.7kΩ) on both data lines to pull them up to the 3.3V rail for signal stability.

## Oct 6 (Tuesday - Long School Day) | ⏱️ 20:00 - 22:30 (2.5 Hours)

* Project Phase: Power Delivery Network (PDN) Engineering
* Task List:
* Design the system power safety scheme.
   * Add a 3.7V LiPo battery input terminal connector.
   * Integrate a low-dropout (LDO) linear voltage regulator (like the AP2112K-3.3) to cleanly drop raw battery voltage down to a stable 3.3V for the sensitive sensors.
   * Place 10uF and 0.1uF ceramic filtering capacitors near the voltage input and output pins to eliminate electrical noise.

## Oct 7 (Wednesday - Hobby Night) | ⏱️ 20:30 - 23:00 (2.5 Hours)

* Project Phase: Black-Box Telemetry Storage Integration
* Task List:
* Integrate a MicroSD Card SPI connection block.
   * Wire the high-speed data pins from the Pico to the SD card terminal: MOSI (Master Out Slave In), MISO (Master In Slave Out), SCK (Serial Clock), and CS (Chip Select).
   * Add defensive 10kΩ pull-up resistors to the CS line to ensure the SD card doesn't glitch or erase during high-vibration launch states.

## Oct 8 (Thursday) | ⏱️ 18:30 - 23:00 (4.5 Hours)

* Project Phase: Pyro-Channel Pyrotechnic Deployment System
* Task List:
* Design the high-current circuit that will trigger the parachute.
   * Place an N-Channel MOSFET transistor (e.g., IRLZ44N) to act as a heavy-duty switch.
   * Wire a digital output pin from the Pico to the Gate pin of the MOSFET through a 220Ω resistor.
   * Connect a high-current screw terminal block to the Drain pin where the virtual parachute heating wire will plug in. Add a flyback diode (1N4007) across the terminals to block unexpected voltage spikes.

## Oct 9 (Friday) | ⏱️ 18:30 - 23:00 (4.5 Hours)

* Project Phase: Comprehensive Electrical Rule Check (ERC)
* Task List:
* Review every line of your completed schematic blueprint.
   * Run EasyEDA’s built-in Design Rule Check tool to scan for unconnected components or shorted power wires.
   * Assign exact physical production footprints to every resistor, capacitor, and connector you used.

## Oct 10 (Saturday - Full Hackathon Day) | ⏱️ 09:00 - 13:00 & 14:00 - 18:30 (8.5 Hours)

* Project Phase: Netlist Migration & Circular Board Boundaries
* Task List:
* Import your audited schematic data directly into EasyEDA’s PCB Layout window.
   * Define a strict physical board limit: change the standard square board into a slim rectangle measured to exactly 22.0mm wide and 75.0mm long.
   * Arrange the physical footprints logically: place the heavy Pico in the absolute center for weight balance, place the sensors at the top edge away from power lines, and place the terminal blocks on the bottom edge.

## Oct 11 (Sunday - Full Hackathon Day) | ⏱️ 09:00 - 13:00 & 14:00 - 18:30 (8.5 Hours)

* Project Phase: Power Rail Routing & Track Width Calculations
* Task List:
* Begin manually routing traces. Do not use the autorouter!
   * Route the heavy power lines (GND, VBAT, 3.3V) with extra thick traces (0.5mm to 0.8mm width) to ensure they can carry high currents without overheating.
   * Route your sensitive data paths (SDA, SCL, SPI lines) with thin, clean traces (0.2mm width) keeping them straight and direct.

-----------

## WEEK 2: High-Density PCB Architecture & Signal Layering

## Oct 12 (Monday - Long School Day) | ⏱️ 20:00 - 22:30 (2.5 Hours)

* Project Phase: High-Speed Telemetry Signal Tracing
* Task List:
* Route the complicated connections between the Pico and the MicroSD Card block.
   * Ensure all SPI data traces match in length as closely as possible to prevent signal delays or corrupted logs when writing fast data at launch.

## Oct 13 (Tuesday - Long School Day) | ⏱️ 20:00 - 22:30 (2.5 Hours)

* Project Phase: Ground Plane Engineering
* Task List:
* Generate a solid copper ground pour on the top and bottom layers of the PCB.
   * Drop multiple thermal vias (connecting copper holes) through the board to tie the top and bottom ground planes together. This shields the data traces from radio interference and serves as a heatsink for the system.

## Oct 14 (Wednesday - Hobby Night) | ⏱️ 20:30 - 23:00 (2.5 Hours)

* Project Phase: Silkscreen Graphics & Label Detailing
* Task List:
* Switch to the textual overlay layer (Silkscreen text).
   * Write clear text labels for every pin terminal, draw clear polarity signs (+ / -) near the battery terminal, and add custom vector text (e.g., "FORGE AVIONICS v1.0"). Add pinout maps for the Pico so it is easy to debug.

## Oct 15 (Thursday) | ⏱️ 18:30 - 23:00 (4.5 Hours)

* Project Phase: Final 3D Board Verification
* Task List:
* Run a complete 3D Design Rule Check (DRC) to confirm no copper lines are too close together.
   * Open EasyEDA Pro's integrated 3D Canvas Viewer. Inspect all component heights, clear any mechanical interference bugs, and export the finished board as a universal 3D file format (.STEP).

## Oct 16 (Friday) | ⏱️ 18:30 - 23:00 (4.5 Hours)

* Project Phase: Onshape CAD Environment Launch
* Task List:
* Switch over to browser modeling. Open Onshape.
   * Create a clean design document named Forge_Avionics_Chassis.
   * Import the .STEP file of your custom PCB that you exported from EasyEDA. Use Onshape's modeling tools to construct a perfect 3D cylinder representing the outer walls of the Estes BT-50 rocket tube (24.1mm inner diameter).

## Oct 17 (Saturday - Full Hackathon Day) | ⏱️ 09:00 - 13:00 & 14:00 - 18:30 (8.5 Hours)

* Project Phase: Avionics Structural Sled Design
* Task List:
* Build the structural carriage that slides inside the rocket.
   * Extrude a custom plastic frame (sled) shaped to slide perfectly into your 24.1mm circular tube.
   * Model physical slot rails inside the sled where your 22mm PCB will slide in and lock in place without needing heavy screws.

## Oct 18 (Sunday - Full Hackathon Day) | ⏱️ 09:00 - 13:00 & 14:00 - 18:30 (8.5 Hours)

* Project Phase: Battery Enclosure & Structural Weight Relief
* Task List:
* Design a secure structural pocket on the back side of your plastic sled to hold a 3.7V Lithium-Polymer battery block.
   * Incorporate retaining brackets or zip-tie holes into the plastic wall to prevent the battery from shifting under high G-forces. Use pocketing cuts to remove unneeded plastic material to keep the sled ultra-lightweight.

------------------------------
## WEEK 3: Aerodynamic Mechanicals & Structural Optimization## Oct 19 (Monday - Long School Day) | ⏱️ 20:00 - 22:30 (2.5 Hours)

* Project Phase: Retaining Cap Design
* Task List:
* Model the top cap of the sled.
   * Create a solid circular bulkhead cap with an eyelet ring at the top where the parachute shock cord can safely tie on.
   * Incorporate pass-through holes through the bulkhead wall so the deployment wires can run up to the parachute bay.

## Oct 20 (Tuesday - Long School Day) | ⏱️ 20:00 - 22:30 (2.5 Hours)

* Project Phase: Aerodynamic Nose Cone Architecture
* Task List:
* Move beyond the electronics bay to design the structural parts of the rocket.
   * Use Onshape’s Revolve tool to draw a mathematically optimized, low-drag aerodynamic nose cone (Ogiva profile) scaled to snap seamlessly onto the front of your rocket body tube.

## Oct 21 (Wednesday - Hobby Night) | ⏱️ 20:30 - 23:00 (2.5 Hours)

* Project Phase: Stabilizing Fin Geometry
* Task List:
* Design the rear stability system.
   * Model a set of three aerodynamic stabilizing fins (swept-wing profile).
   * Incorporate an alignment ring at the base of the fins so they slide perfectly onto the rear end of the rocket body tube with perfectly square 120-degree spacing.

## Oct 22 (Thursday) | ⏱️ 18:30 - 23:00 (4.5 Hours)

* Project Phase: Spring-Loaded Parachute Ejection Mechanism
* Task List:
* Model a tiny mechanical latch system inside your sled.
   * Design a small hatch door held down by a release arm. When the electronic switch heats up, it will cut a simple rubber band or trigger a micro lever, letting a compressed spring push the hatch open to throw the parachute out.

## Oct 23 (Friday) | ⏱️ 18:30 - 23:00 (4.5 Hours)

* Project Phase: Assembly Analysis & Material Budgeting
* Task List:
* Bring all your separate Onshape models together into a master Assembly file.
   * Combine the nose cone, body tube, fin alignment ring, electronics sled, and PCB. Use Onshape's interference tools to verify that every single piece fits together perfectly without a single mistake.

## Oct 24 (Saturday - Full Hackathon Day) | ⏱️ 09:00 - 13:00 & 14:00 - 18:30 (8.5 Hours)

* Project Phase: Mechanical Blueprint Engineering & Exploded Views
* Task List:
* Generate a detailed, technical multi-page engineering drawing sheet (.PDF format blueprint).
   * Create an Exploded View diagram with callout bubbles showing exactly how the PCB, battery, wires, and structural sled fit together piece-by-piece, ready for an assembly video presentation.

## Oct 25 (Sunday - Full Hackathon Day) | ⏱️ 09:00 - 13:00 & 14:00 - 18:30 (8.5 Hours)

* Project Phase: Final Portfolio Review & Render Engineering
* Task List:
* Render photorealistic project presentation media inside Onshape.
   * Apply proper material finishes (glossy fiber PCB substrate, copper traces, matte plastic sled walls).
   * Take beautiful, high-resolution screenshots and screen-recordings of your master digital prototype for your final showcase.

------------------------------
## 🛠️ THE EVERYDAY FLIGHT ROUTINE (YOUR 4-STEP REPEATABLE LOG)
To protect your 7.5 coins/hour multiplier and prevent any tracking software errors from dropping your rate, follow this exact routine every single day:

   1. The Pre-Flight Check (First 5 Minutes): Clear your desk, close all gaming apps or distracting tabs, boot up your screen capture/timelapse software, and make sure it is actively recording your main work monitor.
   2. The Focus Session (Deep Work Block): Keep your focus entirely inside EasyEDA Pro or Onshape. Keep your mouse moving, draw traces, adjust dimensions, and update files. Continuous movement guarantees that your tracking system records every minute of your work.
   3. The Project Export (Last 10 Minutes): Stop designing. Save your master design file, create a local backup, export a quick screenshot or 5-second video clip of the component or trace you built today, and close your software.
   4. The Ship Submission (Before Bed): Open the Hack Club Slack channel #forge. Post your daily log using this exact structure to lock in your progress:
   
   🚀 FORGE DEVLOG - PROJECT AVIONICS - [INSERT TODAY'S DATE]
   - Today I completed the design layout for [insert what you built today, e.g., the SPI SD card data rails].- Successfully verified all trace dimensions using the integrated 3D inspection view.
   - [Attach your daily screenshot or video clip showing your progress].
   
   Total time spent today: X.X Hours
   
   
------------------------------
## 🏗️ STRUCTURING THE PROJECT BLUEPRINT FOR SUBMISSION
When you click the final "Ship Project" button on November 23, your GitHub project directory needs to be exceptionally clean and well-structured so the Hack Club community reviewers can instantly approve your 2,500 coins. Organize your repository exactly like this:

├── 📂 hardware-blueprints/          # The full circuit board files
│   ├── 📄 avionics_schematic.json   # EasyEDA Pro project schematic file
│   └── 📄 avionics_pcb_layout.json  # EasyEDA Pro physical PCB layout file
├── 📂 mechanical-cad/               # All mechanical engineering assets
│   ├── 📄 avionics_sled_assembly.step # Complete 3D CAD model of the internal carriage
│   └── 📄 rocket_nosecone_bt50.step # 3D model of the matching nose cone piece
├── 📂 documentation/                # High-fidelity project records
│   ├── 📄 engineering_blueprint.pdf # Full dimensioned assembly drawing sheets
│   └── 🖼️ flight_computer_3d_render.png # Photorealistic rendering of the device
├── 📄 JOURNAL.md                    # Master log compiling every daily Slack post
└── 📄 README.md                     # The final project summary document

## 📝 The README.md Golden Template
Your root README.md file should serve as a professional front page for your project. Copy and paste this framework into your repository:

# 🚀 Custom Model Rocket Flight Computer & Avionics CarriageDesigned for Tier III Forge by Hack Club
## 📋 Project AbstractThis project is a complete, high-density avionics hardware prototype designed to fit inside a standard 24.1mm Estes BT-50 rocket body tube. The system integrates a dual-core RP2040 microcontroller processing architecture with a high-accuracy BMP280 barometric altimeter for apogee tracking and an MPU6050 accelerometer for launch detection, recording high-speed data to a MicroSD card.
## 🛠️ System Engineering Features- **Strict Size Limitations:** 22mm x 75mm 2-layer PCB designed inside EasyEDA Pro.- **Integrated Power Delivery:** On-board AP2112K low-dropout regulator converting LiPo power to a stable 3.3V for internal components.- **High-Current Deployment:** Built-in N-Channel MOSFET circuit designed to trigger parachute mechanisms at apogee.- **Custom Internal Carriage:** 3D-modeled avionics sled built in Onshape featuring snap-fits for the circuit board and a dedicated battery compartment.
## 📁 Engineering Assets & Deliverables- Fully routed manufacturer-ready 2-layer PCB schematic and layout files.
- Exported 3D CAD assembly files (`.STEP`) for all structural hardware.- Complete technical assembly drawing sheets including exploded design views.

------------------------------
Your entire virtual engineering pipeline is mapped out and requires zero budget or shipping delays! To ensure you start off strong, let me know:

* Have you already downloaded and logged into the EasyEDA Pro desktop software?
* Would you like me to help you generate the exact text description for your first HCB project submission so your group registration gets approved right away?


