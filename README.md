# CSV-JSON Package

This package was designed in order to read in Comma Separated Value Files (CSV) and output a JavaScript Object Notation (.json) file.

## Versions

node: v16.17.1

npm: 8.15.0

OS: Windows 10 Home Single Language (Version: 21H2, OS Build: 19044.2728)

## Usage

### Required Packages

The packages required for this package to be run are mocha, sinon, chai, nyc and prompt-sync.

### Test CSV Files

In order to test each csv file within the test file, the following code must be run in a terminal window rooted in this project folder, with the csv name being replaced with the desired csv to be converted:

```bash

npm i

node convert 01_basic.csv

```

If the file name has spaces contained within it, please ensure that you wrap the file name in double quotes.

```bash
node convert "10 space in name.csv"
```

### Unit Testing

To run the unit tests created with the mocha, sinon and chai libraries, the "npm run test" command must be inputted into a terminal window rooted in this project folder.

### Coverage Reports

For more information on the coverage of the unit tests performed, the "npm run coverage" command can be inputted into a terminal window rooted in this project folder. This will make use of the nyc reporting package in order to produce comprehensive coverage reports.

## Conversion Logic

The logic used to convert the csv data in to JSON format was fairly simple. As it is assumed the headers are in the first row of each csv file, the headers are extracted and cleaned from the first row of the array of values. The values under each header are then retrieved by iterating through each other row in the initial array of the csv data, and they are separated via the "|" character rather than a "," in order to make the process of splitting the values easier. Once more cleaning is completed, the function checks if there are multiple values in a column and assigns them a header accordingly. This data is pushed to an array which is then formatted using the JSON.stringify function, and an output.json is produced.

## Assumptions

- The JSON file should contain an array of objects
- The first line in a CSV file will define the column headers
- Column headers should be used as the JSON property names.
- Each subsequent row in the CSV file should result in an object with corresponding properties to be added to the main array.
- Files may be malformed, best-effort conversion should be attempted and exception handling is left up to the developer.

## Potential Improvements

One potential improvement to this project would be having a script that allows all of the csv files within the test folder to simultaneously be run through the csvjs function, printing json output files for each of them in a separate folder. Although this could have been achieved, it did not seem like what was desired within this project.

This package has also not been either linked or published using npm.   

Another improvement could have been creating more robust unit tests.
