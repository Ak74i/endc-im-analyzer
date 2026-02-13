# Changelog

All notable changes to the ENDC IM Analysis Tool will be documented in this file.

## [2.0.0] - 2025-02-13

### Added
- **Enhanced Statistics Dashboard**
  - Total combinations count
  - Average risk score display
  - Percentage breakdowns for each risk level
  - Individual counts for Critical, High, Medium, Low, and Minimal risk
  - Total IM2 and IM3 counts across all combinations
  - More granular metrics with percentages

- **3GPP Release Support (Optional)**
  - Tool now detects and displays 3GPP Release column if present in Excel
  - Release information shown in combinations table
  - Release badges in detailed analysis
  - Fully backward compatible - works without this column

- **Frequency Visualization**
  - Interactive chart showing top 20 carriers by risk score
  - Color-coded bars matching risk levels
  - Risk distribution pie chart
  - Tab-based interface for different visualizations
  - Powered by Chart.js library

- **Enhanced Carrier Analysis**
  - Average risk per combination for each carrier
  - Victim vs Source interference breakdown
  - Frequency information display
  - Top 20 combinations per carrier
  - Detailed metrics grid showing IM2/IM3 as victim/source

- **Improved UI/UX**
  - Larger, more detailed analysis panels
  - Better hover effects on carrier cells
  - Enhanced statistics cards with subtitles
  - Tabbed content for visualizations
  - Better responsive design

### Changed
- Statistics section now shows 8 key metrics (was 4)
- Carrier heatmap cells now show average risk
- Analysis panels are wider (900px vs 800px)
- Enhanced color schemes for better visibility
- Improved export functionality with optional columns

### Technical
- Added Chart.js 3.9.1 for visualizations
- Improved Excel parsing to detect optional columns
- Better error handling for missing data
- Enhanced performance for large datasets

## [1.0.0] - 2025-02-13

### Added
- Initial release
- Support for 50+ LTE and 5G NR bands
- IM2/IM3 calculation engine
- Interactive carrier heatmap
- Excel import/export functionality
- Comprehensive documentation
- MIT License
- Educational disclaimer

### Features
- Real-time intermodulation analysis
- Risk assessment and scoring
- Carrier risk visualization
- Combinations ranking
- Detailed interference breakdown
- Search and filter capabilities

