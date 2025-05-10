# Weekly activities:

## ECSE 395 
## 03/31/25

Robert found a new design that we think will be better for the cat bowls. They just slide into a plastic tray that is raised on two legs, sort of like a horizontal table. 
We realized that 4 AA batteries in parallel was too low of a voltage for the 7805 voltage regulator. It needs at least two volts above 5v to output without voltage drop. We are looking at 7805 regulator, built-in regulator, and TPS783xx regulator. We also need to make sure to disable the excess arduino parts that we aren't using to maximize battery life. It's not safe to discharge a lithium polymer battery pack below 3.0 volts so we can't use that. Li-ion is safer in this regard but bulkier. 

We learned later that it is not recommended to use alkaline batteries at the barrel jack input because it may damage the arduino. So we are going with the buck DC-DC converter with 5 AA batteries. 
	![](Pasted%20image%2020250331114339.png)