# creative-commons-coalition-emoiji-codec-project


## Test 6/7/2023

Here's an example of representing the table in YAML format and then loading it into Python using the `pyyaml` library:

```yaml
- [0, 6, 7, 8, 9, "0", "⨀⨀⨀⨀"]
- [1, 11, 12, 13, 14, "1", "⨀⨀⨀⨁"]
- [2, 16, 17, 18, 19, "2", "⨀⨀⨁⨀"]
```

To load this YAML data into Python, you can use the `pyyaml` library. Make sure you have `pyyaml` installed before running the code.

```python
import yaml

# Read YAML data from a file
with open('table.yaml', 'r') as file:
    table_data = yaml.safe_load(file)

# Example usage
def decimal_to_kaktovic(decimal):
    kaktovic_numeral = None
    kaktovic_binary = None

    for row in table_data:
        if row[1] == decimal:
            kaktovic_numeral = row[5]
            kaktovic_binary = row[6]
            break

    return kaktovic_numeral, kaktovic_binary

def kaktovic_to_decimal(kaktovic):
    decimal = None

    for row in table_data:
        if row[5] == kaktovic or row[6] == kaktovic:
            decimal = row[1]
            break

    return decimal

# Convert decimal to Kaktovic numeral and binary
decimal = 8
kaktovic_numeral, kaktovic_binary = decimal_to_kaktovic(decimal)
print(f"Decimal {decimal} converted to Kaktovic numeral: {kaktovic_numeral}")
print(f"Decimal {decimal} converted to Kaktovic binary: {kaktovic_binary}")

# Convert Kaktovic numeral to decimal
kaktovic = "1"
converted_decimal = kaktovic_to_decimal(kaktovic)
print(f"Kaktovic numeral {kaktovic} converted to decimal: {converted_decimal}")

# Convert Kaktovic binary to decimal
kaktovic = "⨀⨀⨀⨁"
converted_decimal = kaktovic_to_decimal(kaktovic)
print(f"Kaktovic binary {kaktovic} converted to decimal: {converted_decimal}")
```

In this example, the YAML data is loaded from the file "table.yaml" using `yaml.safe_load()` and stored in the `table_data` variable. Then, the `decimal_to_kaktovic()` and `kaktovic_to_decimal()` functions from the previous code snippet are used for the conversions.

Remember to replace `'table.yaml'` with the actual path to your YAML file.

I hope this helps! Let me know if you have any further questions.
