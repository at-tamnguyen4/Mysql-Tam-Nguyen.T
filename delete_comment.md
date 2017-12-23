#### 7. Xoá tất cả comment của user = 2 trong blog = 5
```mysql
delete from comment
where user_id = 2 and target_id = 5 and target_table= "blog"
```
