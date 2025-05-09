# Healthstat: a Healthcare-Project
Our Dataset is about a fictitious consulting company called HealthStat that hired us to uncover insights on potential hospital efficiency opportunities. The focus is on patients who received hip replacement surgery. Deliverable of this case will be to create dashboards enabling the stakeholders of analyzing the needed data and gaining insights.

Project goals
Track the cost per dicharge of each facility and relate it to its root causes.
Analyze the length of stay of the patients.
Detailed Hospitals profile created with ability to comparison.

____

Data Sourcing:
For this case study, we will be working with a dataset that includes New York state-wide hospital discharge data for a year. Elective hip replacement surgery was the main reason for their hospital stay.

The dataset is one single table with 30 columns Each row in the dataset represents a single inpatient stay, from their admission to discharge date. The health information in this dataset is not individually identifiable. This means the file does not contain personal health information.

The dataset has some key attributes to analyze efficiency: Length of stay measured in total days and Total costs attributed to each hospital stay.

Here's a list of some of the key columns of interest for the case study:

facility_id,
age_group,
patient disposition,
diagnosis description,
severity of illness, and risk of mortality
will be closely evaluated  understand the factors that impact the length of stay and related costs.

____
Dax Measures


-Total Hospitals = 
    DISTINCTCOUNT(
        Hospital_discharges[facility_id]
        )
-Total Surgeons = 
DISTINCTCOUNT(
    Hospital_discharges[operating_provider_license_number]
)

-Total Discharges = 
    COUNTROWS(
        Hospital_discharges
    )
-Average LOS Days All = 
CALCULATE([Average LOS Days],ALL()
)
-Average Cost per Discharge All = 
CALCULATE(
    [Average Cost Per Discahrge],ALL()
    )
-Average LOS Days = 
    AVERAGE(
        Hospital_discharges[length_of_stay]
    )

-Average Cost Per Discahrge = 
DIVIDE(
    SUM(Hospital_discharges[total_charges]),
    [Total Discharges]
    )

-%Var Cost For Discharge = 
DIVIDE(
[Average Cost Per Discahrge]- [Average Cost per Discharge All],
[Average Cost per Discharge All]
)
-%Var Average LOS Days = 
DIVIDE(
    [Average LOS Days]-[Average LOS Days All],
    [Average LOS Days All]
)

![1](https://github.com/user-attachments/assets/3974ab33-5be6-4bae-bcd6-300385724991)

![2](https://github.com/user-attachments/assets/e583ed24-8767-4e7a-90ba-774a23607af2)
Understanding Demographic Patterns: By examining demographic patterns, a noticable  portion of elective hip replacement patients belonged to the 60-75 age group, providing valuable insights for targeted healthcare programs and resource allocation.

![3](https://github.com/user-attachments/assets/fa9da38a-71e2-4d74-8c4d-64b1a9411091)
 The analysis of costs revealed a notable variation in average total costs across hospitals. By understanding these cost differences, hospitals can implement cost-effective measures and potentially reduce healthcare expenses.

![4](https://github.com/user-attachments/assets/d1a95f1c-adfa-4968-93d4-0bd004d63d09)
Analyzing Hospitals' Profiles revealed variations in outcomes and costs. This information can guide each  facility in optimizing their provider selections.

full project navigation:
[Healthstat Healthcare Project.pdf](https://github.com/user-attachments/files/20129386/Healthstat.Healthcare.Project.pdf)


