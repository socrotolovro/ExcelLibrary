# ExcelLibrary

The aim of this project is to simplify reading from and writing to Excel workbooks (.xlsx). Here's an example to get you started:

    Workbook workbook = new Workbook();
    workbook.Open("Book1.xlsx");
    Sheet sheet = workbook.Sheet("Sheet1");
    Row row = sheet.Row(2);
    Cell cell = row.Cell(3);
    string text = cell.Value;

See the wiki for more examples.

## Features

* No dependencies except .NET Framework 4.5. Easy to include in other solutions.
* Built and extendable with LINQ. Most collections in the library (e.g. `Workbook.Sheets` or `Row.Cells`) is of type `IEnumerable<T>`, which  allows you to use LINQ queries to find exactly what you need.
* Distinguishes values of different data types (using the `Cell.Type` property).
* Respects the visibility of sheets, rows and columns. Set the `IncludeHidden` option to `true`to return hidden objects.
* Well-documented. A software library is only as useful as its documentation.

## Limitations

The following things have been considered outside the scope of the project:

* All file formats except `.xslx`.
* Formulas
* Formatting properties

Also, the library will not create new workbooks _per se_, but this can be achieved by including a template workbook in your project and copy it whenever you need to create a workbook.
