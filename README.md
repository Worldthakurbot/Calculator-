def add(x, y): return x + y
def subtract(x, y): return x - y
def multiply(x, y): return x * y
def divide(x, y):
    return x / y if y != 0 else None

def get_number(prompt):
    while True:
        try:
            return float(input(prompt))
        except ValueError:
            print("Invalid number. Please try again.")

def main():
    print("Simple CLI Calculator")
    while True:
        print("\n1) Add  2) Subtract  3) Multiply  4) Divide  5) Exit")
        choice = input("Choose an option (1‑5): ")
        if choice == '5':
            print("Bye!")
            break
        if choice not in ('1','2','3','4'):
            print("Invalid choice, try again.")
            continue

        num1 = get_number("Enter first number: ")
        num2 = get_number("Enter second number: ")

        ops = {'1': (add, '+'), '2': (subtract, '-'),
               '3': (multiply, '*'), '4': (divide, '/')}
        func, symbol = ops[choice]
        result = func(num1, num2)
        if result is None:
            print("Error: Cannot divide by zero.")
        else:
            print(f"{num1} {symbol} {num2} = {result}")

if __name__ == "__main__":
    main()
