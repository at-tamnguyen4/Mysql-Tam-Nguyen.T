#### 11. Lấy tổng lượt view của từng category thông qua blog và news
```mysql
select id, title, sum(view) as total_view from 
(
 select view, category_id from blog
 union all
 select view, category_id from news
) as total inner join category on category.id=total.category_id
group by id, title
```
