# CSV-JSON Package

This package was designed in order to read in Comma Separated Value Files (CSV) and output a JavaScript Object Notation (.json) file.

## Usage

### Test CSV Files

In order to test each csv file within the test file, one must replace the path inputted into the csvjs function found at the bottom of the convert.js file with the path of the desired csv file. Then, within a terminal window that is rooted in this project folder, run the "node convert.js" command. This will produce an output.json file that is a conversion of the information within the inputted csv file.

### Unit Testing

To run the unit tests created with the mocha, sinon and chai libraries, the "npm run test" command must be inputted into a terminal window rooted in this project folder.

### Coverage Reports

For more information on the coverage of the unit tests performed, the "npm run coverage" command can be inputted into a terminal window rooted in this project folder. This will make use of the nyc reporting package in order to produce comprehensive coverage reports.

## Versions

node: v16.17.1

npm: 8.15.0

OS: Windows 10 Home Single Language (Version: 21H2, OS Build: 19044.2728)

## Assumptions

- The JSON file should contain an array of objects
- The first line in a CSV file will define the column headers
- Column headers should be used as the JSON property names.
- Each subsequent row in the CSV file should result in an object with corresponding properties to be added to the main array.
- Files may be malformed, best-effort conversion should be attempted and exception handling is left up to the developer.

## Potential Improvements

One potential improvement to this project would be having a script that allows all of the csv files within the test folder to simultaneously be run through the csvjs function, printing json output files for each of them in a separate folder. Although this could have been achieved, it did not seem like what was desired within this project.

Another improvement could have been creating more robust unit tests.
