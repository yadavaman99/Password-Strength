import re

def check_password_strength(password):
    score = 0

    print("\nChecking password:", password)
    print("-" * 40)

    # 1. Length check
    if len(password) >= 8:
        score += 1
        print("[+] Good length (8+ characters)")
    else:
        print("[-] Too short (min 8 characters)")

    # 2. Uppercase check
    if re.search(r"[A-Z]", password):
        score += 1
        print("[+] Contains uppercase letter")
    else:
        print("[-] No uppercase letter")

    # 3. Lowercase check
    if re.search(r"[a-z]", password):
        score += 1
        print("[+] Contains lowercase letter")
    else:
        print("[-] No lowercase letter")

    # 4. Number check
    if re.search(r"[0-9]", password):
        score += 1
        print("[+] Contains number")
    else:
        print("[-] No number")

    # 5. Special character check
    if re.search(r"[!@#$%^&*(),.?\":{}|<>]", password):
        score += 1
        print("[+] Contains special character")
    else:
        print("[-] No special character")

    # Final result
    print("-" * 40)

    if score == 5:
        print("🔐 Password Strength: VERY STRONG")
    elif score == 4:
        print("🟢 Password Strength: STRONG")
    elif score == 3:
        print("🟡 Password Strength: MEDIUM")
    elif score == 2:
        print("🟠 Password Strength: WEAK")
    else:
        print("🔴 Password Strength: VERY WEAK")


# -------------------------
# MAIN PROGRAM
# -------------------------
password = input("Enter your password: ")
check_password_strength(password)
