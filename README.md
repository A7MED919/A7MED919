
```python
import pandas as pd
import os
import zipfile

# تحميل البيانات من ملف CSV
data = pd.read_csv("data.csv")

# تحليل البيانات وتخزينها في ملف ZIP مضغوط
with zipfile.ZipFile("data.zip", mode="w") as archive:
    archive.write("data.csv")

# إنشاء جدول للبيانات
table = pd.DataFrame(data)

# تحليل البيانات وفقًا للأساس المحدد
analysis = table.groupby("اساس").sum()

# عرض عدد البيانات وثمنها
count = table.count()
total_price = table["ثمن"].sum()
print(f"عدد البيانات: {count}")
print(f"إجمالي الثمن: {total_price}")
```
