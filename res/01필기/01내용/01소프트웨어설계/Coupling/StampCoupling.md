
## ✅ 스탬프 결합도(Stamp Coupling)란?
### 🔸 키워드:

* **"필요 이상으로 많은 정보"가 전달됨**
* 서로 **자료구조의 내부를 알고 있어야 함**
* **은근한 의존성 증가**

---

## ✅ 예제 (Python)

```python
# data.py
class User:
    def __init__(self, name, email, password):
        self.name = name
        self.email = email
        self.password = password
```

```python
# module_a.py
def greet_user(user):  # user 전체를 받지만,
    print(f"Hello, {user.name}!")  # name만 씀
```

```python
# main.py
from data import User
from module_a import greet_user

u = User("Alice", "alice@example.com", "1234")
greet_user(u)  # ← 스탬프 결합도 발생
```

> `greet_user()` 함수는 `user.name`만 필요하지만
> **전체 User 객체를 넘기고 있어서**
> → **스탬프 결합도** 발생

---

## ✅ 왜 문제인가?

* `greet_user()`는 name만 필요한데, 전체 객체(User)를 받아야 하므로:

  * 다른 필드가 바뀌면 영향을 받을 수 있음
  * 테스트나 유지보수 시, **불필요한 의존성이 생김**
* **"이 모듈은 user 객체의 구조를 은근히 알아야 한다"** → 결합도 증가

---

## ✅ 해결 방향: 필요한 값만 전달

```python
def greet_user(name):  # 필요한 데이터만 받음
    print(f"Hello, {name}!")
```

```python
greet_user(u.name)
```

> → \*\*데이터 결합도(Data Coupling)\*\*로 개선됨
> → 필요한 데이터만 주고받음 → **결합도 ↓**

---

## ✅ 한 줄 요약

> \*\*스탬프 결합도(Stamp Coupling)\*\*는
> **일부 정보만 필요하면서 전체 자료구조를 전달하는 결합 방식**으로,
> **불필요한 의존성과 결합도를 증가시킵니다.**
> 가능한 한 **필요한 데이터만 따로 추출해서 넘기는 게 바람직**합니다.

---

원하시면 **결합도 6\~7단계 전체 요약표**도 만들어드릴 수 있어요!
