## vòng lặp while
- while là 1 vòng lặp phổ biến và trực quan 
```
while [ condition ]; do
[COMMANDS]
done
```
```
num=1
while [ $num -le 10 ]; do
     echo $(($num * 3))
     num=$(($num+1))
done
```
- `while [ $num -le 10 ]; do` 
- `$num` là giá trị của biến `num`
- `-le` là nhỏ hơn hoặc bằng 
- bao giờ `$num` còn nhỏ hơn hoặc bằng 10 thì vòng lặp tiếp tục chạy . `$num` lớn hơn 10 vòng lặp dừng 
## vòng lặp for 
```
prime=(2 3 5 7 11 13 17 19 23 29)
for i in "${prime[@]}"; do
        echo $i
done
```
- `prime=(2 3 5 7 11 13 17 19 23 29)` khai báo mảng 
- `for i in "${prime[@]}"; do` để duyệt từng phần tử trong mảng 
  
