# U.S. Medical Insurance Costs
looking at how region can impact on Medical Costs.
does where you live impact your medical costs?



```python
import csv 
csv_file = open("insurance.csv", "r")
csv_data = list(csv.reader(csv_file, delimiter= ","))
csv_file.close()
#print(csv_data)
#data is held in csv_data

#new lists for data to be moved to
age = []
sex = []
bmi = []
children = []
smoker = []
region = []
insurance_cost = []

#create age list
def extract_age(csv_data):
    age = []
    for row in csv_data[1:]:
        age.append(int(row[0]))
    return age
age = extract_age(csv_data)

#create sex list
def extract_sex(csv_data):
    sex = []
    for row in csv_data[1:]:
        sex.append(row[1])
    return sex
sex = extract_sex(csv_data)

#create bmi list
def extract_bmi(csv_data):
    bmi = []
    for row in csv_data[1:]:
        bmi.append(float(row[2]))
    return bmi
bmi = extract_bmi(csv_data)

#create children list
def extract_children(csv_data):
    children = []
    for row in csv_data[1:]:
        children.append(int(row[3]))
    return children
children = extract_children(csv_data)

#create smoker list
def extract_smoker(csv_data):
    smoker = []
    for row in csv_data[1:]:
        smoker.append(row[4])
    return smoker
smoker = extract_smoker(csv_data)

#create region list
def extract_region(csv_data):
    region = []
    for row in csv_data[1:]:
        region.append(row[5])
    return region
region = extract_region(csv_data)

# create insurance cost list
def extract_cost(csv_data):
    insurance_cost = []
    for row in csv_data[1:]:
        value = float(row[6])
        insurance_cost.append(round(value, 2))
    return insurance_cost
insurance_cost = extract_cost(csv_data)

#create regional cost master list
regional_insurance_costs = list(zip(region, insurance_cost))


#create regional lists
northwest = []
northeast = []
southwest = []
southeast = []

#create northeast list
def extract_northeast(regional_insurance_costs):
    northeast = []
    for row in regional_insurance_costs:
        if row[0] == "northeast":
            northeast.append(row[1])
    return northeast
northeast = extract_northeast(regional_insurance_costs)

#create northwest list
def extract_northwest(regional_insurance_costs):
    northwest = []
    for row in regional_insurance_costs:
        if row[0] == "northwest":
            northwest.append(row[1])
    return northwest
northwest = extract_northwest(regional_insurance_costs)

#create southeast list
def extract_southeast(regional_insurance_costs):
    southeast = []
    for row in regional_insurance_costs:
        if row[0] == "southeast":
            southeast.append(row[1])
    return southeast
southeast = extract_southeast(regional_insurance_costs)

#create southwest list
def extract_southwest(regional_insurance_costs):
    southeast = []
    for row in regional_insurance_costs:
        if row[0] == "southwest":
            southwest.append(row[1])
    return southwest
southwest = extract_southwest(regional_insurance_costs)

#work out northeast average 
northeast_t = 0
for cost in northeast:
    northeast_t += cost
northeast_total = round(northeast_t, 2)
northeast_average = round(northeast_total / len(northeast), 2)
print("The average insurnace cost in the Northeast is $" + str(northeast_average) + ".")

#work out northwest average
northwest_t = 0
for cost in northwest:
    northwest_t += cost
northwest_total = round(northwest_t, 2)
northwest_average = round(northwest_total / len(northwest), 2)
print("The average insurance cost in the Northwest is $" + str(northwest_average) + ".")
        
#workout southeast average
southeast_t = 0
for cost in southeast:
    southeast_t += cost
southeast_total = round(southeast_t, 2)
southeast_average = round(southeast_total / len(southeast), 2)
print("The average insurance cost in the Southeast is $" + str(southeast_average) + ".")

#workout southwest average 
southwest_t = 0 
for cost in southwest:
    southwest_t += cost
southwest_total = round(southwest_t, 2)
southwest_average = round(southwest_total / len(southwest), 2)
print("The average insurance cost in the Southwest is $" + str(southwest_average) + ".")








    



    
    
    
```

    The average insurnace cost in the Northeast is $13406.38.
    The average insurance cost in the Northwest is $12417.58.
    The average insurance cost in the Southeast is $14735.41.
    The average insurance cost in the Southwest is $12346.94.



```python

```


```python

```
