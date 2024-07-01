# CHECK AGE OF PEOPLE

## Project Description

This project involves creating a flow that handles HTTP requests at the `/check_age_people` path. The goal is to receive an XML message containing information about individuals, determine if they are adults based on their age, append an "Apto" field with a value of TRUE or FALSE accordingly, and then generate individual XML files for each person with this updated information.

## Requirements

1. **HTTP Request Handling**: The HTTP server must handle POST requests at `/check_age_people` with an XML payload structured as follows:

```xml
<Personas>
    <Persona>
        <Nombre>Maria</Nombre>
        <Apellido>Perez</Apellido>
        <Edad>17</Edad>
        <Movil>657900192</Movil>
    </Persona>
    <Persona>
        <Nombre>Laura</Nombre>
        <Apellido>Jimenez</Apellido>
        <Edad>15</Edad>
        <Movil>617928492</Movil>
    </Persona>
    <Persona>
        <Nombre>Adrian</Nombre>
        <Apellido>Garcia</Apellido>
        <Edad>25</Edad>
        <Movil>637925412</Movil>
    </Persona>
    <Persona>
        <Nombre>Pedro</Nombre>
        <Apellido>Lopez</Apellido>
        <Edad>65</Edad>
        <Movil>607923412</Movil>
    </Persona>
</Personas>
```

2. **Age Verification**: Each person's age must be checked, and an "Apto" field must be added to their respective XML block with the value TRUE if they are 18 or older, and FALSE if they are younger than 18.

3. **Output Files**: Generate XML files named after each person (e.g., "Maria Perez.xml") with the updated XML structure including the "Apto" field.

4. **HTTP Response**: Respond to the request with an XML containing the generated XML blocks in a CDATA field under `<XMLEntrada>` within `<Salida>`. Example response format:

```xml
<Salida>
    <XMLEntrada><![CDATA[
        <Personas>
            <Persona>
                <Nombre>Maria</Nombre>
                <Apellido>Perez</Apellido>
                <Edad>17</Edad>
                <Movil>657900192</Movil>
                <Apto>FALSE</Apto>
            </Persona>
            <Persona>
                <Nombre>Laura</Nombre>
                <Apellido>Jimenez</Apellido>
                <Edad>15</Edad>
                <Movil>617928492</Movil>
                <Apto>FALSE</Apto>
            </Persona>
            <Persona>
                <Nombre>Adrian</Nombre>
                <Apellido>Garcia</Apellido>
                <Edad>25</Edad>
                <Movil>637925412</Movil>
                <Apto>TRUE</Apto>
            </Persona>
            <Persona>
                <Nombre>Pedro</Nombre>
                <Apellido>Lopez</Apellido>
                <Edad>65</Edad>
                <Movil>607923412</Movil>
                <Apto>TRUE</Apto>
            </Persona>
        </Personas>
    ]]></XMLEntrada>
</Salida>
```

## Installation and Execution

1. **Clone the repository**:
    ```sh
    git clone https://github.com/ManuelCobos24/IIB-APP-CONNECT.git
    ```
2. **Navigate to the project directory**:
    ```sh
    cd CHECK_AGE_PEOPLE
    ```
3. **Open the project in your preferred IDE or editor**.

## Usage

1. **Send an HTTP Request**:
    Send an HTTP POST request to `http://HOST:PORT/check_age_people` with the XML payload containing the list of persons.
2. **Receive the Response**:
    The response will contain an XML with the processed data encapsulated in CDATA within `<XMLEntrada>` under `<Salida>`.

## Contributions

Contributions are welcome. Please open an issue or submit a pull request.