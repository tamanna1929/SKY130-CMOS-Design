# SKY130-CMOS-Design
CMOS Circuit Design and SPICE Simulation using SKY130 Technology Workshop
<br>![banner-1024x683 png](https://github.com/user-attachments/assets/9c1ef691-4a17-4245-b2d6-d7bbe1017618)
<br>**Brief description of the course**
<br>This ten-day workshop, organized by VLSI System Design, was centered on CMOS circuit design and SPICE simulation using SKY130 technology. The sessions were structured progressively, beginning with the basics of NMOS device structure and operation, and gradually moving towards advanced CMOS inverter analysis. We explored transistor behavior in different operating regions, simulated DC and transfer characteristics, and studied inverter switching thresholds. The workshop further emphasized CMOS robustness by analyzing noise margins, power supply variations, and device-level variations. It concluded with discussions on process-related effects, such as oxide thickness and etching variations, and their impact on circuit performance.
<br>**Key learnings and practical work included:**
<br>1.Understanding NMOS structure and its performance in cutoff, resistive, and saturation regions.
<br>2.Performing SPICE simulations for NMOS I–V characteristics and CMOS inverter transfer curves.
<br>3.Analyzing CMOS inverter switching thresholds and deriving relations with device sizing (W/L ratios).
<br>4.Evaluating inverter robustness through noise margin analysis and supply voltage variations.
<br>5.Studying process variations (oxide thickness, etching) and their influence on single inverters and inverter chains.
<bR>**INDEX**
<ul>
      <li>Basics of NMOS Drain Current (Id) vs Drain-to-source Voltage (Vds)
        <ul>
          <li>Part 1: Introduction to Circuit Design and SPICE Simulation (Id)</li>
          -What was learnt
          <li>Part 2: NMOS Resistive region and Saturation region of operation (Id)</li>
          -What was learnt
          <li>Part 3: Introduction to SPICE</li>
          -What was learnt
          <br>-Lab Activity
        </ul>
      </li>
      <li>Velocity Saturation and basics of CMOS inverter VTC
        <ul>
          <li>Part 1: SPICE Simulation for lower nodes and velocity saturation effect</li>
          -What was learnt
          <br>-Lab Activity
          <li>Part 2: CMOS voltage transfer characteristics (VTC)</li>
          -What was learnt
        </ul>
      </li>
      <li>CMOS Switching threshold and dynamic simulations
        <ul>
          <li>Part 1: Voltage transfer characteristics and SPICE simulations</li>
          -What was learnt
          <br>-Lab Activity
          <li>Part 2: Static behavior evaluation- CMOS inverter robustness- Switching threshold</li>
          -What was learnt
        </ul>
      </li>
      <li>CMOS Noise Margin robustness evaluation
        <ul>
          <li>Part 1: Static behavior evaluation- CMOS inverter robustness- Noise margin </li>
          -What was learnt
          <br>-Lab Activity
        </ul>
      </li>
      <li>CMOS power Supply and device variation robustness evaluation
        <ul>
          <li>Part 1: Static behavior evaluation- CMOS inverter robustness- Power supply variation </li>
          -What was learnt
          <br>-Lab Activity
          <li>Part 2: Static behavior evaluation- CMOS inverter robustness- Device variation </li>
          -What was learnt
          <br>-Lab Activity
        </ul>
      </li>
    </ul>
  </li>
</ul>
<ul style="list-style-type: circle;">
  <li>Conclusion</li>
  <li>References</li>
</ul>
<h2>Basics of NMOS Drain Current (Id) vs Drain-to-source Voltage (Vds)</h2>
The first session of the workshop emphasized the role of SPICE as an essential tool for circuit simulation and analysis, and demonstrated how it can be used to tune cell delays by varying the W/L ratio. We explored the fundamentals of NMOS transistors, including threshold voltage and the distinct regions of operation—cut-off, linear (resistive), and saturation. We also understand the behavior of drain current (Id) with respect to drain-to-source voltage (Vds). The session concluded with a practical exercise, where SPICE was set up and used to simulate Id–Vds characteristics at different gate-to-source voltages (Vgs), effectively bridging theoretical knowledge with hands-on practice.
<ul>
  <h3>Part 1: Introduction to Circuit Design and SPICE Simulation </h3>
  <h4>What was learnt</h4>
   In this we learnt how SPICE can be used to study the device behaviour by simulating the circuits and analyzing the waveforms. W/L ratio is an important parameter in deciding the device performance. 
    <br>We study the structure of NMOS- it consists of a p-type substrate, has 4 terminals (G,S,D,B), an isolation region created from SiO2 is present to isolate different devices, 2 n+ diffusion regions known as source and drain near the isolation region, a gate oxide layer deposited on the substrate followed by a poly-Si or metal gate layer on top of it. 
   <br>G stands for gate
    <br>S stands for source
    <br>D stands for drain
    <br>B stands for body
    <br>Body terminal can be used to tune the threshold voltage.
    <br>![WhatsApp Image 2025-08-20 at 23 30 42](https://github.com/user-attachments/assets/9066bd97-a346-429d-a059-898c850275c0)

    <b>Threshold Voltage (Vt)</b>- This is the minimum gate-to-source voltage (Vgs) required to form a conducting channel at the semiconductor surface or we can say that this is the voltage where "strong inversion" happens.
    <br>
    <b>Strong Inversion</b>- When Vgs is sufficiently large, the surface inverts to n type, creating a channel of mobile electrons that allows current to flow from drain to source.
    <br>2 cases were discussed:
    <br>1. Vsb=0; here no body bias is applied. In this case, the threshold voltage remains at its nominal value and strong inversion occurs as soos as Vgs exceeds this value
    <br>2. Vsb?0; here a +ve source-to-body bias is applied. This increases the depletion charge in the channel region and thereby raises the threshold voltage (body effect). As a result, a larger Vgs is required to reach strong inversion.
    <br>"In the presence of Vsb, additional potential is needed for strong inversion."
    <br><b>Threshold Voltage Equation</b>b>
    <br>V<sub>T</sub> = V<sub>T0</sub> + γ ( √(|-2φ<sub>F</sub> + V<sub>SB</sub>|) − √(|-2φ<sub>F</sub>|) )
    <br>where
    <br>V<sub>T0</sub> is the threshold voltage when Vsb=0 and is a function of manufacturing process
    <br>γ  is the body effect coefficient and it expresses the impact of changes in body bias Vsb ( γ  has the units of V^0.5)
    <br>φ<sub>F</sub> is the fermi potential
    <br>
    <br><b>Body effect coefficient expression</b>
   <br>γ = ( √(2 q ε<sub>si</sub> N<sub>A</sub>) ) / C<sub>ox</sub>
    <br>where
    <br> ε<sub>si</sub> is the relative permitivity of silicon (=11.7)
    <br>N<sub>A</sub>is the doping concentration
    <br>q is the charge of an electron
    <br>Cox is the oxide capacitance
    <br>
    <br><b>Fermi potential equation</b>
    <br>φ<sub>F</sub> = -φ<sub>T</sub> ln( N<sub>A</sub> / n<sub>i</sub> )
    <br>where n<sub>i</sub> is the intrinsic doping parameter for the substrate.
    <br>
     <h3>Part 2: NMOS Resistive region and Saturation region of operation</h3>
     <h4>What was learnt</h4>
     The resistive region, also known as linear region of operation, occurs when the transistor operates with Vgs=Vt, and further changes can be observed when Vgs>Vt. In this region, the induced charge Qi is proportional to (Vgs-Vt). For analysis, we took 
    <br>Vgs=1V, Vds=0.05V, Vt=0.45V
    <br>When Vds=0, the voltage across the n channel remains constant but not the case when Vds is applied due to potential gradient across the channel as source is at 0V but drain at 0.05V.
    <br>Let the effective channel length be L and 'x' axis be along the channel length and 'y' axis be perpendicular to the channel length. Let V(x) be the voltage at any point 'x' along the channel. Now, Vgs-V(x) is the gate-to-channel voltage at that point.
<br>Therefore, in the channel, induced charge at any point 'x' Q<sub>i</sub>(x) ∝ − ( V<sub>GS</sub> − V(x) − V<sub>T</sub> )
<br>Formula for charge induced at any point ‘x’
<br>Q<sub>i</sub>(x) = − C<sub>ox</sub> ( V<sub>GS</sub> − V(x) − V<sub>T</sub> )
<br>Gate oxide capacitance formula C<sub>ox</sub> = &epsilon;<sub>ox</sub> / t<sub>ox</sub>
<br>where
    <br>εox is the oxide permittivity = 3.97εo = 3.510e-11 F/m
    <br>tox is the oxide thickness

<br> From device point of view, we have 2 types of current
<br>Drift Current: Current due to potential difference
<br>Diffusion Current: Current due to difference in carrier concentration
<br>Here we are only talking about the drift current (Id) that is from source to drain.
<br> Id=velocity of charge carriers* available charge over channel width
<br>![Uploading WhatsApp Image 2025-08-20 at 23.32.14.jpeg…]()

<br>
<b>Drift current (Id) formula</b>
<br>I<sub>D</sub> = μ<sub>n</sub> C<sub>ox</sub> (W/L) [ (V<sub>GS</sub> − V<sub>T</sub>) V<sub>DS</sub> − (V<sub>DS</sub><sup>2</sup> / 2) ]
<br>The term µn.Cox is denoted by kn' and kn' is known as process transconductance
<br>kn'.(W/L) is denoted by kn and kn is also known as gain factor
<br>Condition on Vds for the MOSFET to be in linear/resistive region or saturation/pinch-off region
<br>When Vds <= (Vgs-Vt), the MOSFET is in linear region of operation
<br>For this region, Id=kn.(Vgs-Vt).Vds as (Vds^2)/2 is a very small amount in this case
<br>Vdds can be sweeped from 0V to (Vgs-Vt)V to make the device work in linear region of operation
<br> Dependance of Id on Vds in pinch-off region: The chanel voltag
e is denoted with Vgs-Vds.
<br>![WhatsApp Image 2025-08-20 at 23 32 14 (1)](https://github.com/user-attachments/assets/da4b26f3-dda6-48a3-bf45-b91488917c67)

<b>Pinch-off condition</b> is when Vgs-Vds=Vt
<br>When the Pinch-off phenomenon is started, the channel begins to disappear. Basically, the channel starts to disappear only from the Drain side acquiring a triangular shape.
When Vgs-Vds<Vt, there is no channel present near the Drain terminal.Id becomes (kn/2).(Vgs-Vt)^2
<br>Looks like a perfect current source but in reality it is not true because the effective conductive channel length can be still changed by applying Vds.
<br>As Vds increases, more area of channel near the drain terminal will disappear resulting in decrease in effective channel length.
<br><b>New modified drain current equation</b>
    <br>I<sub>D</sub> = (K<sub>n'</sub>)/2) (W/L) [ ((V<sub>GS</sub> − V<sub>T</sub>))<sup>2</sup>[1+λV<sub>DS</sub>]
<br>Here, λ is the channel length modulation
    <br>
<h3>Part 3: Introduction to SPICE</h3>
<h4>What was learnt</h4>
<br>SPICE is a software/engine which already have predefined models which can be used to calculate waveforms and delays by inserting the input values. 
<br>SPICE model parameters also known as technological constant nodes, which come from foundaries and is listed in the model file which we provide to the engine. Example: Vt0, kn', λ, γ
<br>These are the 1st level inputs
<br>Levels of SPICE simulation- 1st level input is SPICE model parameters+Spice netlist, these are given to the SPICE Software to get required SPICE waveform.
<br>![WhatsApp Image 2025-08-20 at 23 31 30](https://github.com/user-attachments/assets/fc3ecaea-061f-411b-8587-2342bcb3b391)

<br>https://user-images.githubusercontent.com/89193562/132711027-1aa941dc-56bc-4be9-af32-5a96b76d9c09.jpg
<br>A node is a point that connects two terminals. When two terminals of the same device are short-circuited, the node exists between them. In most cases, however, a node connects multiple devices. Nodes can be identified in a SPICE netlist, where every wire linking different components corresponds to a unique node.
<h4>Lab Activity</h4>
    <br> The following code is used for day1 lab activity
<br>*Model Description
.param temp=27

*Including sky130 library files
.lib "sky130_fd_pr/models/sky130.lib.spice" tt

*Netlist Description

XM1 Vdd n1 0 0 sky130_fd_pr__nfet_01v8 w=0.65 l=0.25
R1 n1 in 55
Vdd vdd 0 1.8V
Vin in 0 1.8V

*simulation commands

.op
.dc Vdd 0 1.8 0.1 Vin 0 1.8 0.2

.control

run
display
setplot dc1
.endc

.end
<br>In the lab activity, tt(typical corner) corner is used.
<br>![VirtualBox_vsdworkshop_15_08_2025_18_05_15](https://github.com/user-attachments/assets/96ef8322-12f2-4932-9007-4bfa6d5f7d56)
<br>![VirtualBox_vsdworkshop_15_08_2025_18_05_35](https://github.com/user-attachments/assets/82230928-d2dc-4d60-ae12-20b42381db43)
<br>![VirtualBox_vsdworkshop_15_08_2025_18_05_46](https://github.com/user-attachments/assets/4cf6d045-408e-47f3-a5db-579d077acc13)
<br>By left click on the point on the required curve, we get the value of Id at that point as displayed in the the form of y0 in figure and y0 is value of Id in amperes.
<br>
<h2>Velocity Saturation and basics of CMOS inverter VTC</h2>
In the Second session of the workshop, SPICE simulations were carried out for lower technology nodes, and the characteristics of both long-channel and short-channel devices were studied. The concepts of velocity saturation at low and high electric fields, along with the drain current model under velocity saturation, were also explored.
<br>At the end of this session, we studied about the operation of MOSFET as a switch and analysis of the CMOS inverter characteristics.
<h3>Part 1: SPICE Simulation for lower nodes and velocity saturation effect</h3>
 <h4>What was learnt</h4>
  We did some SPICE Simulation for two  devices whose channel width and channel length is different but there width by length ratio(W/L) is same .
<br>Case1-    W=1.8u, L=1.2u device (W/L=1.5)
<br>Case2-     W=0.375U, L=0.25 device (W/L=1.5)
<br>As W/L ratio is constant then (Id) at saturation region should be constant . 
<br>Simulate Id  v/s VGS  graph to the difference between two regions
<br>For case 1 – drain current quadratic dependence 
<br>case 2- (Short channel device) Id quadratic change for small current but on increasing gate voltage current increases linearly because of velocity saturation.
<br><b>Formulae of velocity and mobility</b>
<br>v<sub>n</sub>(m/s)=u<sub>n</sub>.dV/dx
<br>
<b>Velocity saturation effect for Short channel length</b>
<br>For lower value of EF velocity tends to linear function of EF but after some time becomes constant.
<br>Vn(m/S) = linear for ε<=εc
<br>Vn(m/S) = constant for ε>=εc
<br>v<sub>n</sub>(m/s)=u<sub>n</sub>. ε/(1+ ε/ε<sub>c</sub>), for ε<=εc
<br>v<sub>n</sub>(m/s)=v<sub>sat</sub> , for  ε>=εc
<br>![WhatsApp Image 2025-08-20 at 23 32 18](https://github.com/user-attachments/assets/032aa7b6-9231-4cd2-b892-6ffa032457c2)

<br>Solve above formulae using continuity equation 
<br>Then re- deriving drain current using the boundary conditions.
<br>Id= -Vn(x). Qi(x).W
<br>After substitiution, Id becomes too complex.
<br>“lets try one model : OPERATINAL MODES”
<br>There are 4 different modes :
<br>1.	Cut off 
<br>2.	Resistive
<br>3.	Velocity saturation
<br>4.	Saturation
<br>(for long channel there is no velocity saturation)
<br>Let's call (Vgs-Vt)=Vgt
<br>I<sub>d</sub>=k<sub>n</sub>.[(V<sub>gt</sub>.V<sub>min</sub>)-(V<sub>min</sub><sup>2</sup>/2][1+λV<sub>ds</sub>]
<br>In Id equation λV<sub>ds</sub> vanishes for low value of Vds
<br>Vmin = min(Vgt, Vds, Vsat)
<br>where Vsat is Technology parameter (saturation voltage) 
<br>When Vgt is the smallest among Vgt, Vds, and Vdsat, the device operates in the saturation region.
<br>When Vds is the smallest, the device operates in the resistive (linear) region.
<br>When Vdsat is the smallest, the device operates in the velocity saturation region.
<br>In general, current tends to increase at lower voltage nodes. Velocity saturation causes the device to enter saturation earlier than expected, limiting further current increase.
<h4>Lab Activity</h4>
<br>We will plot the graph between Id vs Vds for short channel device and following code is needed:
<br>*Model Description
.param temp=27

*Including sky130 library files
.lib "sky130_fd_pr/models/sky130.lib.spice" tt

*Netlist Description

XM1 Vdd n1 0 0 sky130_fd_pr__nfet_01v8 w=0.39 l=0.15
R1 n1 in 55

Vdd vdd 0 1.8V
Vin in 0 1.8V

*simulation commands

.op
.dc Vdd 0 1.8 0.1 Vin 0 1.8 0.2

.control

run
display
setplot dc1
.endc

.end!
<br>![VirtualBox_vsdworkshop_18_08_2025_22_26_05](https://github.com/user-attachments/assets/24021f21-ff58-4a4a-ac42-bc635668626c)
<br>![VirtualBox_vsdworkshop_18_08_2025_22_26_23](https://github.com/user-attachments/assets/f172e705-841c-42b1-b0e5-347df0c96270)


<br>To calculate Threshold voltage for Id versus Vgs curve, the following SPICE code is required:
<br>*Model Description
.param temp=27

*Including sky130 library files
.lib "sky130_fd_pr/models/sky130.lib.spice" tt

*Netlist Description
XM1 Vdd n1 0 0 sky130_fd_pr__nfet_01v8 w=0.39 l=0.15
R1 n1 in 55

Vdd vdd 0 1.8V
Vin in 0 1.8V

*simulation commands

.op
.dc Vin 0 1.8 0.1

.control

run
display
setplot dc1
.endc

.end
<br>![VirtualBox_vsdworkshop_18_08_2025_22_30_02](https://github.com/user-attachments/assets/1b534841-ffb2-4ab0-a6c5-61f9763ecfff)
<br>In order to calculate the Threshold voltage, the linear part of the plot must be extended. Now, the x intercept of this extended plot gives the value of the threshold voltage of the device that is being simulated.
<br>
<h3>Part 2: CMOS voltage transfer characteristics (VTC)</h3>
 <h4>What was learnt</h4>
 <br>![WhatsApp Image 2025-08-20 at 23 32 54](https://github.com/user-attachments/assets/f082d8c1-9e1b-4bf2-a2ee-675b9edfdba1)

 In this Topic we will explore the CMOS topic . Introduce standard MOS voltage parameters creating CMOS using NMOS  and PMOS and plot load current for PMOS and NMOS and at last merge both the curves of NMOS and PMOS to plot VTC.
<br>MOSFET As a Switch: 
<br>Characteristic of MOS device :
<br>Transistor works whenever : |Vgs| > Vt
<br>Transistor acts as a switch with two conditions: 
<br>1.	With infinite OFF resistance when |vgs|<|Vt|
<br>2.	With finite ON resistance when |Vgs|>|Vt|
<br>CMOS: complementary MOS
<br>NMOS+ PMOS = CMOS
<br>For understanding CMOS first have to understand PMOS and NMOS and their voltage current parameters.
<br>1.	When Vin is LOW and equal to ‘0V’ then (PMOS turned ON and NMOS turned OFF)
<br>2.	When Vin = Vdd, for PMOS direct path exists between Vout and Vss resulting Vout=0.
<br>For NMOS Vout = Vdd
<br>CMOS will be made using combination of PMOS and NMOS , Where
<br>•	G= gate
<br>•	S= source
<br>•	D= drain
<br>•	Vgs= Gate- Source voltage
<br>•	Vds = Drain – Source voltage
<br>•	P,N = PMOS and NMOS respectively
<br>•	Idsn= Drain Source current through NMOS
<br>•	Idsp= Drain Source current through PMOS
<br>VTC
<br>1.	To obtain load curve for NMOS and PMOS first have to obtain Idsn V/s Vdsn curve for NMOS and PMOS respectively
<br>By observations , 
<br>Vgsn= Vin-Vss = Vin
<br>VdsN= ‘Vout’
<br>Vgsp = ‘Vin – Vdd’ 
<br>Vdsp = Vout – Vdd
<br>For the relationship between the currents: Idsp=-Idsn
<br>Load curve for PMOS transistor in CMOS inverter
<br>![WhatsApp Image 2025-08-20 at 23 33 24](https://github.com/user-attachments/assets/72792c55-6dfd-4bef-9586-20fcca3481f3)
<br> For NMOS ![WhatsApp Image 2025-08-20 at 23 33 43](https://github.com/user-attachments/assets/c664f97b-897d-40b1-a1d8-d045437e0b28)
<br>for CMOS![WhatsApp Image 2025-08-20 at 23 34 12](https://github.com/user-attachments/assets/81962ab0-85c5-438d-8e76-c4faf0147ad1)








<br><h2>CMOS Switching threshold and dynamic simulations</h2>
<br>In the third session of the workshop, the main focus was on understanding voltage transfer characteristics using SPICE simulations. Later, CMOS inverter robustness was discussed, with a detailed explanation of the switching threshold. It was also shown how the switching threshold relates to the (W/L) ratios of PMOS and NMOS, and how you can find one if the other is preset.
<br>![WhatsApp Image 2025-08-20 at 23 38 18](https://github.com/user-attachments/assets/adff7c10-fada-4adc-ba9e-2bc399543654)

<h3>Part 1: Voltage transfer characteristics and SPICE simulations</h3>
<h4>What was learnt</h4>
<br>SPICE deck has the following components-
<li>Component connectivity</li>
<li>Component values</li>
<li>Identification of nodes</li>
<li>Naming nodes</li>

<br>Let us consider the following SPICE netlist
<br>***MODEL Description***
***NETLIST Description***
M1 out in vdd vdd pmos W=0.375u L=0.25u
M2 out in  0   0  nmos W=0.375u L=0.25u

cload out 0 10f

Vdd vdd 0 2.5
Vin  in 0 2.5

***SIMULATION Commands***
.op
.dc Vin 0 2.5 0.05

***.include tsmc_025um_model.mod***
.LIB "tsmc_025um_model.mod" CMOS_MODELS
.end
<br>
 <h4>Lab Activity</h4>
 <br> Following code is needed for plotting VTC characteristics of CMOS inverter:
 <br>*Model Description
.param temp=27

*Including sky130 library files
.lib "sky130_fd_pr/models/sky130.lib.spice" tt

*Netlist Description

XM1 out in vdd vdd sky130_fd_pr__pfet_01v8 w=0.84 l=0.15
XM2 out in 0 0 sky130_fd_pr__nfet_01v8 w=0.36 l=0.15

Cload out 0 50fF

Vdd vdd 0 1.8V
Vin in 0 1.8V

*simulation commands

.op

.dc Vin 0 1.8 0.01

.control
run
setplot dc1
display
.endc

.end
<br>![VirtualBox_vsdworkshop_19_08_2025_21_24_58](https://github.com/user-attachments/assets/3d3072b5-3384-4986-9199-c47fded29087)
<br>![VirtualBox_vsdworkshop_19_08_2025_21_25_10](https://github.com/user-attachments/assets/1e6e755e-d79e-49a5-8670-a78f09419d7b)
<br>
<li>To find the switching threshold voltage (Vm), look for the region where Vout is about equal to Vin on the plot.</li>
<li>Right-click and drag to select and zoom in on this area a couple of times until the Vm point is clear.</li>.
<li>Left-click near the spot on the curve where Vout should be nearly equal to Vin.</li>
<li>The terminal will show x0 and y0 values.</li>
<li>Since Vm is where Vout equals Vin, you’ll see x0 ≈ y0, so x0 = y0 = Vm.</li>
<br>
<br>For performing the transient analysis, the following code is required:
<br>*Model Description
.param temp=27

*Including sky130 library files
.lib "sky130_fd_pr/models/sky130.lib.spice" tt

*Netlist Description

XM1 out in vdd vdd sky130_fd_pr__pfet_01v8 w=0.84 l=0.15
XM2 out in 0 0 sky130_fd_pr__nfet_01v8 w=0.36 l=0.15

Cload out 0 50fF

Vdd vdd 0 1.8V
Vin in 0 PULSE(0V 1.8V 0 0.1ns 0.1ns 2ns 4ns)

*simulation commands

.tran 1n 10n

.control
run
.endc

.end
<br>![VirtualBox_vsdworkshop_19_08_2025_21_39_24](https://github.com/user-attachments/assets/991cbf04-912a-4cfa-8e3b-3580e4d4faa9)
<br>![VirtualBox_vsdworkshop_19_08_2025_21_39_44](https://github.com/user-attachments/assets/a788378a-605c-4d8b-9e9e-11f30c964485)
<br>
**Rise delay** is the time difference between when the input drops through Vdd/2 and when the output rises through Vdd/2.
<br>
**Fall delay** is the time difference between when the input rises through Vdd/2 and when the output falls through Vdd/2.
<br>
<li>To find rise delay:</li>
<br>Zoom in on the plot section where the input is falling and the output is rising around Vdd/2 by right-clicking and dragging to select.
<br>Left-click on the output’s rising edge at Vdd/2 to note the x0, y0 values shown in the terminal.
<br>Do the same for the input waveform’s falling edge at Vdd/2.
<br>The difference between the x-values at these points gives the rise delay.
<br>
<li>To find fall delay:</li>
<br>Zoom in on the section of the plot where the input is rising and the output is falling near Vdd/2.
<br>Left-click on the output’s falling edge at Vdd/2 and record x0, y0.
<br<Likewise, click on the input’s rising edge at Vdd/2.
<br>The difference in the x-values of these points is the fall delay.
<br>
<h3>Part 2: Static behavior evaluation- CMOS inverter robustness- Switching threshold</h3>
 <h4>What was learnt</h4>
 <br>The CMOS inverter is considered highly robust because its input-output curve maintains the same overall shape, even when the (W/L) ratios change.
<br>
    <li>Key aspects evaluated for static behavior and robustness include:</li>
    -Switching threshold
    -Noise margins
    -Variations in power supply
    -Changes in device characteristics
    <br>Switching Threshold (Vm)
    <br>It is the point where Vin = Vout
    <br>Graphical method to find Vm is to draw a line across the graph of output voltage to input voltage of a CMOS inverter starting at the origin and ending at the opposite diagonal of the plot (basically a line with a 45 degree inclination with the x-axis). Now, the x-coordinate of the point of intersection of this line and the curve is the switching threshold.
<br>Vm when (Wp/Lp) is 1.5 is approximately equal to 0.98V and when (Wp/Lp) is 3.75 it is approximately equal to 1.2V
<br>Wp and Lp in the above section are Width of PMOS channel and Length of PMOS channel
<br>At Vm, both PMOS and NMOS are turned 'ON' because Vgs almost crossed the threshold region for both of them.
<br>A few observations can be made from the information stated above,
<br>Therefore, Vgs = Vds
<br>IdsP = - IdsN which means that IdsP + IdsN = 0
<br>We know the equations for IdsN and IdsP which are as stated below:
<br>I<sub>dsN</sub>=k<sub>n</sub>.[([V<sub>m</sub>-V<sub>t</sub>].V<sub>dsatN</sub>)-V<sub>dsatN</sub><sup>2</sup>/2]
<br>Similarly for PMOS we can replace Idsn by Idsp and Vm by Vm-Vdd, VdsatN by VdsatP
<br>We ignore the 1+λVds because the term is very small and it makes the equations very difficult for hand calculations.
<br>Since, IdsP + IdsN = 0
<br>(W<sub>p</sub>/L<sub>p</sub>)/(W<sub>n</sub>/L<sub>n</sub>)={k<sub>n'</sub>.V<sub>satN</sub>.[(v<sub>m</sub>-V<sub>t</sub>)-V<sub>dsatN</sub>/2]}/{k<sub>p'</sub>.V<sub>satP</sub>.[(-v<sub>m</sub>+V<sub>dd</sub>+V<sub>t</sub>)+V<sub>dsatP</sub>/2]}
<br>Here,
<br>-Wp is the width of the channel in PMOS
<br>-Lp is the length of the channel in PMOS
<br>-Wn is the width of the channel in NMOS
<br>-Ln is the length of the channel in NMOS
<br>-kn' is the process transconductance of the NMOS
<br>-kp' is the process transconductance of the PMOS
<br>-VdsatN is the Vdsat of the NMOS
<br>-VdsatP is the Vdsat of the PMOS
<br>-Vm is the switching threshold voltage
<br>-Vt is the threshold voltage
<br>-Vdd is the supply voltage
<br>We experimented with the sizes of the PMOS with respect to the sizes of NMOS and came up with the following conclusions
<br><table>
  <tr>
    <th>(Wp/Lp)</th>
    <th>(x.Wn/Ln)</th>
    <th>Rise Delay</th>
    <th>Fall Delay</th>
    <th>Vm</th>
  </tr>
  <tr>
    <td>(Wp/Lp)</td>
    <td>1.(Wn/Ln)</td>
    <td>148 ps</td>
    <td>71 ps</td>
    <td>0.99 V</td>
  </tr>
  <tr>
    <td>(Wp/Lp)</td>
    <td>2.(Wn/Ln)</td>
    <td>80 ps</td>
    <td>76 ps</td>
    <td>1.2 V</td>
  </tr>
  <tr>
    <td>(Wp/Lp)</td>
    <td>3.(Wn/Ln)</td>
    <td>57 ps</td>
    <td>80 ps</td>
    <td>1.25 V</td>
  </tr>
  <tr>
    <td>(Wp/Lp)</td>
    <td>4.(Wn/Ln)</td>
    <td>45 ps</td>
    <td>84 ps</td>
    <td>1.35 V</td>
  </tr>
  <tr>
    <td>(Wp/Lp)</td>
    <td>5.(Wn/Ln)</td>
    <td>37 ps</td>
    <td>88 ps</td>
    <td>1.4 V</td>
  </tr>
</table>
<br>From the table, we can conclude the following:
<li>When (Wp/Lp) equals twice (Wn/Ln), the rise and fall delays are nearly equal.</li>
<li>This equal rise-fall delay makes (Wp/Lp) = 2 × (Wn/Ln) ideal for clock inverters or buffers.</li>
<li>Other (Wp/Lp) ratios can still serve as regular inverters or buffers and are often preferred for data paths.</li>
<li>The switching threshold is very low for both (Wp/Lp) = 2 × (Wn/Ln) and (Wp/Lp) = 3 × (Wn/Ln), as well as for (Wp/Lp) = 4 × (Wn/Ln) and (Wp/Lp) = 5 × (Wn/Ln).</li>
<li>Increasing Wp/Lp significantly reduces the rise delay because the output capacitor charges faster due to the larger transistor area.</li>
<li>The resistance of the PMOS transistor is approximately 2.5 times that of the NMOS transistor.</li>
<br>
<h2>CMOS Noise Margin robustness evaluation</h2>
<br>
<h3>Part 1: Static behavior evaluation- CMOS inverter robustness- Noise margin</h3>
<br>In 4th session ,the robustness of a CMOS inverter was studied through the concept of noise margins. The key parameters Voh, Vih, Vil, Vol and the equations for NMh and NMl were derived. In the lab, noise margins were measured for an inverter with (Wp/Lp) = 2.77 × (Wn/Ln).

<br>**Introduction to noise margin**
<br>Ideal and actual Input-Output characteristics of an inverter were observed:
<br>Ideal: Sharp transition between logic 0 and logic 1
………figure…………
<br>When Vin = 0,  Vout = Vdd
<br>If Vin =vdd/2, Vout will tends to zero/ becomes Zero.
<br>Slope, dy/dx = Vd/0 = infinite
<br>Actual: Finite slope, leading to undefined region .
…..figure………..
<br>**Conclusion :**  From above figure  . We observe that
<br>1.	Vil is Input Low Voltage (Vil could be Vdd/4) : input voltage level between 0 and Vil will be treated as logic '0'.
<br>2.	Voh is Output High Voltage (Vih < Voh <= Vdd) : Any output voltage level between Voh and Vdd will be treated as logic '1'.
<br>3.	Vih is Input High Voltage (Vih could be 3.Vdd/4) : Any input voltage level between Vih and Vdd will be treated as logic '1'.
<br>4.	Vol is Output Low Voltage (0 <= Vol < Vil) : Any output voltage level between 0 and Vol will be treated as logic '0'.
<br>Actual graph  of an inverter were observed and they were plotted on a scale:
……………………figure………………
<br>Curve graph plotted because of non idality of diode. Slope of above graph is -1 .

<br>I/o characteristic plotted on scale ( using previous graphs):
…………………..figure………………
<br>1.	NMh (Noise Margin High)  :   Any voltage level in "NMh" range will be detected as logic '1'.
<br>2.	NMl (Noise Margin Low) : Any voltage level in "NMl" range will be detected as logic '0'.
<br>3.	Undefined region  ( Any input between Vil and Vih ) : indefinite logic level
<br>**Noise Margins :** 
<br>•	NMh = Voh – Vih
<br>•	NMl = Vil – Vol

<br>**Noise margin Summary :** 
…………………..figure…………….
<br>1.	 Vol to Vil → Glitches in this range are safe, as the signal is still recognized as logic ‘0’.
<br>2.	 Vil to Vih (Undefined Region) → Glitches here are unsafe, since the logic level is uncertain and may cause errors.
<br>3.	Vih to Voh → Glitches in this range are critical, as they are always interpreted as logic ‘1’ and must be eliminated.
<br>The noise margins of the inverter at different values of Wp/Lp were observed and they were as follows:
<br><table>
  <tr>
    <th>(Wp/Lp)</th>
    <th>(x.Wn/Ln)</th>
    <th>NMh</th>
    <th>NMl</th>
    <th>Vm</th>
  </tr>
  <tr>
    <td>(Wp/Lp)</td>
    <td>1.(Wn/Ln)</td>
    <td>0.3</td>
    <td>0.3</td>
    <td>0.99 V</td>
  </tr>
  <tr>
    <td>(Wp/Lp)</td>
    <td>2.(Wn/Ln)</td>
    <td>0.35</td>
    <td>0.3</td>
    <td>1.2 V</td>
  </tr>
  <tr>
    <td>(Wp/Lp)</td>
    <td>3.(Wn/Ln)</td>
    <td>0.4</td>
    <td>0.3</td>
    <td>1.25 V</td>
  </tr>
  <tr>
    <td>(Wp/Lp)</td>
    <td>4.(Wn/Ln)</td>
    <td>0.42</td>
    <td>0.27</td>
    <td>1.35 V</td>
  </tr>
  <tr>
    <td>(Wp/Lp)</td>
    <td>5.(Wn/Ln)</td>
    <td>0.42</td>
    <td>0.27</td>
    <td>1.4 V</td>
  </tr>
</table>
<br>Several conclusions can be drawn from the table above:
<li>When (Wp/Lp) equals twice (Wn/Ln), the Noise Margin High (NMh) increases because the PMOS transistor effectively holds the charge on the capacitance. Increasing the PMOS size creates a low-resistance path from the supply to the capacitance, allowing it to retain charge longer, thus enhancing NMh.</li>
<li>At (Wp/Lp) equal to four times (Wn/Ln), there is a decrease in Noise Margin Low (NMl) since the NMOS becomes weaker relative to the PMOS.</li>
<li>For (Wp/Lp) equal to five times (Wn/Ln), NMh stabilizes and reaches a near-constant value.</li>
<li>NMl remains largely unaffected, but NMh improves by approximately 120 mV, which remains within acceptable limits, demonstrating the CMOS inverter’s robustness in terms of noise margin.</li>

<br>Lastly, the figure below outlines the suitable regions for both digital and analog applications.
<br>![WhatsApp Image 2025-08-20 at 23 35 47](https://github.com/user-attachments/assets/098c3fce-1d71-4284-9c8c-ce707851a45a)

 <h4>Lab Activity</h4>
 <br>Following code is used:
 <br>*Model Description
.param temp=27

*Including sky130 library files
.lib "sky130_fd_pr/models/sky130.lib.spice" tt

*Netlist Description

XM1 out in vdd vdd sky130_fd_pr__pfet_01v8 w=1 l=0.15
XM2 out in 0 0 sky130_fd_pr__nfet_01v8 w=0.36 l=0.15

Cload out 0 50fF

Vdd vdd 0 1.8V
Vin in 0 1.8V

*simulation commands

.op

.dc Vin 0 1.8 0.01

.control
run
setplot dc1
display
.endc

.end
<br>![WhatsApp Image 2025-08-20 at 22 43 17](https://github.com/user-attachments/assets/a686d25d-d6cf-43c4-b34e-dd12a7e4da83)

<br>Method to calculate the Noise Margins from the plot:
<br>Run the ngspice command and open the plot
<br>left click on the point towards the top of the graph where the curvature seems to be '-1'
<br>In this case it was x0 = 0.775556, y0 = 1.70213
<br>Now, left click on the point towards the bottom of the graph where the curvature seems to be '-1'
<br>In this case it was x0 = 0.976667, y0 = 0.102128. Let's consider these points as x1 and y1 thus making the coordinates x1 = 0.977333, y1 = 0.110811
<br>For noise margin high we need Voh-Vih and in this case Voh=y0 and Vih=x1
<br>For noise margin low we need Vil-Vol and in this case Vil=x0 and Vol=y1
<br>Therefore, we get NMh = 0.725463 and NMl = 0.673428
<br>
<h2>CMOS power Supply and device variation robustness evaluation</h2>
<br>In 5th session, the impact of power supply variation on device gain and its pros and cons was studied. The influence of manufacturing variations such as etching and oxide thickness was also observed. Finally, the behavior of strong/weak PMOS and NMOS combinations was analyzed, highlighting transitions from Weak PMOS–Strong NMOS to Strong PMOS–Weak NMOS.
<br>
<h3>Part 1: Static behavior evaluation- CMOS inverter robustness- Power supply variation</h3>
<h4>What was learnt</h4>
<br>Power supply scaling : even we change supply CMOS behaviour should not be changing. 
<br>When CMOS technology scales from 250 nm to advanced nodes like 20 nm, the supply voltage (Vdd) is also reduced (e.g., from ~1 V down to ~0.7 V or lower) to limit power dissipation and reliability issues.  
<br>A CMOS inverter can even operate at 0.5 V :
<br>Advantages of 0.5 V Operation
<br>1.	Higher gain (≈50% improvement).
<br>2.	Much lower energy consumption (≈90% reduction).
<br>Disadvantages of 0.5 V Operation
<br>1.	Performance degradation: The lower supply causes weaker drive strength, making rising/falling edges slower.
<br>2.	Incomplete switching: At 0.5 V, the inverter may not fully charge or discharge the load capacitance, affecting logic reliability.
<br>
<h4>Lab Activity</h4>
<br>To perform the lab activity for power supply scaling, we need the following code:
<br>*Model Description
.param temp=27

*Including sky130 library files
.lib "sky130_fd_pr/models/sky130.lib.spice" tt

*Netlist Description

XM1 out in vdd vdd sky130_fd_pr__pfet_01v8 w=1 l=0.15
XM2 out in 0 0 sky130_fd_pr__nfet_01v8 w=0.36 l=0.15

Cload out 0 50fF

Vdd vdd 0 1.8V
Vin in 0 1.8V

.control

let powersupply = 1.8
alter Vdd = powersupply
        let voltagesupplyvariation = 0
        dowhile voltagesupplyvariation < 6
        dc Vin 0 1.8 0.01
        let powersupply = powersupply - 0.2
        alter Vdd = powersupply
        let voltagesupplyvariation = voltagesupplyvariation + 1
      end

plot dc1.out vs in dc2.out vs in dc3.out vs in dc4.out vs in dc5.out vs in dc6.out vs in xlabel "input voltage(V)" ylabel "output voltage(V)" title "Inveter dc characteristics as a function of supply voltage"

.endc

.end
<br>![WhatsApp Image 2025-08-20 at 23 04 15](https://github.com/user-attachments/assets/1e5871cc-6b37-4ba5-8af8-ccce022abba6)
<br>![WhatsApp Image 2025-08-20 at 23 04 15 (1)](https://github.com/user-attachments/assets/0409dd66-0419-4682-89e0-66ec7e0245a3)
<br>To calculate the gain for the given plot:
<br>Select the curve for which the gain is to be calculated (In this case, we chose the plot for 1.8V Vdd)
<br>Left click on the point where the slope of the curve is almost changing toward the top of the plot
<br>The point obtained was x0 = 0.777528, y0 = 1.70213
<br>Now, left click on the point where the slope of the curve is almost changing toward the bottom of the plot
<br>The point obtained was x0 = 0.983146, y0 = 0.102128 but for our convenience let us consider the coordinates of the point to be x1, y1
<br>Therefore, the point becomes x1 = 0.983146, y1 = 0.102128
<br>Subtract y1 from y0. So, y0 - y1 = 1.600002
<br>Subtract x1 from x0. So, x0 - x1 = -0.205618
<br>Now, gain = (y0-y1)/(x0-x1)
<br>Hence, Gain(g) = |(1.600002)/(-0.205618)| = |-7.78142| = 7.78142





<br><h3>Part 2: Static behavior evaluation- CMOS inverter robustness- Device variation</h3>
<br>Device variation arises from two main sources:

<br>Etching Process Variation
<br>Oxide Thickness
<br>![WhatsApp Image 2025-08-20 at 23 35 46](https://github.com/user-attachments/assets/68ecb1c2-7f35-452c-b269-6ea3f9b8121a)

**Etching Process Variation:**
<br>The etching process plays a crucial role in defining the physical structures within the CMOS inverter layout. It is a vital fabrication step that determines the width and height of the device features. These structural dimensions directly influence the inverter’s delay characteristics.

<br>In the CMOS inverter layout:
<br>The P-diffusion region is shown in green.
<br>The poly-silicon area is marked in red.
<br>The metal layers appear in blue.
<br>The N-diffusion region is highlighted in yellow.
<br>Contacts between layers are represented by black crosses.
<br>The poly-silicon layer thickness corresponds to the gate length, determining the technology node (e.g., 20nm, 30nm, 45nm). The thickness of the P-diffusion and N-diffusion layers correspond to the gate widths of the PMOS and NMOS transistors, respectively. The gate width is defined by the overlap area between the diffusion layer and the poly-silicon layer.

<br>The fabrication process involves numerous chemicals, water, and gases, which can cause deviations from the ideal device structures, leading to variations in the final device characteristics.
<br>
<br>**Oxide Thickness:**
<br>In an ideal oxidation process, the gate oxide thickness remains uniform, but in reality, it can vary along the gate length and between transistors in an inverter chain. This thickness affects the device current since the oxide capacitance (Cox) depends on it.
<br>Device Strength Variations:
<br>Strong PMOS: Low resistance due to larger transistor width.
<br>Weak PMOS: High resistance with smaller size.
<br>Strong NMOS: Low resistance from larger size.
<br>Weak NMOS: High resistance with smaller size.
<br>Switching threshold voltage varies between approximately 0.7V (Weak PMOS–Strong NMOS) and 1.4V (Strong PMOS–Weak NMOS), which is acceptable as inverter functionality is maintained.
<br>From SPICE simulations, we observe that:
<br>Noise Margin High (NMh) varies from about 2.5V to 2.1V, a 400mV range, sufficient to handle high-voltage noise.
<br>Noise Margin Low (NMl) changes from 0V to 0.3V, providing adequate low-voltage noise tolerance.
<br>Overall, the noise margin variations are small, ensuring stable gate operation.
<br>
 <h4>Lab Activity</h4>
 <br>for device variation, we need the following code:
 <br>*Model Description
.param temp=27

*Including sky130 library files
.lib "sky130_fd_pr/models/sky130.lib.spice" tt

*Netlist Description

XM1 out in vdd vdd sky130_fd_pr__pfet_01v8 w=7 l=0.15
XM2 out in 0 0 sky130_fd_pr__nfet_01v8 w=0.42 l=0.15

Cload out 0 50fF

Vdd vdd 0 1.8V
Vin in 0 1.8V

*simulation commands

.op

.dc Vin 0 1.8 0.01

.control
run
setplot dc1
display
.endc

.end
<br>![WhatsApp Image 2025-08-20 at 23 16 27](https://github.com/user-attachments/assets/fe7e2644-b7bd-4889-bfca-9d90d928a36c)

<br>![WhatsApp Image 2025-08-20 at 23 16 27 (1)](https://github.com/user-attachments/assets/3790bc5f-c573-43cf-93eb-e8a347153d99)

<br>![WhatsApp Image 2025-08-20 at 23 16 27 (2)](https://github.com/user-attachments/assets/a00e352a-f0bd-4505-b990-468e26124178)

<br>Since the pfet width is very huge as compared to the nfet width, the plot is shifted towards right
<br>**To find the value of the switching threshold:**
<br>Zoom in on the plot where Vin ~ Vout by right clicking and dragging the cursor to select the area
<br>Zoom until the value of switching threshold becomes almost certain
<br>Left click on the point where Vin is roughly equal to Vout
<br>A point x0 = 0.988568, y0 = 0.985 is obtained
<br>Since x0 ~ y0. Therefore, Switching Threshold Voltage = Vm = x0 = y0 = 0.988V
<br><h2>Conclusion</h2>
<br>Throughout the course, I gained a comprehensive understanding of MOSFETs and CMOS inverters. I learned various techniques to modify inverter characteristics and acquired practical skills in creating SPICE decks from netlists and running simulations. The study of voltage transfer characteristics and their influencing factors deepened my knowledge further. Additionally, exploring static behavior and its components was highly enlightening. The hands-on lab activities were particularly valuable, as analyzing simulation plots encouraged me to experiment with parameter adjustments. Overall, the workshop significantly enhanced my grasp of MOSFET fundamentals and sparked a keen interest in the subject. The continuous guidance provided by the VLSI System Design team made this experience highly rewarding.
<br><h2>References</h2>
<li>https://github.com/kunalg123/sky130CircuitDesignWorkshop</li>
<li>https://www.vlsisystemdesign.com/</li>
<li>https://github.com/kunalg123/vsdflow</li>



   
      
  <li>Drain-to-Source Voltage (Vds)</li>
  <li>Characteristic plots</li>
</ul>
