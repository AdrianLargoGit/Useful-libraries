# 📊 TextTable

> A lightweight Java library for printing beautiful, colored, and aligned tables in the console.

---

## ✨ Features

* ✅ Auto-sized columns
* ✅ Custom alignment (left, center, right)
* ✅ ANSI colors (headers, custom styles)
* ✅ Optional automatic `ID` column
* ✅ Replace values by column index or name
* ✅ Fluent and intuitive API
* ✅ Zero dependencies – pure Java
* More soon

---

## 📆 Installation

Add the JAR manually or publish to your Maven/Gradle repository.

<details>
<summary><strong>Gradle</strong></summary>

```
dependencies:
  implementation 'com.adrianlargogit:texttable:1.0.0'
```

</details>

<details>
<summary><strong>Maven</strong></summary>

```xml
<dependency>
  <groupId>com.adrianlargogit</groupId>
  <artifactId>texttable</artifactId>
  <version>1.0.0</version>
</dependency>
```

</details>

---

## 🚀 Quick Start

```java
import com.adrianlargogit.texttable.*;

public class Main
{
  public static void main(String[] args)
  {
    Table table = new Table("Name", "Age", "Country")
        .withIdColumn(true); // Adds an auto-incrementing ID column

    table.setAlignment(1, Align.LEFT);
    table.setAlignment(2, Align.CENTER);
    table.setAlignment(3, Align.RIGHT);

    table.addRow(new Row().add("Alice").add(30).add("USA"));
    table.addRow(new Row().add("Bob").add(28).add("Spain"));
    table.addRow(new Row().add("Charlie").add(25).add("UK"));

    table.replaceCell(1, "Country", "Germany");  // By header
    table.replaceCell(2, 1, "Carlos");           // By column index

    table.print();
  }
}
```

---

## 📄 Output

```
+----+--------+-----+---------+
| ID |  Name  | Age | Country |
+----+--------+-----+---------+
|  1 | Alice  |  30 |     USA |
|  2 | Bob    |  28 | Germany |
|  3 | Carlos |  25 |      UK |
+----+--------+-----+---------+
```

> ✅ Headers are colored and bolded using ANSI codes.
> ✍ Replace any cell using column name or index.

---

## 🧠 API Reference

### `Table(boolean include, String... headers)`

Creates a new table with the specified headers. Includes a column "ID" at the beginning. Defaults to `false`.

### `addRow(Row row)`

Adds a new row of data. Row length must match number of headers.

### `setAlignment(int columnIndex, Align align)`

Aligns a column: `LEFT`, `CENTER`, or `RIGHT`.

### `replaceCell(int rowIndex, int columnIndex, String value)`

Replaces the content of a cell by column index.

### `replaceCell(int rowIndex, String headerName, String value)`

Replaces the content of a cell by header name.

### `print()`

Prints the formatted table to the console.

---

## 🎨 ANSI Colors

TextTable uses basic ANSI codes to color terminal output.
This works in most IDEs, Unix shells, and Windows Terminal (PowerShell 7+).

You can customize colors via `ANSI.java`.

---

## 🛠 Utilities

### Enum: `Align`

```java
Align.LEFT
Align.CENTER
Align.RIGHT
```

---

## ✅ Requirements

* Java 8+
* No external dependencies

---

## 📂 Project Structure

```
com/adrianlargogit/texttable/
├── Table.java
├── Row.java
├── Align.java
└── ANSI.java
```

---

## 🧪 Test It Locally

```bash
javac -d out src/com/adrianlargogit/texttable/*.java
java -cp out com.adrianlargogit.texttable.Main
```

---

## 📢 Roadmap Ideas

* [ ] Export to CSV/Markdown
* [ ] Style themes (minimal, boxed, bold)
* [ ] Column width limit
* [ ] Conditional formatting

---

## 📄 License

MIT License © 2025 \[AdrianLargoGit](https://github.com/AdrianLargoGit).

## 💡 Author

Made with ☕ by [AdrianLargoGit](https://github.com/AdrianLargoGit).

Feel free to connect or follow for more tools and open-source work.
