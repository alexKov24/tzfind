# Teudat Zeut Validator

A lightweight, web-based tool for validating Israeli ID numbers (Teudat Zeut) and suggesting possible corrections for invalid numbers. Built with vanilla JavaScript and styled with Tailwind CSS.

![Teudat Zeut Validator Screenshot](Xnapper-2024-11-30-11.55.35.png)

## Features

- Instantly validate 9-digit Israeli ID numbers
- Real-time input validation and formatting
- Generate possible corrections for invalid IDs:
  - Single-digit corrections
  - Double-digit corrections
- Clear visual feedback on validation status
- Mobile-responsive design
- No server-side dependencies

## How It Works

The validator implements the official Israeli ID validation algorithm:

1. Converts the ID to a 9-digit number (padding with leading zeros if necessary)
2. Takes the first 8 digits as the base number
3. Applies the check digit algorithm:
   - Multiplies even-positioned digits by 2
   - If result > 9, subtracts 9
   - Sums all digits
   - Calculates check digit as `(10 - sum % 10) % 10`
4. Compares calculated check digit with the 9th digit of the ID

For invalid IDs, the tool generates possible corrections by:
- Testing single-digit changes in all positions
- Testing combinations of two-digit changes
- Sorting suggestions by number of changes required and numeric proximity

## Usage

1. Open the HTML file in a web browser
2. Enter a 9-digit Teudat Zeut number
3. Click "Analyze" or press Enter
4. View validation result and possible corrections if invalid

## Installation

Simply download the HTML file and open it in a web browser. No installation or build process required.

```bash
# Clone the repository
git clone https://github.com/alexKov24/tzfind.git

# Navigate to the project directory
cd tzfind

# Open index.html in your browser
```

## Dependencies

- Tailwind CSS (2.2.19) - loaded via CDN

## Browser Support

Works in all modern browsers that support:
- ES6+ JavaScript
- Flexbox
- CSS Grid
- Modern DOM APIs

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- Israeli Ministry of Interior for the ID validation algorithm specification
- Tailwind CSS team for the excellent CSS framework
