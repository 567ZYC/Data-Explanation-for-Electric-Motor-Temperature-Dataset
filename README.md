# Data Explanation for Electric Motor Temperature Dataset
# Statement
This dataset builds upon the "Electric Motor Temperature" dataset. If your research benefits from this dataset, we kindly ask that you acknowledge the LEA Laboratory at Paderborn University, Germany. In addition, we encourage you to reference their research paper, titled "Estimating Electric Motor Temperatures Using Deep Residual Machine Learning Techniques".

# Introduction
The "Electric Motor Temperature" dataset provides valuable insights into the thermal behavior of a Permanent Magnet Synchronous Motor (PMSM). This dataset is particularly useful for researchers and engineers working on motor thermal management, predictive maintenance, and performance optimization. The data was collected from a physical test bench, ensuring its relevance to real-world applications.

# Data Collection and Sources
The dataset originates from experiments conducted at the LEA Laboratory at Paderborn University, Germany. The measurements were taken from a 52 kW three-phase automotive traction PMSM. The setup included:
Thermocouples embedded in various motor components (stator teeth, winding, yoke, and rotor permanent magnets)
A telemetry unit for rotor temperature data transmission
A dSPACE DS1006MC system and ADCs for synchronized data acquisition
Sampling at 2 Hz over 140 hours of operation
This comprehensive measurement approach captures the motor's thermal dynamics under different operating conditions.

# Data Composition
The dataset is organized in a tabular format with each row representing sensor measurements at a specific time point. The main variables include:

# Input Features:
Motor state variables: motor_speed (rotational speed), torque
Currents and voltages in the d/q coordinate system: i_d, i_q, u_d, u_q
Temperature variables: coolant temperature, stator winding temperature, stator tooth temperature, stator yoke temperature
# Target Variable:
pm: permanent magnet temperature (prediction target)
The dataset contains multiple experimental groups with varying temperature ranges and sample sizes. Groups 24 (Group A) and 46 (Group B) were specifically highlighted for further study due to their distinct temperature variation characteristics.

# Data Preprocessing
Different preprocessing methods were applied to Group A and Group B to prepare the data for modeling:
Group A (15,015 samples):
Every fifth sample was retained, resulting in 3,003 samples
500 samples randomly selected for training, remaining 2,503 for testing
This approach reduces data redundancy while preserving essential information for rotor temperature prediction
Group B (2,180 samples):
Every tenth sample was retained, resulting in 218 samples
1:1 split between training and test sets (109 each)
Tests the model's generalization ability with limited data
Preprocessing techniques like exponentially weighted moving averages (EWMA) and standard deviations (EWMS) were applied to enhance regression features and reduce high-frequency noise.

# Data Utilization
This dataset can be used to:
Develop and validate thermal models for PMSM
Create predictive maintenance systems for motor overheating
Optimize motor control strategies based on thermal behavior
Study the relationship between motor operating conditions and temperature changes
The dataset's focus on predicting permanent magnet temperature is particularly important, as this parameter is difficult to monitor in real applications but critical for motor performance and longevity.

# Considerations for Users
When working with this dataset, keep in mind:
The data represents a specific motor configuration and test bench conditions
The sampling rate and preprocessing methods were optimized for rotor temperature prediction
The dataset contains both extensive temperature variation (Group A) and limited high-temperature scenarios (Group B)
The preprocessing techniques may affect the detection of rapid temperature changes
Users should validate if the dataset's characteristics align with their specific application requirements before developing models.
