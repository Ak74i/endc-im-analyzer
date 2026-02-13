# Example ENDC Combinations

This file shows example combinations you can use to test the IM Analysis Tool.

## Quick Start

Create an Excel file (.xlsx) with the following structure:

### Column Headers (Row 1):

**Required Column:**
```
ENDC Combination
```

**Optional Columns (will be displayed if present):**
```
ENDC Combination | Type | 3GPP Release | Status
```

### Example Data - Basic (Required column only):
```
DC_1A-3A-8A-20A-38A_n78A
DC_2A-4A-66A_n77A
DC_3A-7A-28A_n1A-n78A
DC_1A-3A-7A_n78A
DC_2A-5A-66A_n2A-n77A
```

### Example Data - With Optional Columns:
```
DC_1A-3A-8A-20A-38A_n78A | NSA | Rel-17 | LIVE
DC_2A-4A-66A_n77A | NSA | Rel-16 | LIVE
DC_3A-7A-28A_n1A-n78A | NSA | Rel-18 | PLANNED
DC_1A-3A-7A_n78A | NSA | Rel-17 | LIVE
DC_2A-5A-66A_n2A-n77A | NSA | Rel-17 | TEST
```

**About Optional Columns:**
- The tool automatically detects these columns if present
- If not present, the tool works perfectly without them
- **Type**: NSA (Non-Standalone), SA (Standalone), or any custom value
- **3GPP Release**: Rel-15, Rel-16, Rel-17, Rel-18, etc.
- **Status**: LIVE, PLANNED, TEST, or any custom status
- You can include any or all of these columns

## Combination Format Rules

### General Structure:
```
DC_[LTE bands separated by -]_[5G NR bands separated by -]
```

### LTE Bands:
- Use format: `[band number][bandwidth class]`
- Examples: `1A`, `3A`, `7A`, `20A`, `66A`
- Common classes: `A` (most common), `C` (wider bandwidth)

### 5G NR Bands:
- Use format: `n[band number][bandwidth class]`
- Examples: `n1A`, `n78A`, `n77A`, `n257A`
- For wider configurations: `n78(2A)` means 2x carrier aggregation

### Examples by Region:

**Europe/APAC:**
```
DC_1A-3A-8A-20A_n78A
DC_3A-7A-8A-20A_n1A-n78A
DC_1A-8A-28A_n78A
```

**Americas:**
```
DC_2A-4A-66A_n77A
DC_2A-4A-12A-66A_n2A-n77A
DC_4A-5A-66A-71A_n77A
```

**Asia (with n79):**
```
DC_1A-3A-41A_n79A
DC_3A-8A-40A_n79A
DC_1A-3A-7A-41A_n1A-n79A
```

**mmWave Scenarios:**
```
DC_2A-66A_n77A-n257A
DC_1A-3A_n78A-n258A
DC_4A-66A_n77A-n260A
```

## Creating Your Excel File

### Method 1: Excel
1. Open Microsoft Excel or LibreOffice Calc
2. In cell A1, type: `ENDC Combination`
3. Starting from A2, paste your combinations (one per row)
4. Save as: `my_combinations.xlsx`

### Method 2: Google Sheets
1. Create new Google Sheet
2. In cell A1, type: `ENDC Combination`
3. Add combinations starting from A2
4. File → Download → Microsoft Excel (.xlsx)

### Method 3: Copy-Paste Template

Here's a ready-to-use template with 20 diverse examples:

```
ENDC Combination
DC_1A-3A-8A-20A-38A_n78A
DC_2A-4A-66A_n77A
DC_3A-7A-28A_n1A-n78A
DC_1A-3A-7A_n78A
DC_2A-5A-66A_n2A-n77A
DC_8A-20A-28A_n78A
DC_1A-3A_n1A-n3A-n78A
DC_4A-66A_n77A
DC_1A-8A-20A_n1A-n78A
DC_2A-4A-12A-66A_n2A-n77A
DC_3A-7A-8A-20A_n78A
DC_2A-4A-5A-66A_n77A
DC_1A-3A-8A_n1A-n78A
DC_4A-12A-66A_n77A
DC_3A-7A-20A-28A_n3A-n78A
DC_2A-66A-71A_n2A-n77A
DC_1A-3A-7A-8A-20A_n78A
DC_4A-5A-66A_n77A
DC_8A-20A-28A-38A_n78A
DC_2A-4A-66A_n2A-n77A-n257A
```

## Testing the Tool

1. Save the combinations to an Excel file
2. Open `endc_im_analyzer.html` in your browser
3. Click "Choose Excel File"
4. Select your file
5. View the analysis!

## Tips for Real Data

- Start with 10-20 combinations to test
- Use actual combinations from your network planning
- Verify band numbers against 3GPP specifications
- Check regional frequency allocations
- Consider both NSA and SA 5G scenarios

## Common Mistakes to Avoid

❌ **Wrong**: Missing DC_ prefix
```
1A-3A-8A_n78A  (Missing DC_)
```

✅ **Correct**:
```
DC_1A-3A-8A_n78A
```

❌ **Wrong**: Spaces in combination
```
DC_1A - 3A - 8A_n78A
```

✅ **Correct**:
```
DC_1A-3A-8A_n78A
```

❌ **Wrong**: Mixing separators
```
DC_1A,3A,8A_n78A
```

✅ **Correct**:
```
DC_1A-3A-8A_n78A
```

## Need Help?

- Check README.md for supported bands
- Verify band numbers in 3GPP specifications
- Open an issue on GitHub if you find bugs
- Share your use case to help improve the tool!
