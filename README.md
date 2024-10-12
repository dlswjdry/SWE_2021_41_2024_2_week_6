# SWE_2021_41_2024_2_week_6

## Week4 Assignment
Learn abount how to use google colab and basic python such as data type, basic loops, functions, if ~ else, and file handling. 

<br>

### Task 
- Complete **isHappy** function following the description below
- A **happy number** is a number defined by the following process:
  - Starting with any positive integer, replace the number by the sum of the squares of its digits
  - Repeat the process until the number equals 1 (where it will stay), or it loops endlessly in a cycle which does not include 1.
  - Those numbers for which this process ends in 1 are happy.
- Return **true** if n is a happy number, and **false** if not
- https://github.com/dlswjdry/SWE_2021_41_2024_2_week_4.git



### Code
```python
def isHappy(n):
  seen = set()  # 이미 본 숫자들을 저장

  while n != 1 and n not in seen:  # 1이 되거나 새로운 숫자일 때만 처리
      seen.add(n)
      # print(seen)
      n = sum(int(digit) ** 2 for digit in str(n))
      # print(n)

  return n == 1


n = int(input("숫자를 입력하세요: "))
print(isHappy(n))

```

### description
1. seen = set():
이미 확인한 숫자들을 저장하기 위해 빈 set을 사용

2. while n != 1 and n not in seen::
주어진 숫자가 1이 되지 않았거나, 이미 확인된 숫자가 아니라면 루프를 계속 돌린다.
숫자가 1이 되거나, 숫자가 이미 seen 집합에 있으면 루프를 멈춘다.

3. seen.add(n):
현재 숫자를 seen 집합에 추가하여 같은 숫자가 다시 나오면 무한 루프에 빠지지 않도록 한다.

4. n = sum(int(digit) ** 2 for digit in str(n)):
숫자 n의 각 자릿수를 문자열로 변환한 후, 각 자릿수의 제곱을 더해 새로운 n을 계산한다.
예를 들어, n = 19일 경우, 1^2 + 9^2 = 82로 변환됩니다.

5. return n == 1:
n이 1이 되면 True를 반환하고, 그렇지 않으면 False 반환한다.

6. n = int(input("숫자를 입력하세요: "))
사용자로부터 숫자를 입력받아 isHappy() 함수로 그 숫자가 happy number인지 확인하고, 결과를 출력한다.

### Test case
#### Testcase1.
Input: 19
```python
n = 19
print(isHappy(n))  # Expected output: True
```

#### Testcase2.
Input: 2
```python
n = 2
print(isHappy(n))  # Expected output: False
```

<br>


---

## Week5 Assignment
Learn about Docker

<br>

### Docker Commands and Explanation
**1. Check Operating System Information Inside Container**
```bash
docker exec ossp-container cat /etc/os-release
```
- This command shows the operating system information from inside the container by reading the /etc/os-release file.

```bash
PRETTY_NAME="Ubuntu 24.04.1 LTS"
NAME="Ubuntu"
VERSION_ID="24.04"
ID=ubuntu
...
```
<br>

**2. Check Git Version**
```bash
docker exec ossp-container git --version
```
- This command checks the version of Git installed inside the container.

```bash
git version 2.43.0
```
<br>

**3. Check Python3 Version**
```bash
docker exec ossp-container python3 --version
```
- This command checks the Python 3 version inside the container.

```bash
Python 3.12.3
```
<br>

**4. Inspect Container Bind Mounts**
```bash
docker inspect --format="{{ .HostConfig.Binds }}" ossp-container
```
- This command inspects the bind mounts for the container, showing how directories from the host are mapped into the container.

```bash
[/host/path:/container/path:rw]
```

## Docker Command Output

My output for the Docker commands:

![image](https://github.com/user-attachments/assets/fb315b6a-1e6a-41e0-8d3f-c52362e2643f)





