# Credit Card Simulator

A Java console application that simulates credit card usage: the user sets a spending limit, registers purchases, and the system tracks the available balance, blocking purchases that would exceed the limit.

## Features

- Set the credit card's initial limit
- Register purchases with description and value
- Automatic balance check before each purchase
- Blocks purchases that exceed the remaining balance
- Lists all completed purchases at the end of the session
- Displays the final card balance

## How it works

The program runs in a console loop:

1. Asks for the card's initial limit
2. Asks for the description and value of each purchase
3. If there's enough balance, the purchase is registered and the balance is updated
4. If there isn't enough balance, the purchase is declined and the program ends
5. At the end, it displays a summary of all purchases made and the remaining balance

## Project structure

```
├── Main.java              # Entry point, user interaction via Scanner
├── CartaoDeCredito.java   # Business logic: limit, balance, and purchase processing
└── Compra.java            # Represents a single purchase (description + value)
```

### Main classes

**`CartaoDeCredito`** (CreditCard)
- Stores `limite` (limit), `saldo` (balance), and the list of `compras` (purchases) made
- `lancaCompra(Compra compra)`: checks whether there's enough balance, deducts the value, and adds the purchase to the list; returns `true` or `false` depending on the result

**`Compra`** (Purchase)
- Simple object with `descricao` (description) and `valor` (value), representing a single purchase

**`Main`**
- Interacts with the user via `Scanner`, creates purchases, and displays the final summary

## Technologies

- Java (`ArrayList`, `Scanner`, encapsulation and object-oriented programming)

## How to run

```bash
javac Main.java CartaoDeCredito.java Compra.java
java Main
```

## Example run

```
Enter the card limit: 
500
Enter the purchase description:
Laptop
Enter the purchase value:
300
Purchase completed!
Enter 0 to exit or 1 to continue
0
************************************
PURCHASES MADE:

Laptop - 300.0

************************************

Card balance: 200.0
```

## Possible future improvements

- Allow multi-word descriptions
- Add sorting of purchases by value
- Validate invalid input (text where a number is expected)
- Persist data to a file or database

## Author

Developed by Juan as part of his Java and object-oriented programming studies.
