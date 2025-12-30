Approximate Computing: 8×8 Approximate Multiplier Design in Cadence Virtuoso
Overview:

This project presents the design and implementation of an 8×8 approximate multiplier using approximate computing techniques to achieve improved power, delay, and area efficiency at the cost of controlled computational accuracy. The complete design is implemented and verified at the schematic level in Cadence Virtuoso.
The work focuses on carry-disregard and compressor-based approximation, which is well suited for error-tolerant applications such as image processing, signal processing, and machine learning.

Motivation:

Exact multipliers are one of the most power and delay intensive blocks in digital systems. 
Many modern applications can tolerate small numerical errors, allowing a trade-off between accuracy and hardware efficiency. 
Approximate computing exploits this tolerance to reduce logic complexity, switching activity, and carry propagation delay.

Architecture and Design Methodology

a. Approximate 4×4 Multiplier Block

The fundamental building block of the design is an approximate 4×4 multiplier.
Partial-product reduction is performed using modified 4:2 compressors instead of exact compressors.
To reduce complexity:
XOR gates and the Cout path are ignored, as they contribute significantly to power and delay.
Generate (G) and Propagate (P) signals are used to encode partial products, reducing the probability of erroneous outputs.
Compressor logic is simplified across multiple reduction stages while maintaining acceptable accuracy.

b. 8×8 Multiplier Construction

The 8-bit operands are divided into two 4-bit halves:
A = {AH, AL}, B = {BH, BL}
Four 4×4 multipliers are used to generate partial products:
P₁ = AH × BH (most significant)
P₂ = AL × BH
P₃ = AH × BL
P₄ = AL × BL (least significant)
A carry-disregard strategy is applied to lower-significance partial products to reduce carry propagation delay.

c. Circuit Implementation

All building blocks were implemented at the transistor and schematic level, including:
Basic logic gates (AND, OR, XOR, NAND, NOR)
Half adders and full adders

Approximate compressors:
Carry Lookahead Adder (CLA)
Transistor sizing was optimized to balance speed and power consumption.

Verification and Results:

Functional verification was performed using Cadence Virtuoso simulations.
The multiplier was tested with multiple input combinations to observe:
Correct functionality
Approximation-induced error behavior
Performance improvement compared to exact multipliers
Results demonstrate a significant reduction in carry delay and logic complexity with acceptable accuracy degradation.

Tools and Technologies:

Cadence Virtuoso – Schematic design and simulation
CMOS logic design
Approximate computing techniques
Carry Lookahead Adders (CLA)
Compressor-based multiplier architectures

Key Learning Outcomes

Understanding of approximate arithmetic architectures

Practical experience in compressor-based multiplier design

Trade-off analysis between accuracy, power, delay, and area

Hands-on experience with Cadence Virtuoso and transistor-level digital design

Applications

Image and video processing

Signal processing

Error-tolerant machine learning hardware

Low-power embedded and VLSI systems

References

Mohammad Saeed Ansari et al.,
Low-Power Approximate Multipliers Using Encoded Partial Products and Approximate Compressors,
IEEE Journal on Emerging and Selected Topics in Circuits and Systems.
