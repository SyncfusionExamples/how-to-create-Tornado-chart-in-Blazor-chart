# how-to-create-Tornado-chart-in-Blazor-chart

This article explains how to create tornado chart in blazor chart component.

**Creating Tornado chart using Stacked Bar**

The [Blazor Chart](https://www.syncfusion.com/blazor-components/blazor-charts) provides the support to display data points as Tornado chart by using [Stacked Bar](https://www.syncfusion.com/blazor-components/blazor-charts/chart-types/stacked-bar-chart) chart by providing Positive and negative values for Y to render as Tornado Chart.

The Negative stack axis label can be made positive by using [OnAxisLabelRender](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartEvents.html#Syncfusion_Blazor_Charts_ChartEvents_OnAxisLabelRender) event. This event triggers before the axis label render.

The following properties are available in the [AxisLabelRenderEventArgs](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AxisLabelRenderEventArgs.html).

•	[LabelStyle](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AxisLabelRenderEventArgs.html#Syncfusion_Blazor_Charts_AxisLabelRenderEventArgs_LabelStyle) – Specifies the font information of the axis label.

•	[Text](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AxisLabelRenderEventArgs.html#Syncfusion_Blazor_Charts_AxisLabelRenderEventArgs_Text) – Specifies the text to be displayed in the axis label.

•	[Value](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AxisLabelRenderEventArgs.html#Syncfusion_Blazor_Charts_AxisLabelRenderEventArgs_Value) – Specifies the value of the axis label.

The below code example illustrates this.

**C#**

```cshtml

@using Syncfusion.Blazor.Charts

<SfChart>

    <ChartPrimaryXAxis Minimum="4.4" Interval="0.2"></ChartPrimaryXAxis>

    <ChartEvents OnAxisLabelRender="AxisLabelRenderEvent"></ChartEvents>

    <ChartSeriesCollection>
        <ChartSeries ColumnWidth="0.5" DataSource="@ChartPoints" XName="Height" YName="Female" Name="Female" Type="ChartSeriesType.StackingBar">
            <ChartMarker>
                <ChartDataLabel Visible="true" Position="LabelPosition.Top" Name="Female_Text">
                    <ChartDataLabelFont FontWeight="600"></ChartDataLabelFont>
                </ChartDataLabel>
            </ChartMarker>
        </ChartSeries>
        
        <ChartSeries ColumnWidth="0.5" DataSource="@ChartPoints" XName="Height" YName="Male" Name="Male" Type="ChartSeriesType.StackingBar">
            <ChartMarker>
                <ChartDataLabel Visible="true" Name="Text" Position="LabelPosition.Top">
                    <ChartDataLabelFont FontWeight="600"></ChartDataLabelFont>
                </ChartDataLabel>
            </ChartMarker>
        </ChartSeries>
    </ChartSeriesCollection>

</SfChart>


@code {

    public class StackedBarChartData
    {
        public string Height { get; set; }
        public double Female { get; set; }
        public double Male { get; set; }
        public string Text { get; set; }
        public string Female_Text { get; set; }
    }

    public string Width { get; set; } = "90%";

    public List<StackedBarChartData> ChartPoints { get; set; } = new List<StackedBarChartData>
    {
        new StackedBarChartData { Height = "4.5", Female = 31, Male = -31, Text = "31 KG", Female_Text = "31 KG" },
        new StackedBarChartData { Height = "4.8", Female = 37, Male = -39, Text = "39 KG", Female_Text = "37 KG" },
        new StackedBarChartData { Height = "5.1", Female = 49, Male = -52, Text = "52 KG", Female_Text = "49 KG" },
        new StackedBarChartData { Height = "5.4", Female = 57, Male = -64, Text = "64 KG", Female_Text = "57 KG" },
        new StackedBarChartData { Height = "5.7", Female = 63, Male = -70, Text = "70 KG", Female_Text = "63 KG" },
        new StackedBarChartData { Height = "6", Female = 69, Male = -74, Text = "74 KG", Female_Text = "69 KG" }
    };   
    
    private void AxisLabelRenderEvent(AxisLabelRenderEventArgs args)
    {
        args.Text = args.Text.Contains("-") ? (args.Text.Replace("-", "")) : args.Text;
    }

}

```


The following screenshot illustrate the output of the above code snippet.

**Output:**
 
![](/tornado-chart.png)


**Conclusion**

I hope you enjoyed learning how to display Tornado chart using Blazor Chart Component.

You can refer to our [Blazor Chart feature tour](https://www.syncfusion.com/blazor-components/blazor-charts) page to know about its other groundbreaking feature representations and [documentation](https://blazor.syncfusion.com/documentation/chart/getting-started), and how to quickly get started for configuration specifications. You can also explore our [Blazor Chart example](https://blazor.syncfusion.com/demos/chart/line?theme=bootstrap5) to understand how to create and manipulate data.

For current customers, you can check out our components from the [License and Downloads](https://www.syncfusion.com/sales/teamlicense) page. If you are new to Syncfusion, you can try our 30-day [free trial](https://www.syncfusion.com/downloads/blazor) to check out our other controls.

If you have any queries or require clarifications, please let us know in the comments section below. You can also contact us through our [support forums](https://www.syncfusion.com/forums), [support portal](https://support.syncfusion.com/create), or [feedback portal](https://www.syncfusion.com/feedback/blazor-components?control=charts). We are always happy to assist you!




