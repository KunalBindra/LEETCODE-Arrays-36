# LEETCODE-Arrays-36
```text
[
 ['5','3','.','.','7','.','.','.','.'],
 ['6','.','.','1','9','5','.','.','.'],
 ['.','9','8','.','.','.','.','6','.'],
 ['8','.','.','.','6','.','.','.','3'],
 ['4','.','.','8','.','3','.','.','1'],
 ['7','.','.','.','2','.','.','.','6'],
 ['.','6','.','.','.','.','2','8','.'],
 ['.','.','.','4','1','9','.','.','5'],
 ['.','.','.','.','8','.','.','7','9']
]
```

---

### 🔎 Dry Run Process

We loop through each cell `(i, j)`:

---

**Step 1: (0,0) → '5'**

* `rowKey = "5row0"`
* `colKey = "5col0"`
* `boxKey = "5box0_0"`
* `hash` is empty → add all three. ✅

---

**Step 2: (0,1) → '3'**

* `rowKey = "3row0"`
* `colKey = "3col1"`
* `boxKey = "3box0_0"`
* None exists → add all. ✅

---

**Step 3: (0,4) → '7'**

* `rowKey = "7row0"`
* `colKey = "7col4"`
* `boxKey = "7box0_1"`
* Add all. ✅

---

**Step 4: (1,0) → '6'**

* `rowKey = "6row1"`
* `colKey = "6col0"`
* `boxKey = "6box0_0"`
* Add all. ✅

---

**Step 5: (1,3) → '1'**

* `rowKey = "1row1"`
* `colKey = "1col3"`
* `boxKey = "1box0_1"`
* Add all. ✅

---

**Step 6: (1,4) → '9'**

* `rowKey = "9row1"`
* `colKey = "9col4"`
* `boxKey = "9box0_1"`
* Add all. ✅

---

**Step 7: (1,5) → '5'**

* `rowKey = "5row1"`
* `colKey = "5col5"`
* `boxKey = "5box0_1"`
* None exists yet → add all. ✅

---

**Step 8: (2,1) → '9'**

* `rowKey = "9row2"`
* `colKey = "9col1"`
* `boxKey = "9box0_0"`
* All unique → add. ✅

---

**Step 9: (2,2) → '8'**

* `rowKey = "8row2"`
* `colKey = "8col2"`
* `boxKey = "8box0_0"`
* Add. ✅

---

**Step 10: (2,7) → '6'**

* `rowKey = "6row2"`
* `colKey = "6col7"`
* `boxKey = "6box0_2"`
* Add. ✅

---

...and so on. Each number gets encoded into **row, col, box form**, and checked against the `hash`.

---

### 🎯 Key Observation

* If a duplicate exists (say another '5' in row 0), then `"5row0"` will already be in the hash → function returns `false`.
* Otherwise, loop finishes and returns `true`.

---

✅ For this board, the function will **return true** (valid Sudoku).

---
