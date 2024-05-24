#!/bin/bash

# Function to get the number of files in the current directory
get_file_count() {
    local file_count=$(ls -l | grep "^-" | wc -l)
    echo "$file_count"
}

# Main function
main() {
    local file_count=$(get_file_count)

    while true; do
        read -p "Guess the number of files in the current directory: " guess

        if [[ $guess -lt $file_count ]]; then
            echo "Too low!"
        elif [[ $guess -gt $file_count ]]; then
            echo "Too high!"
        else
            echo "Congratulations! You guessed correctly!"
            break
        fi
    done
}

# Call main function
main
