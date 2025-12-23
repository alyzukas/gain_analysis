# Gain Per Flight Analysis
- **Author:** Group Project 
- **Date:** December 1, 2025

-------

## Project Overview

**Introduction:** This repository contains an R analysis of NYC flight departure delays for United Airlines in 2013,
executed in Google Colab using the `nycflights13` dataset.

**Problem Statement:** <br>
A major player in the aviation industry, United Airlines, wants to better understand how
operational factors affect schedule recovery during flight. Specifically, United Airlines are
interested in answering the following questions:
1. Does departing late impact a flight’s ability to make up time while airborne?
2. Which top five (5) destination airports show the largest or smallest time recoveries?
3. Do longer flights gain more time, especially when accounting for flight duration?
4. At what level of departure delay – like exceeding 30 m

### Main Source of Analysis
- `gain_per_flight_analysis.ipynb` – main Colab notebook


### How to open
1. Click the **Open in Colab** badge below, or  
2. Download the `.ipynb` and open in Colab manually.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1Wdd3cP-pHobzpsajhRchFd7yzk6Jw3q0)

Please view the official **Google Powerpoint** presentation [here](https://docs.google.com/presentation/d/1Do5by0lCA2sLWvQLXe2H-ksfYlGbO42FtPqSB27LKEE/edit0). 

---

## Project Structure

```
├── 'gain_per_flight_analysis.ipynb'          # Google Colab Notebook and R script
├── 'gain_analysis_report                     # Generated reports and visualizations
├── 'gain_analysis_presentation               # Presentation slides for communicating results
└── README.md                                 # Project documentation
```

---

## Data 

## Sources:

This project utilizes 2 main data sets from the **‘nycflights13’ R Package**:

- **Airports**: Contains details about each airport, like the faa code, name, altitude, latitude/longitude, altitude(ft), timezone, and daylight-saving indicators .
- **Flights**: Contains details about the United Airlines flights in and out of NYC for the year of 2013, such as the airline and carrier names, airport information, plane identification codes, and weather origin.   

---

## Analysis

Google Colab Notebook

---

## Statisitcal Methods 
To better understand the patterns in flight delays and time recovery, we used simple visual
tools such as bar charts and boxplots. These helped us see how often certain destinations
were flown to and how much time flights gained or lost in the air. We also looked at basic
summaries of the data, like average times gained and how much those times varied from
flight to flight.
To compare different groups of flights—such as those that departed late versus on time—
we used a standard statistical method that tests whether the differences we see are likely
real or just due to chance. We looked for results that were statistically significant, which
means there is strong evidence that the difference is meaningful. In this report, we
consider a result significant if there is less than a 5% chance that it happened randomly.

---

## Results
### Finding 1: Late departures recover less time than on-time departures

Our analysis reveals that flights departing late gain 1.4-2.0 fewer minutes in the air
compared to on-time flights. While this difference is statistically significant, the practical
implications warrant careful consideration. For a typical 3-hour flight, this translates to
only about 1% less recovery efficiency—a modest but consistent pattern across
thousands of flights.

Why this matters for United Airlines: This finding challenges the assumption that pilots
can simply "make up time" after ground delays. United should consider:

- Schedule padding: Building in appropriate buffer time on routes with frequent
delays, particularly to/from congested airports.
- Crew training: Understanding whether this limitation is due to air traffic control
constraints, fuel optimization protocols, or other operational factors.
- Passenger communication: Setting realistic arrival expectations when departures
are delayed.

Potential explanations: Late departures may have less flexibility to recover time due to:
- Congested air traffic patterns during peak delay periods
- Fuel conservation protocols that limit speed increases
- Cascading delays that affect optimal routing
- Crew duty time limitations that prevent extended flight times
  
### Finding 2: The 30-minute threshold (very late flights) shows compounding effects

Flights delayed more than 30 minutes show even less recovery (1.3-2.2 fewer minutes),
suggesting that severe delays may trigger operational constraints that further limit time
recovery.

Operational insight: The 30-minute mark appears to be a critical threshold where United's
ability to mitigate delays deteriorates. This could inform:
- Proactive intervention protocols: Implementing special procedures when delays
approach 30 minutes
- Resource allocation: Prioritizing recovery efforts before this threshold is reached
- Cancellation decisions: Better cost-benefit analysis of when to cancel versus
delay

### Finding 3: Short flights show superior recovery efficiency

Our most striking finding is that short flights gain approximately 4 more minutes per hour
than long flights (5.59 vs 1.64 minutes per hour). This 3-4x difference has significant
operational implications.

Why short flights may recover better:
- More flexibility in cruise altitude adjustments
- Less complex routing with fewer waypoints
- Typically fly in less congested airspace
  
Strategic recommendations:
- Route-specific strategies: United should develop different recovery protocols for
short-haul vs long-haul flights
- Schedule design: Short-haul routes may need less buffer time since they have
greater recovery potential
- Hub operations: Since many short flights connect to long-haul flights,
understanding this recovery differential is critical for minimizing missed
connections

---

## Authors 

- Alyssa Zukas - [@alyzukas](https://github.com/alyzukas)
- Prince Newman
- Badamgarav Battushig
- Edwin Okwor

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Acknowledgements 

- Tools/libraries used:
    - Ggplot2: Imported for data visualization 
    - Dplyr: Used for data manipulation in R. Such as the filter, select, muttate, arrange, and summarize functions 
    - Tidyr: Used for tidying and reshaping data 
