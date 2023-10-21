# Data Analysis Project - Excel 1

There are 5 Excel files that contain the raw data.
The Export Billing Data Analysis.xlsx file contains the data cleaning and analysis in order to find the difference between Expected Charges and Billed Charges.
<br>
<p>
<br>
Your client has a large e-commerce company in India (let’s call it X).
X gets a thousand orders via their website on a daily basis and they have to deliver them as fast
as they can. For delivering the goods ordered by the customers, X has tied up with multiple
courier companies in India as delivery partners who charge them some amount per delivery.
The charges are dependent upon two factors:
● Weight of the product and the Price of the product.
● Distance between the warehouse (pickup location) and the customer’s delivery address
(destination location)
On average, the delivery charges are Rs. 100 per shipment. So if X ships 1,00,000 orders
per month, they have to pay approximately Rs. 1 crore to the courier companies on a monthly
basis as charges.
As the amount that X has to pay to the courier companies is very high, they want to verify if the
charges levied by their Delivery partners per Order are correct.
Input Data
Left Hand Side (LHS) Data (X’s internal data spread across three reports)
● Website order report- which will list Order IDs, various products (SKUs) part of each
order and the Payment Type of the Order ( COD or Prepaid). Order ID is common
identifier between X’s order report and the courier company invoice
● Warehouse pincode to All India pincode mapping -(this should be used to figure out
delivery zone (a/b/c/d/e) and during analysis compare against one reported by the courier
company in their CSV invoice per Order ID
● SKU master with gross weight of each product. This should be used to calculate the total
weight of each order and during analysis compare against one reported by the courier
company in their CSV invoice per Order ID. The courier company calculates the weight in
slabs that are applicable to that delivery zone, so first you have to figure out the total
weight of the shipment and then figure out the applicable weight (based on the zone’s weight
slab).
<br>
<br>
For example:
Total Weight Applicable Zone Applicable Weight
Slab (based on zone)
Applicable Weight
400gm a 0.25 0.5
400gm b 0.5 0.5
400gm c 0.75 0.75
2.2KG a 0.25 2.25
2.2KG b 0.5 2.5
2.2KG c 0.75 2.25
RHS Data (courier company invoice in CSV file)
● Invoice in CSV file mentioning AWB Number (courier company’s own internal ID), Order
ID (company X’s order ID), weight of shipment, warehouse pickup pincode, customer
delivery pincode, zone of delivery, charges per shipment, type of shipment
● Courier charges rate card at weight slab and pincode level. If the invoice mentions
“Forward charges” then only forward charges (“fwd”) should be applicable as per zone
and fixed & additional weights based on weight slabs. If the invoice mentions “Forward
and rto charges” then forward charges (“fwd”) and RTO charges (“rto”) should be
applicable as per the zone and fixed & additional weights based on weight slabs.
● For the first slab of that zone, “fixed” rate as per the slab is applicable. For each
additional slab, “additional” weight in the same proportion is applicable. Total charges will
be “fixed” + “total additional” if any. For example: weight 2.2KG, Zone C. So for Zone C
the slab length = 0.75KG. So the total applicable weight = 2.25KG. For the first 0.75KG
the charge is “fwd”, and for each 0.75 after the first, charges will be additional charges.
● Once this is done, then you need to calculate the COD charges. For this case, if the
order is Prepaid then COD charge is 0 and if the order is COD then we need to check
the amount of the order
If the order amount is less than equal to 300 then the COD charge is 15
Else the COD charge is 5% of the Order Amount
● Total Charges = Total forward charge + Total RTO charge + COD charge.
<br>
<br>
<h3>Output</h3>
<br>
Create a resultant CSV / Excel file with the following columns:
<ol>● Order ID</ol>
<ol>● AWB Number</ol>
<ol>● Total weight as per X (KG)</ol>
<ol>● Weight slab as per X (KG)</ol>
<ol>● Total weight as per Courier Company (KG)</ol>
<ol>● Weight slab charged by Courier Company (KG)</ol>
<ol>● Delivery Zone as per X</ol>
<ol>● Delivery Zone charged by Courier Company</ol>
<ol>● Expected Charge as per X (Rs.)</ol>
<ol>● Charges Billed by Courier Company (Rs.)</ol>
<ol>● Difference Between Expected Charges and Billed Charges (Rs.)</ol>
<br>
<br>
Create a summary table as follow:
Question | Count | Amount (Rs.)<br>
<ol>Total orders where X has been correctly charged</ol>
<ol>Total Orders where X has been overcharged</ol>
<ol>Total Orders where X has been undercharged</ol>
</p>
