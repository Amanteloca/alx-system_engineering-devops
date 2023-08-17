#!/bin/bash

# Check if at least 3 parameters are provided
if [ "$#" -lt 3 ]; then
    echo "Usage: $0 PATH_TO_FILE IP USERNAME [PATH_TO_SSH_KEY]"
    exit 1
fi

# Assign parameters to variables
file_path="$1"
ip_address="$2"
username="$3"
ssh_key="$4"

# If SSH key path is not provided, use the default identity
if [ -z "$ssh_key" ]; then
    ssh_key="~/.ssh/id_rsa"
fi

# Disable strict host key checking
scp_command="scp -o StrictHostKeyChecking=no -i $ssh_key $file_path $username@$ip_address:~/"

# Transfer the file using scp
$scp_command

echo "File transferred successfully to $ip_address"
