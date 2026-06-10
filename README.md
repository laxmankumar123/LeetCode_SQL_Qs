# LeetCode_SQL_Qs

Q1251. Average Selling Price

SELECT  p.product_id,ROUND(COALESCE(SUM(p.price * u.units) / SUM(u.units), 0),2) AS average_price FROM Prices p
LEFT JOIN UnitsSold u ON p.product_id = u.product_id AND u.purchase_date BETWEEN p.start_date AND p.end_date
GROUP BY p.product_id;


1693. Daily Leads and Partners


select date_id , make_name ,count(DISTINCT lead_id) as unique_leads,count(DISTINCT partner_id) as unique_partners from DailySales group by 1,2;


1148. Article Views I
1149. select distinct author_id as id from Views where author_id=viewer_id order by author_id  ;


178. Rank Scores
SELECT 
    s1.score,
    (
        SELECT COUNT(DISTINCT s2.score)
        FROM Scores s2
        WHERE s2.score >= s1.score
    ) AS `rank`
FROM Scores s1
ORDER BY s1.score DESC;





SELECT id, 
    MAX(IF(month="Jan", revenue, NULL)) AS Jan_Revenue, 
    MAX(IF(month="Feb", revenue, NULL)) AS Feb_Revenue, 
    MAX(IF(month="Mar", revenue, NULL)) AS Mar_Revenue,
    MAX(IF(month="Apr", revenue, NULL)) AS Apr_Revenue,
    MAX(IF(month="May", revenue, NULL)) AS May_Revenue,
    MAX(IF(month="Jun", revenue, NULL)) AS Jun_Revenue,
    MAX(IF(month="Jul", revenue, NULL)) AS Jul_Revenue,
    MAX(IF(month="Aug", revenue, NULL)) AS Aug_Revenue,
    MAX(IF(month="Sep", revenue, NULL)) AS Sep_Revenue,
    MAX(IF(month="Oct", revenue, NULL)) AS Oct_Revenue,
    MAX(IF(month="Nov", revenue, NULL)) AS Nov_Revenue,
    MAX(IF(month="Dec", revenue, NULL)) AS Dec_Revenue
    
FROM Department
GROUP BY id
ORDER BY id

