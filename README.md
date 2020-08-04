## Market Response Model & Uplift Modelling
 
The dataset I was working with has information about 64,000 customers who were divided into three approximately equal groups:

* Customers who received a discount offer
* Buy one get one offer
* No offer at all.

My objective was to build a market response model to measure customers response to each offer and find out which one has the best conversion rates. To go a little bit further I built an Uplift model so the company can target the most pursuable customers in order to correctly distribute marketing campaigns budget.

Here are the answers I was able to find throughout this project:

* Giving an offer does increase conversion rates: Discount - 7.66% and BOGO - 4.52%. If we were basing our decisions only on this factor, then Discount campaign would we the one to chose for targeting campaign. For 21307 customers who were sent a discount, the Revenue Uplift per customer is \$1.9 compared to $1.1 of BOGO offer.

* Customers from rural area were the least represented in the dataset but showed the best conversion rates, although most of the purchases were made customers with a Suburban zip code.

* Conversion rates increase with the increase of the value of the historical purchases until it hits the amount of $1495. With higher value conversion rates drop by approximately 9%.

* Conversion decreases during the first 10 months since last purchase from 19% to 12%. Then it slightly increases. It can be due to many reasons one of which could be the effect of the given offers.

* The highest conversion rates showed the customers who had used one of the offers before and received one during this campaign.

* XGBoost ML model appeared to be the most reliable to predict conversions with the 'history' as the most important feature in it.

* The objective of Uplift modelling is targetting Treatment Responders (Customers that will purchase only if they receive an offer) and Control Non-Responders (Customers that will not purchase if they don’t receive an offer). On the other hand, we need to avoid targeting Treatment Non-Responders (Customer that won’t purchase in any case) and Control Responders (Customers that will purchase without an offer).

* Thanks to the uplift modelling we were able to calculate the uplift score and select the potential target group with the highest probability of buying with the treatment, which are the users in the 80th percentile. Uplift modelling showed that with the right targeting Discount Revenue Uplift per customer is \$3.21 which is 1.31 better then original Discount campaign. With modelled targeting only one quarter of the target group is contributing to 74% of the revenue uplift. (Discount Conversion Uplift is 33.87%, Discount Order Uplift: 1202.28, Discount Revenue Uplift: $30056.94)

Check Market Response Model & Uplift Modelling.ipynb for more details 
