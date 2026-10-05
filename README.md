# Smart Energy Stream Analytics

A Big Data Analytics mini-project that analyzes a real-world smart-meter electricity dataset using **Bloom Filter** and **Flajolet–Martin** algorithms for memory-efficient stream processing.

## Project Title

**Smart Energy Stream Analytics: Memory-Efficient Pattern Detection and Distinct State Estimation Using Bloom Filter and Flajolet–Martin Algorithm**

## Overview

Modern smart meters generate large volumes of electricity-consumption readings continuously. Storing and processing every unique state exactly can become expensive as the data grows.

This project demonstrates how probabilistic data-stream algorithms can be used to process large-scale energy data efficiently.

The project uses:

- **Bloom Filter** to check whether an energy state has probably appeared before.
- **Flajolet–Martin Algorithm** to estimate the number of distinct energy states.
- **Exact Python calculations** to compare and evaluate the approximate algorithms.
- **Data visualization** to study power-consumption patterns and algorithm performance.

## BDA Concepts Covered

This project is primarily based on **Module 4: Mining Data Streams** from the Big Data Analytics syllabus.

It demonstrates:

- Stream Data Model
- Filtering Streams
- Bloom Filter
- Count-Distinct Problem
- Flajolet–Martin Algorithm
- Approximate Analytics
- Memory vs Accuracy Trade-off
- Stream Window Analysis

## Dataset

**Dataset:** Individual Household Electric Power Consumption  
**Source:** UCI Machine Learning Repository

The dataset contains more than **2 million real household electricity readings** recorded at approximately one-minute intervals.

Important attributes include:

- Date
- Time
- Global Active Power
- Global Reactive Power
- Voltage
- Global Intensity
- Sub Metering 1
- Sub Metering 2
- Sub Metering 3

## Project Workflow

```text
Real UCI Smart-Meter Dataset
            |
            v
   Data Cleaning & Preprocessing
            |
            v
   Chronological Energy Stream
            |
      +-----+------+
      |            |
      v            v
 Bloom Filter   Flajolet-Martin
      |            |
      v            v
Membership      Approximate
 Testing       Distinct Count
      |            |
      +-----+------+
            |
            v
   Exact vs Approximate
        Comparison
            |
            v
 Time, Memory & Error Analysis
            |
            v
 Energy Consumption Insights
```

## Energy State Creation

Raw measurements such as power and voltage are converted into discrete energy states.

Example:

```text
Global Active Power = 4.216 kW
Voltage = 234.84 V

After rounding:

Power State = 4.2
Voltage State = 235

Energy State = 4.2_235
```

These energy states are treated as elements of the incoming stream.

## Bloom Filter

A Bloom Filter is a memory-efficient probabilistic data structure used for membership testing.

In this project it answers:

> Has this energy state probably appeared before?

The Bloom Filter may produce **false positives**, but a standard Bloom Filter does not produce false negatives.

The project studies:

- Bloom Filter size
- Number of hash functions
- False-positive rate
- Memory usage
- Performance on large streams

## Flajolet–Martin Algorithm

The Flajolet–Martin algorithm estimates the number of distinct elements in a data stream using hashing.

In this project it answers:

> Approximately how many unique energy states have appeared?

The estimated count is compared with the exact distinct count to calculate estimation error.

The project studies:

- Actual distinct count
- Estimated distinct count
- Percentage error
- Effect of stream size
- Approximate counting efficiency

## Additional Analytics

The project also performs basic smart-energy analysis such as:

- Hourly electricity-consumption trends
- High-consumption event analysis
- Stream-window analysis
- Energy-state frequency analysis
- Exact vs approximate performance comparison

## Technologies Used

- Python
- Google Colab
- Pandas
- NumPy
- Matplotlib
- hashlib
- UCI Machine Learning Repository

## Project Structure

```text
Smart-Energy-Stream-Analytics/
|
|-- Smart_Energy_Stream_Analytics.ipynb
|-- README.md
|-- Mini_Project_Report.pdf
|-- images/
|   |-- architecture.png
|   |-- bloom_flow.png
|   |-- fm_flow.png
|
`-- results/
    |-- bloom_filter_analysis.png
    |-- fm_estimation.png
    `-- energy_consumption_analysis.png
```

## How to Run

1. Open the notebook in **Google Colab**.
2. Run the library-import cells.
3. Download or upload the UCI household power-consumption dataset.
4. Execute the preprocessing cells.
5. Create the energy-state stream.
6. Run the Bloom Filter implementation.
7. Run the Flajolet–Martin implementation.
8. Execute the performance-analysis cells.
9. Generate and observe the result graphs.

## Key Outputs

The notebook generates results for:

- Bloom Filter false-positive rate
- Bloom Filter memory usage
- Exact vs approximate distinct counts
- Flajolet–Martin estimation error
- Performance across different stream sizes
- Hourly electricity-consumption patterns
- High-energy consumption periods
- Window-based stream analysis

## What Big Data Analytics Is Achieved?

The main objective is not simply to analyze a large CSV file.

The project demonstrates how large and continuously arriving data can be analyzed using **approximate, memory-efficient streaming algorithms**.

Instead of storing every unique value:

- Bloom Filter uses a compact bit structure for membership testing.
- Flajolet–Martin uses compact estimator state for approximate distinct counting.

This demonstrates an important Big Data principle:

> A small loss in exactness can sometimes provide major savings in memory and scalability when processing very large data streams.

## Advantages

- Uses a real-world dataset with more than 2 million records.
- Directly implements concepts from the BDA syllabus.
- Requires no Spark or Hadoop setup.
- Runs completely on Google Colab.
- Demonstrates both theoretical and practical BDA concepts.
- Includes accuracy, memory, and performance evaluation.
- Easy to reproduce and explain during viva.

## Limitations

- The project simulates streaming from a stored historical dataset rather than consuming live smart-meter data.
- Bloom Filter can produce false positives.
- Flajolet–Martin gives an approximate rather than exact distinct count.
- Results depend on parameter selection such as filter size and number of hash functions.

## Future Scope

The project can be extended using:

- Live IoT smart-meter feeds
- Sliding and decaying stream windows
- HyperLogLog for improved distinct counting
- Apache Kafka for real-time event ingestion
- Distributed stream-processing frameworks
- Real-time anomaly detection
- Energy-demand forecasting
- Interactive dashboards

## Conclusion

This project demonstrates how probabilistic algorithms can efficiently analyze large energy-data streams.

Bloom Filter provides memory-efficient membership testing, while the Flajolet–Martin algorithm estimates distinct energy states without storing every unique element.

By comparing approximate results with exact computation, the project highlights the important trade-off between **memory efficiency, scalability, and accuracy** in Big Data Analytics.


## References

- UCI Machine Learning Repository — Individual Household Electric Power Consumption Dataset
- Big Data Analytics course syllabus
- Bloom Filter literature
- Flajolet–Martin probabilistic counting algorithm
