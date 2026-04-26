# event-intensity-sleep-recovery-analysis
This project explores how high-stimulation environments (e.g., concerts, festivals, nightlife events) impact next-day sleep quality and recovery duration.

Using a self-collected dataset combined with wearable sleep metrics, I analyzed how event intensity influences:

Next-day sleep score changes
Recovery time (days to return to baseline)
Variation across event types and environments

The goal was to treat personal behavioral data with the same rigor as a real-world analytics problem.

Key Questions
Do higher-intensity events lead to larger next-day sleep disruptions?
How long does it take to recover from different types of events?
Are certain event categories (e.g., bass-heavy shows vs. lower-intensity environments) consistently associated with worse outcomes?
Dataset

The dataset includes event-level and physiological metrics:

Event Variables

Event Name
Date
Event Type (festival, venue, etc.)
Genre
Crowd Size / Density
Social Context (solo vs. group)

Behavioral / Environmental Inputs

Intensity Score (self-reported composite)
sensory stimulation
duration
overall exertion
substance use (if applicable)

Physiological Outcomes

Sleep Score (wearable device)
Sleep Score +1 (next-day effect)
Days to Recover Sleep Baseline
HRV metrics (tracked but not primary focus here)
Methodology
1. Event Alignment

Each event date was aligned with:

Same-day baseline sleep
Next-day sleep outcome (+1 lag)
2. Baseline Comparison

For each event:

Calculated deviation from baseline sleep score
Measured sleep drop magnitude
3. Recovery Metric

Defined recovery as:

Number of days until sleep score returned to baseline range
4. Intensity Modeling

Used a self-reported composite intensity score to approximate total physiological load from:

environment
duration
exertion
substance exposure
Key Findings
1. High-Intensity Events Drive Larger Sleep Disruptions
High-intensity bass events (e.g., Get Lucky, Mersiv)
Produced the largest next-day drops:
→ ~40–60 point decreases in sleep score
2. Recovery is Multi-Day, Not Immediate
High-intensity events required:
→ 2–3 days to return to baseline
Lower-intensity or sober events:
→ Minimal disruption and near-immediate recovery
3. Intensity is a Stronger Signal Than Event Type Alone
Not all events produce disruption
Intensity level explains variance better than category labels
Visualization

The Tableau dashboard highlights:

Time series of sleep scores
Overlaid with event markers
Sleep drop vs. recovery duration
Compared across events
Intensity gradient encoding
Used to visually connect stimulus → outcome

Tools Used
Python / Pandas → data cleaning & transformation
Tableau → visualization & dashboard design
Wearable data integration → sleep metrics
Why This Project Matters

This project demonstrates:

Translating real-world behavior into structured data
Designing lag-based outcome analysis
Building interpretable, narrative-driven dashboards

While the dataset is personal, the analytical approach mirrors:

health analytics
behavioral science
user outcome modeling
Future Improvements
Expand sample size across more events
Incorporate HRV as a primary outcome variable
Apply statistical modeling (regression / mixed effects)
Compare against control (non-event baseline periods)
