Master Class: Now You See, and Now You Don't

---
# Overview
![[Pasted image 20220210144156.png]]

---
# 1. The Swap
![[Pasted image 20220210144325.png]]
![[Pasted image 20220210144644.png]]

## 1.1 Dimension/Measure
### 1.1.1 Dynamic Dimension
```ad-note
TItle: Summary
- **Step 1**: Create a parameter with the names (string) of the dimension to be made available to the users
- **Step 2**: Create a Calculated Field with Logic to selected the Dimension according to the value selected in the parameter
```
![[Pasted image 20220210151234.png]]
![[Pasted image 20220210151731.png]]

### 1.1.2 Dynamic Measure
> Which use very similar 2-step approach as above. 

![[Pasted image 20220210152957.png]]

### 1.1.3 Custom List
![[Pasted image 20220210154056.png]]
![[Pasted image 20220210154403.png]]
![[Pasted image 20220210154748.png]]

---
## 1.2 Swapping at Worksheet Level
![[Pasted image 20220210155152.png]]

> Steps:
> 1. Create a Dashboard with Vertically aligned Charts
> 2. Create parameter for selecting the name of the sheets
> 3. Create calculated field 
> 4. Drop those charts into the Dashboard
> 5. ⚠️ Do note once placed into the Dashboard, should NOT manually adjust the size of the chart in dashboard, otherwise the charts will not automatically expand when not visible

![[Pasted image 20220210161813.png]]

> Screenshot show invisible chart after setting the filter to False
![[Pasted image 20220210162018.png]]
![[Pasted image 20220210162105.png]]

## 1.3 Show/Hide
> Overlay the charts
> Add Show/Hide button


---
# 2. The Unfold (Using Set)
![[Pasted image 20220210164528.png]]

![[Pasted image 20220210164849.png]]
![[Pasted image 20220210165014.png]]
![[Pasted image 20220210165452.png]]
![[Pasted image 20220210165838.png]]
![[Pasted image 20220210170025.png]]

![[Pasted image 20220210170145.png]]


> From here onwards, expand to 3-level (region)

![[Pasted image 20220210170644.png]]


---
## 2. 1With Collapsable 
![[Pasted image 20220210170943.png]]

Demo the Logic: Create a calculated field (dimension) to calculate distinct (Sub-category)
Logic: if collapse become 
![[Pasted image 20220210171204.png]]
Actual calculated Field
![[Pasted image 20220210171421.png]]

![[Pasted image 20220210171658.png]]

THEN Uncheck "Show Header for the actual "Category" and "Sub Category", left with the two calculated fields above

---
## 2.2 Expanding Details - See Details among Aggregation
![[Pasted image 20220210172751.png]]
![[Pasted image 20220210172845.png]]
Add the "Expand" as row's values, set to dual-axis
![[Pasted image 20220210172931.png]]
![[Pasted image 20220210173034.png]]
![[Pasted image 20220210173218.png]]

> Extra Steps for Refining:
> - To sync the axis
> - Use reference lines to set the Min and Max to fix the scale of the y-axis

![[Pasted image 20220210173639.png]]


# Summary Note
![[Pasted image 20220210173753.png]]