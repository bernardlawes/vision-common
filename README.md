
---

## 🔗 `vision-common/README.md`

```markdown
# 🔄 Vision Shared Utils

Centralized config and utility repo for label management, preprocessing, and model metadata shared between `vision-train-py` (Python training/export) and `vision-infer-cpp` (C++ inference).

---

## 📁 Structure

| Path                          | Purpose |
|-------------------------------|---------|
| `labels/class_map.json`       | Class ID-to-label mapping used across all projects |
| `configs/model_meta.json`     | Input size, normalization values, versioning |
| `tools/python/`               | Python loaders and image preprocessors |
| `tools/cpp/`                  | C++ header-only implementations for matching preprocessing logic |

---

## 📦 Use in Python

```python
from tools.python.label_loader import load_labels
labels = load_labels("labels/class_map.json")
```

🧩 Use in C++

```cpp
#include "tools/cpp/label_loader.h"
auto labels = LoadLabels("labels/class_map.json");
```

## 🧠 Goals
Prevent label/preprocessing drift between training and inference

Ensure model configs are reusable, documented, and versioned

Enable full parity across Python and C++ implementations