#!/bin/bash
# Group Management Script

echo "Group Management Script"

# Add a new group
echo -n "Enter the group name to add: "
read group_name
if [ ! -z "$group_name" ]; then
sudo groupadd $group_name
else
echo "No group name entered. Skipping group addition."
fi

# Optionally delete a group

echo -n "Enter the group name to delete: "
read del_group
if [ ! -z "$del_group" ]; then
sudo groupdel $del_group
else
echo "No group name entered. Skipping group deletion."
fi

# Add a user to a group
echo -n "Enter the username to add to a group: "
read user_name
echo -n "Enter the group to add the user to: "
read group_name
sudo usermod -aG $group_name $user_name
echo "$user_name added to $group_name"
