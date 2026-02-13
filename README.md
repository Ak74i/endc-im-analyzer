# ENDC Intermodulation Analysis Tool

A generic RF engineering analysis tool for calculating and visualizing intermodulation (IM2/IM3) interference in EN-DC (E-UTRA-NR Dual Connectivity) carrier combinations.

## 📋 Overview

This tool analyzes ENDC carrier combinations to identify potential intermodulation interference between LTE and 5G NR frequency bands. It calculates IM2 (2nd order) and IM3 (3rd order) intermodulation products and assesses their impact on victim carriers.

### Key Features

- **Comprehensive Band Support**: 50+ LTE and 5G NR bands covering global frequency allocations
- **Real-time IM Analysis**: Automatic calculation of IM2 and IM3 products
- **Risk Assessment**: Color-coded risk levels from Minimal to Critical
- **Carrier Heatmap**: Visual representation of interference risk across all carriers
- **Interactive Analysis**: Click on any carrier or combination for detailed breakdown
- **Export Capabilities**: Export results to Excel for further analysis

## 🎯 Use Cases

- Network planning and optimization
- Carrier aggregation feasibility studies
- EN-DC deployment scenarios
- RF engineering education and training
- Interference mitigation planning

## 🚀 Getting Started

### Prerequisites

- Modern web browser (Chrome, Firefox, Safari, Edge)
- Excel file with ENDC combinations

### Installation

1. Clone this repository:
```bash
git clone https://github.com/ak74i/endc-im-analyzer.git
cd endc-im-analyzer
```

2. Open `endc_im_analyzer.html` in your web browser

No installation or dependencies required - it's a standalone HTML file!

## 📊 Input Format

Create an Excel file (.xlsx) with your ENDC combinations. The tool expects:

**Column A**: ENDC Combination

### Example Combinations:
```
DC_1A-3A-8A-20A_n78A
DC_2A-4A-66A_n77A
DC_3A-7A-28A_n1A-n78A
DC_1A_n1A-n78A
```

### Supported Band Formats:
- LTE bands: `1A`, `3A`, `7A`, `20A`, `28A`, `66A`, etc.
- 5G NR bands: `n1A`, `n78A`, `n77A`, `n257A`, etc.
- Bandwidth variants: `40C`, `41C`, `n78(2A)`, etc.

### Sample Template

See `example_combinations.xlsx` (create this file with your combinations)

## 🌍 Supported Frequency Bands

### LTE Bands (Selected)
| Band | Uplink (MHz) | Downlink (MHz) | Region |
|------|--------------|----------------|--------|
| 1A | 1920-1980 | 2110-2170 | Global |
| 2A | 1850-1910 | 1930-1990 | Americas, APAC |
| 3A | 1710-1785 | 1805-1880 | Global |
| 4A | 1710-1755 | 2110-2155 | Americas |
| 7A | 2500-2570 | 2620-2690 | Global |
| 8A | 880-915 | 925-960 | Global |
| 20A | 832-862 | 791-821 | Europe, APAC |
| 28A | 703-748 | 758-803 | APAC |
| 66A | 1710-1780 | 2110-2200 | Americas |
| 71A | 663-698 | 617-652 | Americas |

### 5G NR Bands (Selected)
| Band | Uplink (MHz) | Downlink (MHz) | Region |
|------|--------------|----------------|--------|
| n1A | 1920-1980 | 2110-2170 | Global |
| n77A | 3300-4200 | 3300-4200 | Global TDD |
| n78A | 3300-3800 | 3300-3800 | Global TDD |
| n79A | 4400-5000 | 4400-5000 | Asia TDD |
| n257A | 26500-29500 | 26500-29500 | Global mmWave |
| n258A | 24250-27500 | 24250-27500 | Global mmWave |

**Total supported bands**: 50+ (see tool for complete list)

## 🔬 How It Works

### Intermodulation Calculation

The tool calculates intermodulation products using standard RF engineering formulas:

**IM2 Products (2nd Order):**
- 2 × f₁ (2nd harmonic)
- 2 × f₂ (2nd harmonic)
- f₁ + f₂ (sum frequency)
- |f₁ - f₂| (difference frequency)

**IM3 Products (3rd Order):**
- |2 × f₁ - f₂|
- |2 × f₂ - f₁|

### Risk Scoring

Each interference is assigned a risk value:
- **IM2 interference**: 1.0 point
- **IM3 interference**: 0.5 points

