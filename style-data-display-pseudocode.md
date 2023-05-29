## **To change the styling of a bar graph in an Android native application written in Java using MPAndroidChart.**

### **1. Add the MPAndroidChart library to your project by adding the following dependency to your app-level ‘build.gradle’ file:**

# **GRADLE:**

    implementation 'com.github.PhilJay:MPAndroidChart:v3.1.0'

### **2. In your XML layout file, add a ‘BarChart’ view:**

# **XML:**

    <com.github.mikephil.charting.charts.BarChart
        android:id="@+id/barChart"
        android:layout_width="match_parent"
        android:layout_height="match_parent" />

### **3. In your Java code, initialize the ‘BarChart’ and customize its styling:**

# **JAVA:**

    import com.github.mikephil.charting.charts.BarChart;
    import com.github.mikephil.charting.components.XAxis;
    import com.github.mikephil.charting.components.YAxis;
    import com.github.mikephil.charting.data.BarData;
    import com.github.mikephil.charting.data.BarDataSet;
    import com.github.mikephil.charting.data.BarEntry;

    // ...

    BarChart barChart = findViewById(R.id.barChart);

    // Customize X-axis
    XAxis xAxis = barChart.getXAxis();
    xAxis.setPosition(XAxis.XAxisPosition.BOTTOM); // Set X-axis position at the bottom

    // Customize Y-axis
    YAxis yAxisLeft = barChart.getAxisLeft();
    yAxisLeft.setAxisMinimum(0f); // Set the minimum value of Y-axis
    yAxisLeft.setDrawGridLines(false); // Hide Y-axis grid lines

    YAxis yAxisRight = barChart.getAxisRight();
    yAxisRight.setEnabled(false); // Disable the right Y-axis

    // Customize bar data and set it to the chart
    List<BarEntry> entries = new ArrayList<>();
    entries.add(new BarEntry(0f, 4f));
    entries.add(new BarEntry(1f, 2f));
    entries.add(new BarEntry(2f, 6f));
    entries.add(new BarEntry(3f, 8f));

    BarDataSet dataSet = new BarDataSet(entries, "Bar Data");
    dataSet.setColor(Color.BLUE); // Set bar color

    BarData barData = new BarData(dataSet);
    barData.setBarWidth(0.9f); // Set the width of the bars

    barChart.setData(barData);
    barChart.invalidate(); // Refresh the chart
 

### **4. You can further customize the bar graph by modifying additional properties of the ‘BarChart’, and ‘BarData’ objects. MPAndroidChart provides many options control the appearance, such as bar colors, bar width, bar labels, grid lines, legends, animations, and more. Refer to the MPAndroidChart documentation for more details on available customization options.**

Remember to handle any necessary permissions and imports as required for your project.

By following these steps, you should be able to change the styling of a bar graph in your Android native application using Java.
