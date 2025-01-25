SELECT 
    date_upd::date AS update_date,
    COUNT(name) AS name_cnt,
    name_store
FROM
    products_data_all
WHERE
    weight :: real > 5
    AND date_upd::date = '2019-06-03'
    AND units = 'oz'
GROUP BY
    update_date,
    name_store
having
    COUNT(name) < 20;
