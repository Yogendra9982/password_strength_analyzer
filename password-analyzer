#!/bin/bash

# ==========================================
# PASSWORD STRENGTH ANALYZER
# Author: Yogendra Samriya
# ==========================================

RED="\e[31m"
GREEN="\e[32m"
YELLOW="\e[33m"
CYAN="\e[36m"
RESET="\e[0m"

echo -e "${CYAN}"
echo "======================================"
echo "     PASSWORD STRENGTH ANALYZER"
echo "======================================"
echo -e "${RESET}"

read -s -p "Enter Password: " password
echo

score=0

# -----------------------------
# Length Check
# -----------------------------

length=${#password}

if [ "$length" -ge 12 ]; then
    echo -e "${GREEN}[+] Good Length (${length})${RESET}"
    ((score+=2))
elif [ "$length" -ge 8 ]; then
    echo -e "${YELLOW}[!] Acceptable Length (${length})${RESET}"
    ((score+=1))
else
    echo -e "${RED}[-] Too Short (${length})${RESET}"
fi

# -----------------------------
# Uppercase Check
# -----------------------------

if [[ $password =~ [A-Z] ]]; then
    echo -e "${GREEN}[+] Uppercase Found${RESET}"
    ((score++))
else
    echo -e "${RED}[-] No Uppercase Letter${RESET}"
fi

# -----------------------------
# Lowercase Check
# -----------------------------

if [[ $password =~ [a-z] ]]; then
    echo -e "${GREEN}[+] Lowercase Found${RESET}"
    ((score++))
else
    echo -e "${RED}[-] No Lowercase Letter${RESET}"
fi

# -----------------------------
# Number Check
# -----------------------------

if [[ $password =~ [0-9] ]]; then
    echo -e "${GREEN}[+] Number Found${RESET}"
    ((score++))
else
    echo -e "${RED}[-] No Number Found${RESET}"
fi

# -----------------------------
# Special Character Check
# -----------------------------

if [[ $password =~ [\!\@\#\$\%\^\&\*\(\)_\+\=\-\[\]\{\}\;\:\'\"\,\<\>\.\?\/\\\|] ]]; then
    echo -e "${GREEN}[+] Special Character Found${RESET}"
    ((score++))
else
    echo -e "${RED}[-] No Special Character${RESET}"
fi

# -----------------------------
# Common Password Detection
# -----------------------------

common_passwords=(
    "password"
    "123456"
    "admin"
    "qwerty"
    "welcome"
    "password123"
)

for common in "${common_passwords[@]}"
do
    if [[ "$password" == "$common" ]]; then
        echo -e "${RED}[-] Common Password Detected${RESET}"
        score=0
        break
    fi
done

# -----------------------------
# Strength Rating
# -----------------------------

echo
echo "Score : $score/6"

if [ "$score" -le 2 ]; then
    echo -e "${RED}Weak Password${RESET}"
elif [ "$score" -le 4 ]; then
    echo -e "${YELLOW}Medium Password${RESET}"
else
    echo -e "${GREEN}Strong Password${RESET}"
fi

# -----------------------------
# Strong Password Suggestion
# -----------------------------

echo
echo "Suggested Strong Passwords:"

for i in {1..3}
do
    tr -dc 'A-Za-z0-9!@#$%^&*()_+=' < /dev/urandom | head -c 16
    echo
done
