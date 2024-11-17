# Crazy Musicians API

This project demonstrates a simple ASP.NET Core Web API for managing a list of musicians with unique and funny traits. The API supports basic CRUD (Create, Read, Update, Delete) operations and includes features like routing, validation, and querying.

## Project Overview

### API Features
- **GET**: Retrieve all musicians or a specific musician by ID.
- **POST**: Add a new musician to the list.
- **PATCH**: Update the `FunFact` of a musician.
- **PUT**: Replace all properties of a musician.
- **DELETE**: Mark a musician as deleted without removing them from the list.

### Data Model

#### Musician Class
The `Musician` class represents the data model for a musician.

| Property      | Type      | Description                        |
|---------------|-----------|------------------------------------|
| `Id`          | `int`     | Unique identifier for the musician. |
| `Name`        | `string`  | Name of the musician.              |
| `Profession`  | `string`  | The musician's profession.         |
| `FunFact`     | `string`  | A fun fact about the musician.     |
| `IsDeleted`   | `bool`    | Marks the musician as deleted.     |

### Example Data

#### Initial Musicians List
| ID  | Name           | Profession           | FunFact                                          |
|-----|----------------|----------------------|-------------------------------------------------|
| 1   | Ahmet Çalgı    | Ünlü Çalgı Çalar     | Her zaman yanlış nota çalar, ama çok eğlenceli  |
| 2   | Zeynep Melodi  | Popüler Melodi Yazarı| Şarkıları yanlış anlaşılır ama çok popüler      |
| 3   | Cemil Akor     | Çılgın Akorist       | Akorları sık değiştirir ama şaşırtıcı derecede yetenekli |
| ... | ...            | ...                  | ...                                             |

### API Endpoints

#### `GET /api/musicians`
Retrieve the list of all musicians.

#### `GET /api/musicians/{id}`
Retrieve a specific musician by ID. Requires a valid `id` parameter.

#### `POST /api/musicians`
Add a new musician. Requires a JSON body with the following properties:
- `Name` (string)
- `Profession` (string)
- `FunFact` (string)

#### `PATCH /api/musicians/{id}`
Update the `FunFact` of a musician. Requires the `id` of the musician and a JSON body with the updated `FunFact`.

#### `PUT /api/musicians/{id}`
Replace all properties of a musician. Requires a valid `id` and a JSON body with the following properties:
- `Id` (int)
- `Name` (string)
- `Profession` (string)
- `FunFact` (string)
- `IsDeleted` (bool)

#### `DELETE /api/musicians/{id}`
Mark a musician as deleted. Requires a valid `id`.

---

## Prerequisites

- **.NET SDK**: Version 6.0 or later.
- **Code Editor**: Visual Studio, Visual Studio Code, or Rider.

## Running the Project

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/crazy-musicians.git
   ```
2. Open the solution in Visual Studio or your preferred editor.
3. Restore NuGet packages:
   ```bash
   dotnet restore
   ```
4. Run the project:
   ```bash
   dotnet run
   ```

## Validation
- The API includes validation for ID inputs to ensure valid integers.
- Endpoints like `POST` and `PUT` check for valid JSON data.

---

## Example Usage

### Get All Musicians
**Request**:
```http
GET /api/musicians
```

**Response**:
```json
[
    {
        "id": 1,
        "name": "Ahmet Çalgı",
        "profession": "Ünlü Çalgı Çalar",
        "funFact": "Her zaman yanlış nota çalar, ama çok eğlenceli",
        "isDeleted": false
    },
    ...
]
```
