# Power BI Calendar Script

## Introduction

This script allows you to create a calendar in Power BI based on your data, which can be extremely useful for analysis. The only thing you need to change is the part between "//", which is taken from a column in a facts table that registers operation dates.

## Usage

Follow these steps to use the script:

1. Open Power Query Editor in Power BI.

2. Select the table that contains the date column you want to use (replace `"Venta"` with your actual table name).

3. Copy and paste the following script into the Advanced Query Editor.

```m
let
    // Replace "Venta" with your actual table name
    fechas = Table.Column(Venta, "Fecha"),
    fecha_min = List.Min(fechas),
    fecha_max = List.Max(fechas),
    dias = Number.From(fecha_max - fecha_min) + 1,
    Fechas_completas = List.Dates(fecha_min, dias, #duration(1, 0, 0, 0))
in
    dias
```


Replace "Venta" with the actual name of your table where you have the date column.

Click "Done" to apply the changes.

### Result
This script will calculate the number of days between the minimum and maximum dates in your selected column and store it in the "dias" variable. You can then use this calendar in your Power BI reports and analysis.
