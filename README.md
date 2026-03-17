# Smart Data Analyzer

A powerful, browser-based data analysis and machine learning platform that allows users to upload, clean, analyze, and prepare datasets for machine learning—all within a modern web interface.

## Features

### 🔼 Data Upload & Import
- Upload CSV datasets directly or use pre-generated demo data
- Automatic format detection and validation
- Real-time raw data preview

### 🧹 Data Cleaning & Preprocessing
- Remove completely empty rows
- Handle missing values and "ND" entries
- Convert all data to strict numeric formats
- **Min-Max Normalization**: Scale features between 0-1 for ML models

### 📊 Exploratory Data Analysis (EDA)
- **Dashboard Metrics**: Highest value, average, volatility (std deviation), and trend direction
- **Trend Analysis**: Visualize temporal progression of primary and comparative features
- **Value Distribution**: Interactive histograms showing feature frequency
- **Correlation Matrix**: Heatmap displaying feature relationships and correlations

### 🤖 Machine Learning Simulation
Simulate predictions using four algorithmic models:
- **Ridge Regression**: L2 regularization to prevent overfitting
- **Lasso Regression**: L1 regularization for feature selection
- **K-Nearest Neighbors (KNN)**: Local similarity-based predictions
- **Support Vector Regression (SVR)**: Margin-based forecasting

### 🔐 Machine Unlearning (Certified)
- Z-Score anomaly detection for identifying influential outliers
- Removes extreme data points from the model's memory map
- Prevents data poisoning bias and ensures regulatory compliance
- Real-time unlearning statistics

### 📥 Data Export
- Download cleaned CSV datasets
- Export normalized, ML-ready data
- Ready for use with external platforms (Python, TensorFlow, etc.)

## Tech Stack

- **Frontend**: HTML5, TailwindCSS, JavaScript (Vanilla)
- **Charts**: Chart.js for interactive visualizations
- **CSV Parsing**: Papa Parse library
- **Icons**: Lucide Icons
- **Dark Mode**: Built-in light/dark theme toggle

## Getting Started

### Prerequisites
- Any modern web browser (Chrome, Firefox, Safari, Edge)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/bharath506879/smart-data-analyzer.git
   cd smart-data-analyzer
   ```

2. **Open in browser**
   - Simply double-click `index.html` to open locally, or
   - Serve via a local HTTP server:
     ```bash
     python -m http.server 8000
     # or
     npx http-server
     ```

3. **Access the application**
   - Local: `http://localhost:8000` (recommended)
   - Direct file: `file:///path/to/index.html` (limited functionality)

### Deploying to Netlify (Recommended)

1. **Push to GitHub**:
   ```bash
   git push origin main
   ```

