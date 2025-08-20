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
  In this we learnt how SPICE can be used to simulate and analyze the device from its waveforms.Also, W/L ratio is a key parameter in defining the devices'S performace.Futhur,   we learnt about the structure of NMOS transistor.NMOS transistor consists of a p-type substrate and two 
      
  <li>Drain-to-Source Voltage (Vds)</li>
  <li>Characteristic plots</li>
</ul>
