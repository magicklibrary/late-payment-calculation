# Late Payment Calculator & Excel Generator

A web-based tool accessed via: https://magicklibrary.github.io/late-payment-calculation/ for calculating compounded interest and late fees on delinquent invoices, with automatic Excel export functionality. Perfect for Accounts Receivable teams to quickly generate supplemental invoices for outstanding balances.


## Features

- **Multi-Invoice Processing** - Handle multiple invoices in a single session
- **Automated Calculations** - Real-time compound interest and late fee computation
- **Excel Export** - One-click download of properly formatted .xlsx files
- **No Backend Required** - Runs entirely in the browser
- **Mobile Responsive** - Works on desktop, tablet, and mobile devices
- **Zero Configuration** - No API keys, no database, no installation needed

##  Calculation Rules

The calculator follows these financial rules based on standard payment terms:

### Interest Calculation
- **Rate**: 1.5% per month (18% annually)
- **Compounding**: Monthly
- **Formula**: `Principal × (1.015)^(Days Delinquent ÷ 30) - Principal`

### Late Fee
- **Amount**: $75.00 (one-time charge)
- **Trigger**: Applied when Days Delinquent > 45 days
- **Application**: Added to the total balance in addition to interest

### Example Calculation
```
Invoice Amount: $10,000.00
Days Delinquent: 60 days (beyond payment terms)

Calculation:
- Months Delinquent: 60 ÷ 30 = 2 months
- Interest: $10,000 × (1.015^2 - 1) = $302.25
- Late Fee: $75.00 (applies because 60 > 45)
- Total Amount Due: $10,000 + $302.25 + $75.00 = $10,377.25
```

## How to Use

### For End Users (AR Team)

1. **Open the Application**
   - Navigate to the deployed GitHub Pages URL
   - Or open `https://magicklibrary.github.io/late-payment-calculation/` locally in your browser

2. **Enter Invoice Details**
   - Client Name
   - Invoice Number
   - Invoice Date
   - Payment Terms (Same Day, 10 days, 14 days, 30 days, 45 days, 60 days)
   - Invoice Amount (principal balance)
   - Days Delinquent (only days past the payment terms)

3. **Review Calculations**
   - Interest accrued displays automatically
   - Late fee shows if applicable
   - Total amount due updates in real-time

4. **Add More Invoices** (Optional)
   - Click "Add Another Invoice" to process multiple invoices
   - Each invoice calculates independently

5. **Export to Excel**
   - Click the "Export to Excel" button
   - Download the generated `.xlsx` file
   - Use the data to draft additional invoices

### Important Note on "Days Delinquent"
Enter **only** the number of days **beyond** the agreed payment terms. 

**Example**: If payment terms are "14 days" and the invoice is 50 days old:
- Days Delinquent = 50 - 14 = **36 days**

## Generated Excel Format

The exported spreadsheet includes these columns:

| Column | Description |
|--------|-------------|
| Client Name | Customer/client identifier |
| Invoice Number | Original invoice reference |
| Invoice Date | Date invoice was issued |
| Payment Terms | Agreed payment period |
| Invoice Amount | Principal balance (USD) |
| Days Delinquent | Days past payment terms |
| Interest Accrued | Calculated compound interest (USD) |
| Late Fee | $75 or $0 based on delinquency |
| Total Amount Due | Sum of all charges (USD) |

All currency values are formatted in USD with proper number formatting.

## Installation & Deployment

### Quick Start (Local Use)

1. Clone the repository:
```bash
git clone https://github.com/yourusername/late-payment-calculator.git
cd late-payment-calculator
```

2. Open `index.html` in your browser:
```bash
# On macOS
open index.html

# On Windows
start index.html

# On Linux
xdg-open index.html
```

That's it! No installation or dependencies required.

### Deploy to GitHub Pages

1. **Enable GitHub Pages**:
   - Go to your repository Settings
   - Navigate to "Pages" section
   - Under "Source", select "main" branch
   - Click "Save"

2. **Access Your App**:
   - Your app will be available at: `https://yourusername.github.io/repository-name/`
   - Share this URL with your AR team

### Deploy to Other Platforms

**Netlify**:
1. Drag and drop your repository folder to Netlify
2. Your app is live instantly

**Vercel**:
```bash
vercel deploy
```

**Any Web Server**:
Simply upload `index.html` to any web hosting service.

## Security & Privacy

- **No Data Storage**: All calculations happen in the browser
- **No Server Communication**: Zero data transmission to external servers
- **No API Keys**: No credentials or secrets in the code
- **Client-Side Only**: Complete privacy for sensitive financial data
- **No Cookies**: No tracking or analytics

This application is completely safe to deploy publicly as it contains no sensitive information and performs all operations locally in the user's browser.

## Technical Stack

- **React** - UI framework
- **Lucide React** - Icon library
- **SheetJS (xlsx)** - Excel file generation
- **Tailwind CSS** - Styling
- **Pure JavaScript** - No build process required

## Legal Compliance

This calculator implements late payment terms that comply with common commercial practices. However:

- **Consult Legal Counsel**: Verify these terms comply with your jurisdiction
- **Contract Terms**: Ensure your contracts explicitly state these penalty terms
- **State/Local Laws**: Some jurisdictions limit interest rates and late fees
- **Disclosure**: Late fees and interest rates must be disclosed to customers

The Terms and Conditions provided should be reviewed by your legal team before use.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request


## Known Issues

None currently. Please report issues via GitHub Issues.

## Future Enhancements

Potential features for future versions:
- [ ] Custom interest rate configuration
- [ ] Multiple late fee tiers
- [ ] PDF export option
- [ ] Invoice history/tracking
- [ ] Email integration
- [ ] Multi-currency support
- [ ] Custom payment term definitions
- [ ] Batch import from CSV

## Support

For questions or issues:
- Open an issue on GitHub
- Contact your organization's AR team lead

## Acknowledgments

- Built with React and modern web technologies
- Uses SheetJS for Excel generation
- Styled with Tailwind CSS

---

**Note**: This tool is provided as-is for financial calculation purposes. Always verify calculations with your accounting team and ensure compliance with applicable laws and regulations.
