# Schmidl and Cox Algorithm for OFDM Synchronization

## Overview

This project implements synchronization for Orthogonal Frequency Division Multiplexing (OFDM) using the Schmidl and Cox algorithm. To implement synchronization in OFDM, detecting the start of an OFDM frame accurately is crucial. The Schmidl and Cox algorithm is a widely used method for this purpose.

## Schmidl and Cox Algorithm

1) **Preamble Structure:** The preamble consists of two identical parts, facilitating the detection of the start of the frame.

2) **Correlation Calculation:** The algorithm calculates a correlation metric using the received signal $r(n)$. The metric involves computing the following:

      $$P(d) = \sum_{m=0}^{L-1} r^*(d+m) \cdot r(d+m+L)$$

3) **Energy Calculation:** The energy of the received signal over the interval is calculated as:

      $$R(d) = \sum_{m=0}^{L-1} \left| r(d+m+L) \right|^2$$

4) **Metric Calculation:** The correlation metric $M(d)$ is then given by:

      $$M(d) = \frac{\left| P(d) \right|^2}{\left( R(d) \right)^2}$$

      This metric exhibits a plateau around the position of the preamble.

## Implementation Steps

To implement the synchronization algorithm effectively, follow these steps:

1. **Metric Calculation**: Compute the metric \( M(d) \) as described above.
2. **Plateau Detection**: Detect the plateau in the metric \( M(d) \), indicating the start of the OFDM frame.
3. **Peak Detection**: Identify the exact peak within the plateau for precise FFT window positioning.
4. **FFT Window Positioning**: Position the FFT window correctly for proper demodulation of OFDM symbols.
5. **Preamble and Payload Extraction**: Extract preamble and payload data for further processing.

## Additional Logic for Robust Synchronization

Consider the following additional logic for robust synchronization:

- **Thresholding**: Use adaptive thresholding to improve plateau detection.
- **Window Averaging**: Smooth out the metric \( M(d) \) to reduce noise impact.
- **Guard Interval Consideration**: Account for guard interval to avoid inter-symbol interference.
- **Fine Synchronization**: Use pilot symbols for fine synchronization.

## Summary

The Schmidl and Cox algorithm is foundational for OFDM synchronization. By calculating a correlation metric and applying additional logic for plateau detection and FFT window positioning, accurate synchronization is achieved, facilitating effective OFDM demodulation and decoding.
