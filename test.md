```
ELECT DISTINCT
    products.product_name,
    products.size,
    products.price,
    order_lines.sku,
    "total_sold" = sum(order_lines.quantity) 
        OVER (PARTITION BY order_lines.sku)
FROM twotrees.sales.order_lines INNER JOIN twotrees.inventory.products
    ON order_lines.sku = products.sku
ORDER BY "total_sold" DESC
```

|product_name|size|price|sku|total_sold|
|---|---|---|---|---|
|First Cold Press|8|8.99|FCP008|9|
|First Cold Press|128|24.99|FCP128|7|
|Koroneiki|128|26.99|KRN128|7|
|Picual|16|14.99|PIC016|7|
|Pure|64|20.99|PUR064|6|
|Extra Virgin|128|24.99|EV128|5|
|Frantoio|128|26.99|FR128|5|
|Refined|8|8.99|REF008|5|
|Basil-Infused EVO|8|10.99|BI008|4|
|Extra Virgin|32|16.99|EV032|4|
|First Cold Press|16|12.99|FCP016|4|
|Garlic-Infused EVO|32|19.99|GI032|4|
|Chili-Infused EVO|16|15.99|JI016|4|
|Chili-Infused EVO|32|19.99|JI032|4|
|Leccino|8|10.99|LEC008|4|
|Picholine|32|19.99|PCH032|4|
|Picholine|64|23.99|PCH064|4|
|Pendolino|64|22.99|PEN064|4|
|Picual|8|10.99|PIC008|4|
|Pure|16|12.99|PUR016|4|
|Rosemary-Infused EVO|32|18.99|RI032|4|
|Virgin|32|16.99|V032|4|
|Delicate|64|22.99|ALB064|3|
|Extra Virgin|8|8.99|EV008|3|
|Light|8|8.99|LGT008|3|
|Light|16|12.99|LGT016|3|
|Lemon-Infused EVO|16|12.99|LI016|3|
|Mandarin-Infused EVO|8|8.99|MI008|3|
|Oblica|8|11.99|OBL008|3|
|Oblica|128|27.99|OBL128|3|
|Picual|64|22.99|PIC064|3|
|Pure|128|24.99|PUR128|3|
|Delicate|128|26.99|ALB128|2|
|Frantoio|8|10.99|FR008|2|
|Bold|8|11.99|HOJ008|2|
|Bold|16|15.99|HOJ016|2|
|Bold|64|23.99|HOJ064|2|
|Bold|128|27.99|HOJ128|2|
|Manzanilla|128|26.99|MAN128|2|
|Moraiolo|32|18.99|MOR032|2|
|Pendolino|32|18.99|PEN032|2|
|Frantoio|64|22.99|FR064|1|
|Mission|16|14.99|MIS016|1|
|Mission|32|18.99|MIS032|1|
|Mission|64|22.99|MIS064|1|
|Pendolino|8|10.99|PEN008|1|
|Rosemary-Infused EVO|8|10.99|RI008|1|
|Rosemary-Infused EVO|16|14.99|RI016|1|
|Virgin|64|20.99|V064|1|
