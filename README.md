import hashlib

def import hashlib

def hash_data(data, algorithm='sha256'):
    """Hashes data using the specified algorithm (md5, sha1, sha256)."""
    encoded_data = data.encode()
    
    if algorithm == 'sha256':
        return hashlib.sha256(encoded_data).hexdigest()
    elif algorithm == 'md5':
        return hashlib.md5(encoded_data).hexdigest()
    elif algorithm == 'sha1':
        return hashlib.sha1(encoded_data).hexdigest()
    else:
        return "Unsupported algorithm"

def verify_data(plain_text, existing_hash, algorithm='sha256'):
    """Checks if the plain text matches the given hash."""
    new_hash = hash_data(plain_text, algorithm)
    return new_hash == existing_hash

# Test scenarios
secret = "SecretKey2026"
stored_hash = hash_data(secret, 'sha256')

print(f"Data: {secret}")
print(f"Stored Hash: {stored_hash}")

# Verification check
is_valid = verify_data("SecretKey2026", stored_hash)
print(f"Verification Result: {'✅ Match' if is_valid else '❌ No Match'}")
