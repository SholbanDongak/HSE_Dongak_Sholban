def roman_to_int(s):
    roman_dict = {'I': 1, 'V': 5, 'X': 10, 'L': 50, 'C': 100, 'D': 500, 'M': 1000}
    result = 0
    prev_value = 0
    
    for char in s:
        value = roman_dict[char]
        result += value
        if value > prev_value:
            result -= 2 * prev_value
        prev_value = value
        
    return result

print(roman_to_int("III"))  # Output: 3
print(roman_to_int("LVIII"))  # Output: 58
print(roman_to_int("MCMXCIV"))  # Output: 1994