# opencsv
opencsv is a very simple csv (comma-separated values) parser library for Java. 

## Quick start
- Download jar file and add it into class path.

- Define format of CSV file
```java
import au.com.bytecode.opencsv.CSV;
CSV csv = CSV .separator(',') // delimiter of fields .quote('"') // quote character .create(); // new instance is immutable 
```

Write file 
```java 
import au.com.bytecode.opencsv.CSVWriteProc;
csv.write("example.csv", new CSVWriteProc() { 
public void process(CSVWriter out) {
out.writeNext("Column1", "Column2"); out.writeNext("Value1", "Value2"); 
} 
}); 
```

Read file 
```java
import au.com.bytecode.opencsv.CSVReadProc; import java.util.Arrays;
csv.read("example.csv", new CSVReadProc() {
public void procRow(int rowIndex, String... values) {
System.out.println(rowIndex + ": " + Arrays.asList(values));
}
}); 
```

### The another csv util http://commons.apache.org/proper/commons-csv/
