# python


## module


### datetime

#### timezone 관련해서...
`pytz` 모듈을 이용하자.
```python3
from pytz import timezone, utc

#now = datetime.datetime.now()
#now.replace(tzinfo=timezone('Asia/Seoul'))
#print(now.time)

print(datetime.datetime.now().strftime('%Y-%m-%d'))

current_milli_time = lambda: int(round(time.time() * 1000))
print(current_milli_time())

dateInObject = datetime.datetime.fromtimestamp(current_milli_time()/1000.0)
print(dateInObject.strftime('%Y-%m-%d'))
```

### file

#### file size 측정하기
```python3
# 파일이 존재하지 않는 경우에도 0
# 데이터가 빈 경우에도 0
os.stat("data1.txt").st_size
```
#### open(f, mode, ...)
##### mode
**파일열기모드	설명**
<br>r	읽기모드 - 파일을 읽기만 할 때 사용
<br>w	쓰기모드 - 파일에 내용을 쓸 때 사용
<br>a	추가모드 - 파일의 마지막에 새로운 내용을 추가 시킬 때 사용

`+`를 모드 캐릭터 뒤에 추가할 경우 나머지 권한도 같이 오픈된다.



#### 

### json
#### JSONLint
Json format checker (lint)
https://jsonlint.com/

#### json.load(f)
open() 메소드를 통해 연 파일을 json 으로 load 하기 위한 함수

error (1,1) : file 내 쓰여진 값이 없는 경우에 뱉어내는 에러(빈 데이터를 가져와 load 할 때 발생하는 에러)
try-except 구문을 활용해 예외처리를 해주도록 하자.

loads(f)는 메모리에 있는 정보를 읽어 json으로 load 하기 위한 함수(?)

#### json.dump(jsonData, f)
file 에 json data를 기록하기 위한 함수


### list

#### sublist
```python
>>> list1 = ['a','b','c','d','e','f','g','h', 'i', 'j', 'k', 'l']
>>> print list1[:5]
['a', 'b', 'c', 'd', 'e']
>>> print list1[-7:]
['f', 'g', 'h', 'i', 'j', 'k', 'l']
```


#### TypeError: 'dict_values' object is not subscriptable

###### subscriptable 이란?
기본적으로 객체가 `__getitem __ ()` 메서드를 구현하는 경우를 의미한다.
즉, 다른 개체를 포함할 수 있는 "컨테이너"인 개체를 뜻한다. 
여기에는 strings, lists, tuples, and dictionaries 가 포함된다.

```python
dict_list = some_dict.values()
casted_list = list(dict_list)

# after casting, you can use any kind of subscriptable methods
casted_list[:-1]
```


------

## VS CODE
### Shortcuts
##### Trigger parameter hint (파라메터 힌트 보기)

For Windows and Linux:`Ctrl + Shift + Space`

For MacOs:
`⇧ + ⌘ + Space`
