#### 时间sql

#####  1.将时间转换成天数，然后计算天数

 统计以往的三十天的数据   to_days 可以将时间（date类型）转换成天

```sql
SELECT
id, store_id, store_name, shop_admin_id, captain_id, captain_name, trade_money, refund_money, 
trade_num, commission_money, stat_date, create_time, update_time
from
    t_captain_daily_trade_stat
where
    1 <= TO_DAYS(now()) -TO_DAYS(stat_date)
	&&	TO_DAYS(now()) -TO_DAYS(stat_date) <= 30
```



##### 2.查询某个日期时间是否在某个日期时间段中

###### 2.1 日期时间分开

select * from t_time where 

(DATE_FORMAT(begin_date, '%Y-%m-%d'),' ',begin_hour)<=now() and

(DATE_FORMAT(end_date, '%Y-%m-%d'),' ',end_hour) <= now()

##### 3.四种时间函数查询

###### ![](C:\Users\wuzhuwei\Desktop\studyNotes\images\1590135862331.png)



##### 4.时间的加减

date 日期  interval间隔  “间隔的内容（数字）”，间隔的单位 可以是year，month，day，second

date_add(date,interval,"1,1,1,1" day_second);

![](C:\Users\wuzhuwei\Desktop\studyNotes\images\15901394515053.png)

##### 5.时间格式化

SELECT DATE_FORMAT('2020-02-01 6:3:4','%Y-%m-%d %h:%i:%s')

![](C:\Users\wuzhuwei\Desktop\studyNotes\images\Snipaste_2020-05-22_17-31-07.png)

