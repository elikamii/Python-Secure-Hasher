import hashlib

def generate_hash(text):
    """Generates a SHA-256 hash for the given string."""
    # Convert string to bytes
    encoded_text = text.encode()
    # Create the hash object
    hash_object = hashlib.sha256(encoded_text)
    # Return the hexadecimal representation
    return hash_object.hexdigest()

# Example usage
input_data = "my_secure_password_123"
hashed_result = generate_hash(input_data)

print(f"Original Data: {input_data}")
print(f"SHA-256 Hash: {hashed_result}")
