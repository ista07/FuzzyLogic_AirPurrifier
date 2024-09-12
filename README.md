# Fuzzy Logic Air Purrifier
This project implements a fuzzy logic control system for an air purifier. The goal is to automatically adjust the fan speed of the air purifier based on three key environmental factors:
* Air Quality
* Humidity
* Temperature
By using fuzzy logic, the system provides a more flexible and human-like way of interpreting sensor data, as opposed to binary on/off control. The fan speed is dynamically adjusted to maintain optimal air conditions based on the input from these sensors.

## How Fuzzy Logic Works
In fuzzy logic, instead of crisp true/false values, we use degrees of truth represented by membership values. Each environmental factor (air quality, humidity, temperature) is divided into different fuzzy categories with corresponding membership functions. These membership functions assign a degree of membership (between 0 and 1) to each input value, based on its proximity to a category like "low," "medium," or "high."

The fan speed is adjusted based on the rules that combine these fuzzy input variables.

## Inputs and Membership Functions
1. Air Quality
* Good: Clean air, low pollution levels
* Moderate: Mild pollution
* Unhealthy: High pollution
* Very Unhealthy: Dangerous levels of pollution
* Hazardous: Extremely dangerous levels of pollution
These are modeled using trapezoidal membership functions (trapmf) to smoothly handle the transition between different pollution levels.

2. Humidity
* Too Dry: Air is excessively dry
* Ideal: Ideal humidity range
* Too Humid: Excessively humid
These are modeled using a mix of trapezoidal and triangular membership functions (trapmf, trimf).

3. Temperature
* Cold: Temperature is too low
* Cool: Slightly cool but tolerable
* Neutral: Ideal room temperature
* Warm: Warmer than neutral but still bearable
* Hot: Excessively hot
These categories use a mix of trapezoidal and triangular membership functions to model gradual changes in comfort levels.

## Output: Fan Speed
The output of the system is the fan speed, which is also divided into fuzzy categories:
* Low
* Medium
* High
The fan speed is determined based on the combination of air quality, humidity, and temperature inputs using a set of fuzzy rules. These rules define how each input combination affects the fan speed. For example, if the air quality is unhealthy, humidity is ideal, and temperature is neutral, the fan speed might be set to high to quickly clean the air.

## Example Rule:
IF air quality is unhealthy AND humidity is ideal AND temperature is neutral, THEN fan speed is high.
