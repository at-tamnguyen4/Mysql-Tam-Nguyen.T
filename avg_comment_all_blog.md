#### 9. Lấy số lượng comment trung bình của tất cả blog
```mysql
select avg(count_com) as avg_com_all_blog 
from (
  select target_id, count(user_id) as count_com
  from comment
  where target_table = "blog"
  group by target_id
) avgcomment;
```