2. **Connect to Netlify**:
   - Go to [Netlify](https://netlify.com)
   - Click "New site from Git"
   - Select your GitHub repository
   - Netlify will auto-detect `netlify.toml` configuration
   - Deploy!

3. **Your app is live!** 🚀
   - URL: `https://your-site-name.netlify.app`

### Alternative Deployment Options

**GitHub Pages**:
```bash
# Push to main branch
git push origin main
# Enable Pages in Settings → Pages → Source: Deploy from a branch
```

**Vercel**:
- Import GitHub repo at https://vercel.com
- Auto-deploys on every push

**AWS S3 + CloudFront**:
- Upload `index.html` to S3 bucket
- Configure index document: `index.html`
- Create CloudFront distribution

## Usage Workflow

1. **Upload Data** → Import CSV or load demo dataset
2. **Clean Data** → Remove empty rows, handle missing values, normalize
3. **Analyze (EDA)** → Explore trends, distributions, and correlations
4. **Predict** → Train ML models and simulate forecasting
5. **Export** → Download processing-ready CSV files

## Data Processing Pipeline

### Cleaning Steps
- Drops rows with all empty cells
- Replaces "ND" and empty strings with 0
- Converts all values to numeric format
- Maintains data integrity

### Normalization
- Min-Max scaling compresses values between 0-1
- Formula: `(value - min) / (max - min)`
- Ensures uniform feature weights in ML models

## Deployment Configuration

### Pre-configured for:
- ✅ **Netlify** - Auto-detects `netlify.toml` | Includes security headers & redirects
- ✅ **GitHub Pages** - Works with static hosting
- ✅ **Vercel** - Compatible with import flow
- ✅ **Apache/Traditional Servers** - `.htaccess` handles routing
- ✅ **Nginx & other servers** - Serve as static site

### Key Configuration Files:
- `netlify.toml` - Netlify deployment & security headers
- `_redirects` - URL routing for Netlify
- `.htaccess` - Apache server routing & caching
- `package.json` - Project metadata

### No Special Requirements:
- No backend server needed
- No database required
- Fully client-side processing (100% private)
- Works offline after initial load
- All data stays in the browser

## Browser Compatibility

- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

## Files Structure

```
smart-data-analyzer/
├── index.html         # Main application (entry point)
├── analyzer.html      # Alternative access (same content as index.html)
├── netlify.toml       # Netlify deployment configuration
├── _redirects         # Netlify URL routing rules
├── .htaccess          # Apache server routing rules
├── package.json       # Project metadata and dependencies
├── README.md          # This file
├── LICENSE            # MIT License
└── .gitignore         # Git ignore rules
```

## Troubleshooting

### 404 Error on Netlify/Deployment
**Problem**: "Page not found" after deployment

**Solution**: 
- ✅ The application now uses `index.html` as the entry point (automatically served)
- ✅ `netlify.toml` has routing rules configured
- ✅ `_redirects` file ensures all routes redirect to index.html
- Simply push the updated code:
  ```bash
  git add .
  git commit -m "Fix: Update deployment configuration"
  git push origin main
  ```
- Netlify will automatically redeploy with the correct routing

### Application Not Loading
- Clear browser cache (Ctrl+Shift+Delete)
- Try incognito/private window
- Check browser console (F12) for errors
- Ensure JavaScript is enabled

### CSV Upload Not Working
- Verify CSV file is properly formatted
- Check file size (should be < 10MB)
- Try with demo data first to test pipeline
- Check browser console for parsing errors

### Z-Score Anomaly Detection
```
Z-Score = |value - mean| / standard_deviation
If Z-Score > 2.0 → data point is considered an anomaly
```

### Min-Max Normalization
```
normalized = (value - min) / (max - min)
Result range: [0, 1]
```

### Correlation Calculation
```
Uses Pearson correlation coefficient
Range: [-1, 1]
- 1: Strong positive correlation
- 0: No correlation
-1: Strong negative correlation
```

## Performance Considerations

- Handles up to 10,000+ rows efficiently
- Real-time chart updates with Chart.js
- Optimized rendering with lazy-loading
- Dark mode reduces eye strain for extended use

## Privacy & Security

- **100% Client-side Processing**: No data sent to servers
- **No Analytics**: No tracking or telemetry
- **No Cookies**: Fully private analysis
- **Browser-based**: Works offline after first load

## Future Enhancements

- [ ] Export predictions as CSV
- [ ] Advanced statistical tests (ANOVA, Chi-square)
- [ ] Time series forecasting (ARIMA)
- [ ] Outlier removal utilities
- [ ] Batch processing for multiple files
- [ ] Advanced visualization options

## Contributing

Contributions are welcome! Please:
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author

**Bharath** - [GitHub Profile](https://github.com/bharath506879)

## Support

For issues, questions, or suggestions:
- Open an [GitHub Issue](https://github.com/bharath506879/smart-data-analyzer/issues)
- Contact via GitHub

## Acknowledgments

- Chart.js for data visualization
- Papa Parse for CSV handling
- TailwindCSS for styling
- Lucide Icons for UI icons

---

**Made with ❤️ for data enthusiasts and ML practitioners**
