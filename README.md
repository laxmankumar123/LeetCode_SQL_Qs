# LeetCode_SQL_Qs

Q1251. Average Selling Price

SELECT  p.product_id,ROUND(COALESCE(SUM(p.price * u.units) / SUM(u.units), 0),2) AS average_price FROM Prices p
LEFT JOIN UnitsSold u ON p.product_id = u.product_id AND u.purchase_date BETWEEN p.start_date AND p.end_date
GROUP BY p.product_id;


1693. Daily Leads and Partners


select date_id , make_name ,count(DISTINCT lead_id) as unique_leads,count(DISTINCT partner_id) as unique_partners from DailySales group by 1,2;