**Risk Levels:**
- **Critical**: ≥10.0 (Major IM issues)
- **High**: 5.0-9.9 (Significant IM)
- **Medium**: 1.0-4.9 (Moderate IM)
- **Low**: 0.1-0.9 (Minor IM)
- **Minimal**: 0.0 (No calculated IM)

### Interference Detection

For each IM product, the tool checks if it falls within:
- Any carrier's uplink (UL) band
- Any carrier's downlink (DL) band

If overlap detected → Interference flagged → Risk score accumulated

## 📈 Using the Tool

### Step 1: Upload Data
1. Click "Choose Excel File"
2. Select your ENDC combinations file
3. Wait for processing

### Step 2: Review Results

**Statistics Dashboard:**
- Total combinations analyzed
- Critical/High risk combinations count
- Average risk score

**Carrier Risk Heatmap:**
- Color-coded carriers showing accumulated risk
- Click any carrier for detailed breakdown

**Combinations Table:**
- Ranked by risk score (highest to lowest)
- Shows IM2/IM3 counts
- Main interferences preview
- Click any row for full analysis

### Step 3: Export Results

**Export Carrier Risk Data:**
- Carrier-by-carrier analysis
- Total risk scores
- Appearance frequency
- IM2/IM3 breakdown

**Export Combinations Ranking:**
- Complete ranking of all combinations
- Detailed interference breakdown
- Two sheets: Summary + Detailed

## 🛠️ Technical Details

### Technologies Used
- **HTML5/CSS3**: User interface
- **JavaScript (ES6+)**: Core logic
- **SheetJS (xlsx.js)**: Excel file processing
- **No backend required**: 100% client-side processing

### Browser Compatibility
- Chrome/Edge: ✅ Recommended
- Firefox: ✅ Supported
- Safari: ✅ Supported
- IE11: ❌ Not supported

### Performance
- Processes 100+ combinations in < 2 seconds
- Handles 500+ combinations efficiently
- Client-side processing (no server required)

## ⚠️ Disclaimer

**Educational & Research Tool**

This is a generic RF engineering analysis tool developed for educational and research purposes. It uses publicly available frequency allocation data from ITU and 3GPP specifications, and applies standard intermodulation calculation methods documented in RF engineering textbooks.

**Important Notes:**
- All frequency data is based on publicly available 3GPP specifications
- IM calculations use standard RF engineering formulas
- Tool does not contain proprietary methodologies or client-specific data
- Results are theoretical - real-world performance may vary
- Users are responsible for ensuring compliance with local regulations
- This tool is not a substitute for professional RF engineering analysis

**Data Sources:**
- 3GPP TS 36.101 (LTE frequency bands)
- 3GPP TS 38.101 (5G NR frequency bands)
- ITU frequency allocation tables
- Standard RF engineering textbooks

## 📝 License

MIT License - See LICENSE file for details

## 🤝 Contributing

Contributions welcome! Please feel free to submit issues or pull requests.

### Areas for Contribution:
- Additional frequency bands
- Enhanced visualization
- Additional export formats
- Performance optimizations
- Documentation improvements

## 👤 Author

**Andriy Korobeyko**
- RF Engineering Specialist
- LinkedIn: [andriykorobeyko](https://au.linkedin.com/in/andriykorobeyko/)
- GitHub: [@ak74i](https://github.com/ak74i)

## 📚 References

### 3GPP Specifications
- TS 36.101: User Equipment (UE) radio transmission and reception (LTE)
- TS 38.101: User Equipment (UE) radio transmission and reception (NR)
- TS 37.340: Multi-connectivity overall description

### RF Engineering Resources
- "RF Microelectronics" by Behzad Razavi
- "Intermodulation Distortion in Microwave and Wireless Circuits" by José Carlos Pedro
- ITU Radio Regulations

## 🔄 Version History

### v1.0.0 (2025-02-13)
- Initial release
- Support for 50+ LTE and 5G NR bands
- IM2/IM3 calculation engine
- Interactive carrier heatmap
- Excel export functionality
- Comprehensive documentation

## 📞 Support

For questions or issues:
- Open an issue on GitHub
- Check existing documentation
- Review 3GPP specifications for band details

## 🙏 Acknowledgments

- 3GPP for comprehensive frequency band specifications
- ITU for global frequency allocation data
- RF engineering community for standardized calculation methods
- SheetJS team for excellent Excel processing library

---

**Note**: This tool is for educational and research purposes. Always validate results with professional RF engineering tools and real-world measurements for production deployments.
