Summaries display a synopsis of grid data. All summaries can be divided into two groups:

- **Total summaries**       
Calculated by values from the whole grid or a single column; configured in the [totalItems](/Documentation/ApiReference/UI_Widgets/dxDataGrid/Configuration/summary/totalItems/) array.

- **Group summaries**       
Calculated by values from each group; configured in the [groupItems](/Documentation/ApiReference/UI_Widgets/dxDataGrid/Configuration/summary/groupItems/) array.

Each summary item displays a value that is a product of applying an aggregate function to data. The **DataGrid** supports [predefined aggregate functions](/Documentation/Guide/Widgets/DataGrid/Summaries/Predefined_Aggregate_Functions/), such as *"sum"*, *"avg"*, and *"count"*, and allows you to implement a [custom aggregate function](/Documentation/Guide/Widgets/DataGrid/Summaries/Custom_Aggregate_Function/). To specify the applied aggregate function, set the [summaryType](/Documentation/ApiReference/UI_Widgets/dxDataGrid/Configuration/summary/totalItems/#summaryType) option.

The code below configures a group summary that counts grid records in each group:

---
##### jQuery

    <!-- tab: index.js -->
    $(function() {
        $("#dataGrid").dxDataGrid({
            // ...
            summary: {
                groupItems: [{
                    summaryType: "count"
                }]
            },
        });
    });

##### Angular

    <!-- tab: app.component.html -->
    <dx-data-grid ... >
        <!-- ... -->
        <dxo-summary>
            <dxi-group-item
                summaryType="count">
            </dxi-group-item>
        </dxo-summary>
    </dx-data-grid>

##### Vue

    <!-- tab: App.vue -->
    <template>
        <div id="app-container">
            <DxDataGrid ... >
                <!-- ... -->
                <DxSummary>
                    <DxGroupItem
                        summary-type="count"
                    />
                </DxSummary>
            </DxDataGrid>
        </div>
    </template>

    <script>
    import {
        DxDataGrid,
        // ...
        DxSummary,
        DxGroupItem
    } from 'devextreme-vue/data-grid';

    export default {
        components: {
            DxDataGrid,
            // ...
            DxSummary,
            DxGroupItem
        },
        // ...
    }
    </script>

##### React

    <!-- tab: App.js -->
    import React, { useState } from 'react';
    import 'devextreme/dist/css/dx.common.css';
    import 'devextreme/dist/css/dx.light.css';
    import './App.css';

    import {
        DataGrid,
        Column,
        // ...
        Summary,
        GroupItem
    } from 'devextreme-react/data-grid';

    // ...
    function App() {
        // ...
        return (
            <div className="App">
                <DataGrid ... >
                    {/* ... */}
                    <Summary>
                        <GroupItem
                            summaryType="count"
                        />
                    </Summary>
                </DataGrid>
            </div>
        );
    }

    export default App;

---

In the following step, we will add an expandable section that displays information about an employee to each grid row.