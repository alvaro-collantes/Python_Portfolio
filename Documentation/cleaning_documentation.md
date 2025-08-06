# Data Cleaning Report - Most Streamed Spotify Songs 2024

```python
# Overview
# Rows: 4,598 | Columns: 27
# Cleaning Steps: Duplicates → Standardization → Null Handling → Validation
```

## 1. Duplicate Removal
### **Actions**
- Removed 2 exact duplicates (0.04% of data)
- *Impact*: Prevented inflated metrics in analysis

### **Before/After**
| Metric          | Before | After |
|-----------------|--------|-------|
| Total Rows      | 4,600  | 4,598 |
| Duplicate Rows  | 2      | 0     |

---

## 2. Data Standardization
### **Column Types Fixed**
| Original Type | Corrected Type | Example Columns          |
|---------------|----------------|--------------------------|
| `object`      | `datetime`     | `Release Date`           |
| `object`      | `Int64`        | `Spotify Streams`        |
| `object`      | `string`       | `Artist`, `Track`        |

### **Key Steps**
```python
# Text Cleaning
df['Artist'] = df['Artist'].str.strip().str.title()

# Numeric Conversion
df['Streams'] = (df['Streams']
                .str.replace(',', '')
                .pipe(pd.to_numeric))
```

---

## 3. Missing Values
### **Handling Strategy**
| Null %   | Action                      | Example Columns       |
|----------|-----------------------------|-----------------------|
| >70%     | Dropped                     | `Pandora Streams`     |
| 20-70%   | Median (numeric)/"Unknown"  | `YouTube Likes`       |
| <20%     | "N/A" or median             | `Album Name`          |

**Result**: 0 nulls remaining (from initially 22/29 columns with nulls)

---

## 4. Validation Checks
```text
✅ Nulls: 0
✅ Duplicates: 0  
✅ Streams Validity: 100% >0  
✅ Date Range: 1987 (Rick Astley) - 2024
```

---

## Key Decisions
| Decision                  | Rationale                          |
|---------------------------|------------------------------------|
| Kept 1987 tracks          | Legacy hits are valid in streaming |
| Preserved ISRC case       | Required for music industry standards |
| Used median imputation    | Robust to outliers in stream counts |

---

## Files
- **Cleaned Data**: `Data/spotify_cleaned.csv`
- **Cleaning Script**: [`scripts/data_cleaning.ipynb`]

> 💡 *Run `final_validation()` in the notebook to reproduce checks*