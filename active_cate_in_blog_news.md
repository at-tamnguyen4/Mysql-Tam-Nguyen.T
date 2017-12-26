#### 10. Lấy Category có tồn tại blog hoặc news đã active (không được lặp lại category)
```mysql
select distinct category.*
from category 
where exists
(
	select category_id
	from blog
	where blog.is_active = 1 and blog.category_id=category.id
)
or exists 
(
	select category_id
	from news
	where news.is_active = 1 and news.category_id=category.id
)
```
