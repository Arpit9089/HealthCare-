import random
import pandas as pd
# Function to generate random patient profiles
def generate_patient_profiles(num_patients=10000):
    profiles = []
    for i in range(num_patients):
        name = f"Patient_{i+1}"
        age = random.randint(18, 80)
        gender = random.choice(['Male', 'Female'])
        bp = random.uniform(80, 120), random.uniform(50, 80)
        sugar_level = random.uniform(70, 140)
        cholesterol = random.uniform(125, 200)
        haemoglobin = random.uniform(12, 18)
        profiles.append({
            'Name': name,
            'Age': age,
            'Gender': gender,
            'BP': bp,
            'Sugar Level': sugar_level,
            'Cholesterol': cholesterol,
            'Haemoglobin': haemoglobin
        })
    return profiles
# Generate profiles
profiles = generate_patient_profiles()
# Convert to DataFrame
df = pd.DataFrame(profiles)
# Save to CSV
df.to_csv('patient_profiles.csv', index=False)
