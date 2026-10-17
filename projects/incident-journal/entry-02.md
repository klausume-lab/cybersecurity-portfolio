# Journal Entry 2

Date: October 10, 2026
Entry:
2
Description
I reviewed a training scenario about a retail company's customer data breach. The attacker exploited weak access controls on the online store to access sensitive customer information and demand payment.
Tool(s) used
I reviewed the supplied incident final report in Google Docs. The report says the security team analyzed web server access logs, but I did not personally inspect the logs or use investigative software.
The 5 W's 
* Who: An unidentified attacker exploited the retailer's website and demanded payment to keep stolen data private.
* What: The attacker changed order numbers in purchase-confirmation URLs to view other customers' transactions, steal personal and financial data, and demand $25,000, later increased to $50,000. The report estimates about 50,000 affected customer records and $100,000 in financial impact.
* When: The first extortion email arrived December 22, 2022, at 3:13 p.m. PT; a second arrived December 28. The report lists December 28 at 7:20 p.m. PT as the incident time, and the investigation continued through December 31.
* Where: The company's e-commerce web application, specifically customer purchase-confirmation pages accessed over the internet.
* Why: Weak access controls allowed forced browsing of order pages by changing the order number in a URL. The attacker appeared to want money in exchange for not exposing the stolen data.
Additional notes
The security team reviewed web server logs showing many sequential customer order requests. The company disclosed the breach and offered identity protection to affected customers. The report recommends routine scans and penetration tests, URL allowlisting, and stronger authorization checks; it does not confirm that all these safeguards are already in place. One point I would follow up on: the report dates the incident to December 28, but the first extortion email arrived December 22, so when was the data first accessed? The course scenario also says over one million users, while the report lists about 50,000 affected records.

Source: Incident handler’s journal. Course simulation; narrative records source claims, not independently reverified actions. [Journal index](README.md).
