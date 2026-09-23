# Create a Tornado Chart in Blazor Charts

## Overview

This sample demonstrates how to create a tornado chart using Syncfusion [Blazor Charts](https://www.syncfusion.com/blazor-components/blazor-charts). The implementation renders mirrored horizontal bars by combining positive and negative values in stacked bar series, allowing easy comparison between two related data groups.

The sample uses separate series for male and female values and customizes axis label rendering so that negative values are displayed as positive labels. Data labels are enabled for both series to provide clear value representation directly within the chart.

## Key Features

- Uses the `SfChart` component to render the chart.
- Creates a tornado chart using `ChartSeriesType.StackingBar`.
- Binds chart data through the `DataSource` property.
- Maps category values using `XName="Height"`.
- Maps numerical values using `YName`.
- Uses positive values for the Female series and negative values for the Male series to create the mirrored tornado effect.
- Displays series data labels using:
  - `ChartMarker`
  - `ChartDataLabel`
  - `ChartDataLabelFont`
- Handles axis label customization with:
  - `ChartEvents`
  - `OnAxisLabelRender`
  - `AxisLabelRenderEventArgs`
- Removes the negative sign from displayed axis labels by modifying `AxisLabelRenderEventArgs.Text`.
- Uses a strongly typed `StackedBarChartData` class for chart data binding.
- Configures chart axis range through `ChartPrimaryXAxis`.
- Displays custom label text using the `Name` property of `ChartDataLabel`.

## Prerequisites

- [Visual Studio 2022](https://visualstudio.microsoft.com/vs/) or [Visual Studio Code](https://code.visualstudio.com/)
- [.NET SDK](https://dotnet.microsoft.com/en-us/download/dotnet) compatible with the project's target framework

## How to Run the Project

**Visual Studio 2022**

1. Clone or download this repository.
2. Open the project file inside the `Tornado Chart` folder.
3. Restore NuGet packages.
4. Build the project.
5. Run the application using `Ctrl+F5`.

**Visual Studio Code**

1. Clone or download this repository.
2. Open the repository folder in Visual Studio Code.
3. Open the integrated terminal.
4. Navigate to the project folder:

```bash
cd "Tornado Chart"
```

5. Restore required packages:

```bash
dotnet restore
```

6. Run the application:

```bash
dotnet run
```

7. Open the local application URL displayed in the terminal after the project starts.

## Project Structure

- `Pages/Index.razor` - Contains the chart implementation, stacked bar series configuration, chart data model, sample data source, and axis label rendering logic.

## Support and Feedback

- For general product questions, visit the [Syncfusion Community Forum](https://www.syncfusion.com/forums) or [Syncfusion Support](https://www.syncfusion.com/support).
- To report an issue specific to this sample, open a GitHub issue in this repository.
- Refer to the official Blazor Chart documentation: https://help.syncfusion.com/chart-sdk/blazor/charts/getting-started

## License

This is a Syncfusion sample project provided to demonstrate product usage. Review the [Syncfusion license terms](https://www.syncfusion.com/sales/pricing?category=ui-components) before using Syncfusion components in your own applications.