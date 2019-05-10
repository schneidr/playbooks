# Store passwords 

Generate the encrypted variable entry with this command:

    ansible-vault encrypt_string  --ask-vault-pass --stdin-name ansible_become_password

The result will look like this:

    ansible_become_password: !vault |
              $ANSIBLE_VAULT;1.1;AES256
              35623732646263636163383738353230626565383533626261313564383832643334363632383134
              3833316539376436333462303564636236646662376535300a356631346166626632333365353465
              30343138313363666434343938393464343861666234633434383037393230633333333364383835
              3962383339373731610a316362326239386539633638646331636633333330633231383730323634
              33653332353239353662366631373037653135303163663365633532643535663933

Copy this entry into the host variable file. Make sure you use the same vault password for all password entries.

Run the playbook with

    ansible-playbook --ask-vault-pass playbook.yml