def caesar_cipher_encrypt(text, shift):
    encrypted_text = ""
    for char in text:
        if char.isalpha():  # Check if the character is a letter
            shifted_char = chr((ord(char) - ord('a' if char.islower() else 'A') + shift) % 26 + ord('a' if char.islower() else 'A'))
            encrypted_text += shifted_char
        else:
            encrypted_text += char  # Non-alphabetical characters remain unchanged
    return encrypted_text

def caesar_cipher_decrypt(text, shift):
    return caesar_cipher_encrypt(text, -shift)  # Decryption is just encryption with negative shift

def main():
    while True:
        print("\nCaesar Cipher")
        print("1. Encrypt")
        print("2. Decrypt")
        print("3. Exit")
        choice = input("Enter your choice (1/2/3): ")

        if choice == '1':
            plaintext = input("Enter the message to encrypt: ")
            shift = int(input("Enter the shift value (0-25): "))
            encrypted_text = caesar_cipher_encrypt(plaintext, shift)
            print(f"Encrypted message: {encrypted_text}")

        elif choice == '2':
            ciphertext = input("Enter the message to decrypt: ")
            shift = int(input("Enter the shift value (0-25): "))
            decrypted_text = caesar_cipher_decrypt(ciphertext, shift)
            print(f"Decrypted message: {decrypted_text}")

        elif choice == '3':
            print("Exiting the program.")
            break

        else:
            print("Invalid choice. Please enter 1, 2, or 3.")

if __name__ == "__main__":
    main()
