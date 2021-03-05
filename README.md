# How to set StackedHeaders when AutoGenerateColumn as true in WPF DataGrid(SfDataGrid)?
# About the sample

This sample show cases how to set StackedHeaders when AutoGenerateColumn as true in [WPF DataGrid](https://www.syncfusion.com/wpf-ui-controls/datagrid) (SfDataGrid)?

You can’t add the [StackedHeaderRows](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.StackedHeaderRows.html) in [WPF DataGrid](https://www.syncfusion.com/wpf-ui-controls/datagrid) (SfDataGrid) while generating the column automatically. But you can achieve this by using [AutoGeneratingColumn](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~AutoGeneratingColumn_EV.html) event

```c#
private void Sfgrid_AutoGeneratingColumn(object sender, Syncfusion.UI.Xaml.Grid.AutoGeneratingColumnArgs e)
{
    if (sfgrid.StackedHeaderRows.Count == 0)
    {
        var gridSHRow = new Syncfusion.UI.Xaml.Grid.StackedHeaderRow();
        gridSHRow.StackedColumns.Add(new Syncfusion.UI.Xaml.Grid.StackedColumn { ChildColumns = "OrderID,CustomerID", HeaderText = "ID" });
        gridSHRow.StackedColumns.Add(new Syncfusion.UI.Xaml.Grid.StackedColumn { ChildColumns = "ProductName,OrderDate,Quantity,UnitPrice", HeaderText = "Order Details" });
        gridSHRow.StackedColumns.Add(new Syncfusion.UI.Xaml.Grid.StackedColumn { ChildColumns = "DeliveryDelay,ShipAddress,ContactNumber", HeaderText = "Delivery Details" });
        sfgrid.StackedHeaderRows.Add(gridSHRow);
    }
}   
```
## Requirements to run the demo
 Visual Studio 2015 and above versions
