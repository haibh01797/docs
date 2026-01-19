# lab Shell
1. ví dụ kiểm tra xem 2 số mình nhập bằng nhau ko hay lớn hơn nhỏ hơn
```
echo "enter the first number"
read num1
echo "enter the second number"
read num2
if [ $num1 -gt $num2 ]; then
      echo "num1 lon hon num2"
elif [ $num1 -lt $num2 ]; then
      echo "num2 lon hon num1"
else
      echo "num1 va num2 bang nhau"
fi
```
- `echo` dùng để in ra thông báo màn hình 
- `read` dùng để dọc dữ liệu người dùng nhập 
- `if` bắt đầu câu điều kiện trong bash
- `elif` nếu ko phải điều trên thử điều kiện khác 
- `else` nếu `if` `elif` sai thì `else` mới được thực thi
- `$num1 -gt $num2`
  - `$num1 $num2` là 2 giá trị cần so sánh 
  - `-gt`là >
  - `-lt`là <

```
root@node3:/home/devops# bash -u  hai.sh
enter the first number
3
enter the second number
2
num1 lon hon num2
root@node3:/home/devops# bash -u  hai.sh
enter the first number
2
enter the second number
3
num2 lon hon num1
root@node3:/home/devops# bash -u  hai.sh
enter the first number
3
enter the second number
3
num1 va num2 bang nhau
```
