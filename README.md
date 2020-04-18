# controlling-storage-group

Tantalus Hydro (TH) operates a pumped hydro storage facility.  When power costs are low water can be pumped up into a raised reservoir and when power costs are high the same water can be released to generate power. The total usable capacity of the reservoir is 10,000,000 litres.

There are only three states that the plant at Tantalus can be in: (a) pumping water up into the reservoir using power, (b) idle, (c) allowing water to flow out of the reservoir to generate power. When pumping water Tantalus requires 300 MW and during this phase a total of 14,000 litres per minute can be pumped. When water is flowing out of the dam 16,000 litres per minute will flow and this will generate 270 MW of power.

There is a loss of efficiency in storing power in this way (it costs more power to pump than Tantalus generates through letting water out, even though the flows are greater when Tantalus are generating). This will mean that it makes sense for there to be significant periods when the plant is idle.

The spreadsheet gives 8 weeks of price data (56 days, or 1344 hours). These are electricity prices in € per MWh  and are taken from the DK1 region in Nordpool for a period from January to March in 2019.

(A)

(30%) Suppose that a single daily schedule of operation will be determined that will be used throughout the eight-week period. It is desired to maximize average daily profit with the reservoir at a level of 5,000,000 litres at the beginning and end of every day (12 midnight). Formulate this as a linear program. Please carefully right down expressions (using Sigma notation) for the objective and each of the constraints, as well as specifying which variables are non-negative. You will need to define some notation for the price in hour t of day n.  Then solve the optimization problem. 

(Hint: you may wish to use, as variables for each of 24 hours, the proportion of the hour pumping, and the proportion of the hour generating, 48 numbers in total - since the proportion idle can then be deduced. You may also want to define a variable for the reservoir level at the end of hour t).

(B)

(60%) Now consider a more realistic scenario. Suppose that Tantalus Hydro needs to decide on what to do for the next hour (proportions of time pumping; or generating; or idle) on the basis of the current price and reservoir level. We consider a simple linear threshold policy of the following form: 

Calculate a number Z = αx + βy where x is the reservoir level at the end of hour t and y is the price in hour t. Here α and β are numbers to be chosen. 

The policy is to pump in the following hour (hour t+1) if Z ≤ C_A, generate in hour t+1 if Z ≥ D_A, and do nothing if Z is between these two values.
  
We allow α, β, C_A and D_A to depend on the time of day. The version of this policy that you should use has two different values for these parameters: one for the morning (first 12 hours before midday) and one for the afternoon/evening (second 12 hours, after midday). Because of the linearity we can normalise so that α=1 in both cases. For the first hour of the day please use a fixed policy based on your answer to Part (A), rather than looking at the last hour of the previous day.

In fact, the policy cannot be applied in exactly this manner – so your first task is to determine a version of this policy that will ensure that the reservoir level stays positive and below 10 Megalitres and returns to a 5 Megalitre level at the end of the day (12 midnight).  Please describe your modified policy carefully.

(Hint: You can achieve this by adding a restriction that the reservoir level (in 1000s of litres) at the  end of hour t lies in the region between the values  min⁡(10000,5000+(24-t)60×16) and max⁡(0,5000-(24-t)60×14). Then the policy is adjusted to ensure that it satisfies these constraints.)

Now find values for the parameters β, C_A, D_A with both am and pm values for each (so 6 parameters in total) that optimize the average profit made over the 56 days of data. Note that this is a nonlinear optimization problem. Because there are more than one local minima, depending on the optimization code you use, it may be helpful to try multiple starting positions.

(C)

(10%) Without carrying out any detailed calculations, propose any modifications to the form of policy in (B) that you think could be helpful (explaining your reasoning for any suggestions).
