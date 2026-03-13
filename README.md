# Survival Modeling for NFL RBs

### Objective
The primary goal of this project is to move beyond traditional age-based scouting and establish a rigid, mathematical threshold for a Running Back's "expected performance life". By treating player health like a risk asset, this model provides front offices with a quantitative tool to predict performance collapse and optimize contract negotiations.

### The Problem
Running Backs are the most rapidly depreciating assets in professional sports. NFL front offices frequently fall into the "sunk trap cost", signing veteran workhorses to second contracts based on past production rather than future durability. Without a mathematical "cutoff" for workload, teams consistently overpay for players on the verge of a statistical cliff, leading to significant salary cap inefficiencies and roster stagnation.

### Methodology
This project applies Acturarial mortality modeling—the same math used by insurance companies to price life insurance to NFL workload data.

* Data Source: Two decades of NFL play-by-play and seasonal data (via `nflfastR`).
* Time vs. Event: Cumulative career touches (carries + receptions) were used as the measure of "time," while a "failure event" was defined as a 20% drop in efficiency or a season-ending injury.
* Statistical Models: Kaplan-Meier Survival Curves: Used to calculate the probability of maintaining efficiency at every workload interval.
    * Nelson-Aalen Hazard Estimation: Employed to prove that player risk is not linear, but follows an accelerating "J-Curve."



### Key Findings
* The Touch Threshold: The actuarial median survival point for an NFL running back is 576 cumulative career touches. At this specific mark, 50% of the population experiences a performance "death" event.
* Exponential Decay: Risk does not increase steadily; it spikes. The Hazard Rate remains manageable until approximately 450 touches, after which the probability of a performance cliff increases exponentially.
* Front Office Application: GMs can use the touch mark as a hard boundary for extensions. The data suggests that trading a player "a year too early" is mathematically superior to being stuck with a non-performing asset "a year too late."
