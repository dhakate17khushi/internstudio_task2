def celsius_to_fahrenheit(celsius):
    return (celsius * 9/5) + 32

def fahrenheit_to_celsius(fahrenheit):
    return (fahrenheit - 32) * 5/9

def temperature_converter():
    print("\nWelcome to the Temperature Converter!")
    print("Select the conversion direction:")
    print("1. Celsius to Fahrenheit")
    print("2. Fahrenheit to Celsius")

    try:
        choice = int(input("Enter your choice (1 or 2): "))
        if choice not in [1, 2]:
            raise ValueError("Invalid choice. Please select 1 or 2.")

        temperature = float(input("Enter the temperature value: "))

        if choice == 1:
            converted_temp = celsius_to_fahrenheit(temperature)
            print(f"{temperature}°C is equal to {converted_temp:.2f}°F.")
        elif choice == 2:
            converted_temp = fahrenheit_to_celsius(temperature)
            print(f"{temperature}°F is equal to {converted_temp:.2f}°C.")

    except ValueError as e:
        print(f"Error: {e}")

if _name_ == "_main_":
    while True:
        temperature_converter()
        again = input("\nDo you want to convert another temperature? (yes/no): ").strip().lower()
        if again != 'yes':
            print("Thank you for using the Temperature Converter! Goodbye!")
            break
