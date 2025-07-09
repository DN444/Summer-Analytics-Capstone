# Summer-Analytics-Capstone
Urban parking spaces are a limited and highly demanded resource. Prices that remain static
throughout the day can lead to inefficiencies — either overcrowding or underutilization.
To improve utilization, dynamic pricing based on demand, competition, and real-time
conditions is crucial.
This project simulates such a system: participants will create an intelligent, data-driven
pricing engine for 14 parking spaces using real-time data streams, basic economic theory,
and ML models built from scratch, using only numpy, pandas libraries.
Location Information:

• Latitude and Longitude of each parking space (to calculate proximity to competitors).

Parking Lot Features:

• Capacity (maximum number of vehicles that can be parked)

• Occupancy (current number of parked vehicles)

• Queue length (vehicles waiting for entry)


Vehicle Information:

• Type of incoming vehicle: car, bike, or truck

Environmental Conditions:

• Nearby traffic congestion level

• Special day indicator (e.g., holidays, events)

Each time step reflects the state of each parking lot, and demand will fluctuate throughout
the day based on these features.

Model 1: Baseline Linear Model
A simple model where the next price is a function of the previous price and current
occupancy:
• Linear price increase as occupancy increases
• Acts as a reference point

Price(t+1) = Price(t) + α(Occupancy/Capacity)
Model 2: Demand-Based Price Function
Demand function:
Demand = α(Occupancy/Capacity)+β·QueueLength−γ·Traffic+δ·IsSpecialDay+ε·VehicleTypeWeight
Price(t) = BasePrice · (1 + λ · NormalizedDemand)
