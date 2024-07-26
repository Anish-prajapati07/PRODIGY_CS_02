from PIL import Image
import numpy as np
import os
def encrypt_image(image_location, key):
    try:
        original_image = Image.open(image_location)
    except (IOError, OSError):
        print("Invalid location. Image not found or unable to open the image.")
        return
    image_array = np.array(original_image)
    encrypted_pixels = (image_array + key) % 256
    encrypted_image = Image.fromarray(encrypted_pixels.astype('uint8'))
    encrypted_image_path = os.path.join(os.path.dirname(image_location), 'encrypted.png')
    encrypted_image.save(encrypted_image_path)
    print(f"Image encryption completed. Encrypted image saved as {encrypted_image_path}")
def decrypt_image(image_location, key):
    try:
        original_image = Image.open(image_location)
    except (IOError, OSError):
        print("Invalid location. Image not found or unable to open the image.")
        return
    image_array = np.array(original_image)
    decrypted_pixels = (image_array - key) % 256
    decrypted_image = Image.fromarray(decrypted_pixels.astype('uint8'))
    decrypted_image_path = os.path.join(os.path.dirname(image_location), 'decrypted.png')
    decrypted_image.save(decrypted_image_path)
    print(f"Image decryption completed. Decrypted image saved as {decrypted_image_path}")
def encryptIt():
    while True:
        try:
            key = int(input("Enter encryption key: ")) 
            break
        except ValueError:
            print("Invalid encryption key. Please enter a valid integer.")
    image_location = input("Enter name of the image: ")
    encrypt_image(image_location, key)
def decryptIt():
    while True:
        try:
            key = int(input("Enter decryption key: ")) 
            break
        except ValueError:
            print("Invalid decryption key. Please enter a valid integer.")
    image_location = input("Enter name of the image: ")
    decrypt_image(image_location, key)
def main():
    while True:
        choice = input("Select (e)ncryption, (d)ecryption or (q)uit: ").lower()
        if choice == 'e':
            encryptIt()
        elif choice == 'd':
            decryptIt()
        elif choice == 'q':
            print("Exiting the program.")
            break
        else:
            print("Invalid choice. Please choose 'e' for encryption, 'd' for decryption, or 'q' to quit.")
if __name__ == "__main__":
    main()

