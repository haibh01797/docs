# ví dụ kiểm tra xem ngày trong tuần hay là ngày cuối tuần 
```
day=$(date +"%a")

case $day in

  Mon | Tue | Wed | Thu | Fri)
    echo "today is a weekday"
    ;;

  Sat | Sun)
    echo "today is the weekend"
    ;;

  *)
    echo "date not recognized"
    ;;
esac
```

- `day=$(date +"%a")` tạo biến cho `day` và gán kết quả là `date`
- `case $day in` 
  - `case` dùng để so sánh 1 biến với nhiều pattern
  - `in` mẫu so sánh 
- `Mon | Tue | Wed | Thu | Fri` đây là các pattern cần so sánh 
- nếu `$day` là 1 trong các giá trị trong này thì 
- câu lệnh `echo "today is a weekday"` sẽ được thực thi 
- `*` là pattern mặc định 
- nếu như ko có bất kỳ giá trị ở các pattern trên thì 
- câu lệnh `echo "date not recognized"` sẽ được thực thi 

```
root@node3:/home/devops# bash -u  hai2.sh
today is a weekday
``
