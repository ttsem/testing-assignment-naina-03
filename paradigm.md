# Paradigms Used in the Calculator Code

## Object-Oriented Programming
- Classes and records model behavior and data.
- Encapsulation keeps arithmetic, service logic, and persistence separate.

## Abstraction and Interfaces
- `ICalculator`, `ICalculatorService`, and `IHistoryRepository` abstract implementation details.
- Interfaces allow swapping concrete implementations without changing callers.

## Dependency Injection
- `CalculatorService` receives `ICalculator` and `IHistoryRepository` via constructor injection.
- This improves testability and decouples business logic from storage details.

## Separation of Concerns
- `Calculator` handles arithmetic operations.
- `CalculatorService` handles command routing, validation, and history updates.
- `XmlHistoryRepository` handles XML persistence of calculation history.

## Repository Pattern
- `IHistoryRepository` defines storage operations.
- `XmlHistoryRepository` implements persistence and history retention.

## C# Language Features
- `record` type for immutable domain data (`CalculationRecord`).
- `sealed` classes to prevent unwanted inheritance.
- `switch` expressions for clean operation dispatch.
- LINQ for XML parsing and collection processing.
- `IReadOnlyList<T>` for read-only history exposure.

## Error Handling
- Throws `ArgumentException` for invalid or unsupported operations.
- Throws `DivideByZeroException` for divide-by-zero attempts.

## Testing Practices
- xUnit tests validate arithmetic and service behavior.
- In-memory test doubles isolate tests from file I/O.
- Unit tests verify history tracking and error conditions.
