# JavaFX FXML Calculator

A small desktop calculator that demonstrates how to connect a JavaFX user interface defined in FXML to a Java controller.

The application accepts two numbers and supports addition, subtraction, multiplication, and division. The result is displayed in a third text field.

## Technologies

- Java
- JavaFX Controls and FXML 11.0.2
- Maven
- Java Platform Module System (JPMS)

## Project structure

```text
src/main/java/
├── module_calc.java
└── com/calculator/calculator/
    ├── Calculator.java
    └── FXMLDocumentController.java

src/main/resources/com/calculator/calculator/
└── FXMLDocument.fxml
```

- `Calculator.java` starts the JavaFX application and loads the FXML layout.
- `FXMLDocumentController.java` handles the four arithmetic actions.
- `FXMLDocument.fxml` defines the window, input fields, result field, labels, and buttons.
- `module_calc.java` declares the JavaFX module requirements.

## Requirements

- A Java Development Kit (JDK)
- Apache Maven

The repository does not currently pin a JDK or Maven version. Its JavaFX dependencies are version 11.0.2.

## Run locally

Clone the repository and enter its directory:

```bash
git clone https://github.com/T4N3V/FXML_calc.git
cd FXML_calc
```

The JavaFX Maven plugin is configured with the application entry point, so the intended run command is:

```bash
mvn clean javafx:run
```

> Note: the current `pom.xml` sets the Maven compiler `source` and `target` values to `0`. Modern Maven/JDK combinations may reject that configuration. Correcting the compiler level is a separate code/build change and is intentionally outside this documentation-only update.

## Usage

1. Enter a numeric value in **Number 1**.
2. Enter a numeric value in **Number 2**.
3. Select **Add**, **Subtract**, **Multiply**, or **Divide**.
4. Read the calculated value in **Result**.

## Screenshot

No screenshot asset is currently stored in the repository. A real application screenshot can be added here after the project is run successfully; no placeholder image is presented as actual output.

## Testing

The Maven file declares JUnit 5 dependencies, but the repository currently contains no test sources. After tests are added, they can be run with:

```bash
mvn test
```

## Current limitations

- Input is parsed directly as `double`; non-numeric text is not handled in the UI.
- Division by zero follows Java floating-point behavior and is not reported with a custom message.
- The result field remains editable.
- There are no automated tests.
- The compiler level in `pom.xml` needs to be corrected before command-line builds are portable across modern JDKs.

## Repository status

This is a compact educational JavaFX example rather than a packaged production application. The repository includes source code, the FXML layout, Maven configuration, and generated files under `target/`; it does not currently include releases, packaged installers, automated tests, or screenshots.
