def caesar_cipher(text, shift, mode='encrypt'):
    result = ''
    shift = shift % 26

    if mode == 'decrypt':
        shift = -shift

    for char in text:
        if char.isalpha():
            base = ord('A') if char.isupper() else ord('a')
            shifted = (ord(char) - base + shift) % 26 + base
            result += chr(shifted)
        else:
            result += char
    return result

if __name__ == "__main__":
    message = input("Enter your message: ")
    shift = int(input("Enter the shift value (e.g., 3): "))
    mode = input("Choose mode - 'encrypt' or 'decrypt': ").lower()

    output = caesar_cipher(message, shift, mode)
    print(f"Result: {output}")
