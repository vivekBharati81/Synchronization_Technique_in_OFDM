# Synchronization Techniques in OFDM
To implement synchronization in OFDM (Orthogonal Frequency Division Multiplexing), detecting the start of an OFDM frame accurately is crucial. The Schmidl and Cox algorithm is a widely used method for this purpose.
## Schmidl and Cox Algorithm
The Schmidl and Cox algorithm uses a preamble that contains two identical parts, which helps in the detection of the OFDM frame. Here's an overview of how the algorithm works:
**1) Preamble Structure:** The preamble is designed such that it has two identical parts. This repeated structure helps in identifying the start of the frame.
**2) Correlation Calculation:** The algorithm calculates a correlation metric using the received signal $r(n)$. The metric involves computing the following:

$$ P(d) = \sum_{m=0}^{L-1} (r[d+m] * r[d+m+L]) $$

where d is the time index, L is the length of one part of the preamble.
