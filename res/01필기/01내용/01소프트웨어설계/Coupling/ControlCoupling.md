
## ✅ 제어 결합도(Control Coupling)란?

> 한 모듈이 \*\*다른 모듈의 흐름(제어)\*\*에 영향을 주기 위해
> **플래그나 제어용 파라미터를 전달**하는 경우

즉, **"이 값을 줄 테니, 네가 이걸 보고 어떻게 동작할지 결정해"** 하는 방식이에요.

---

## ✅ 예제 코드 (Python)

```python
# printer.py
def print_message(msg, mode):
    if mode == "upper":
        print(msg.upper())
    elif mode == "lower":
        print(msg.lower())
    else:
        print(msg)
```

```python
# main.py
from printer import print_message

print_message("Hello, World!", "upper")  # 제어 플래그 전달
```

> `main.py`가 `"upper"`라는 **제어 정보를 직접 넘기고**,
> `print_message()` 내부에서 분기 처리합니다.
> → 이게 **제어 결합도**입니다.

---

## ✅ 왜 문제인가?

* `main.py`는 `printer.py`의 \*\*내부 동작 방식(upper/lower 분기)\*\*을 **알고 있어야** 함
* 둘 사이의 **기능적 독립성 저하**
* 새로운 모드가 생기면 → 호출자도 수정해야 할 수도 있음

---

## ✅ 제어 결합도를 줄이려면?
- 전략 패턴
- 함수 자체를 분기 없이 나누는 것

### 개선 예:

```python
# printer.py
def print_upper(msg):
    print(msg.upper())

def print_lower(msg):
    print(msg.lower())
```

```python
# main.py
from printer import print_upper
print_upper("Hello, World!")  # 더 명확하고 독립적
```

> 이제 **main.py는 어떤 일이 일어날지 명확하게 알 수 있고**,
> **printer.py 내부 구현 변경에 덜 영향을 받습니다.**

