# 쿼리 낙서장

## SQL BETWEEN vs > AND < 차이

### 1️⃣ > AND < 조건

```sql
WHERE duration_seconds > 400 
  AND duration_seconds < 500
```

* 400 **초과**
* 500 **미만**
  👉 범위: **401 ~ 499**

---

### 2️⃣ BETWEEN 조건

```sql
WHERE duration_seconds BETWEEN 400 AND 500
```

* 400 **이상**
* 500 **이하**
  👉 범위: **400 ~ 500**

---

### ⚠️ 핵심 차이

| 값   | > AND < | BETWEEN |
| --- | ------- | ------- |
| 400 | ❌ 제외    | ✅ 포함    |
| 500 | ❌ 제외    | ✅ 포함    |

---

### 💡 정리

* `BETWEEN` → **양쪽 값 포함**
* `> AND <` → **양쪽 값 제외**

👉 경계값이 중요하면 `>=`, `<=`로 명확하게 작성하는 것이 안전

```sql
WHERE duration_seconds >= 400 
  AND duration_seconds <= 500
```

---

### 🚨 참고

```sql
SELECT COUNT(*)
```
