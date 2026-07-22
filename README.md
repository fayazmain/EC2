<img width="1895" height="917" alt="Screenshot 2026-07-22 194504" src="https://github.com/user-attachments/assets/9a7d31c9-c187-4256-8dd4-248e360c6de6" />
<img width="1898" height="901" alt="Screenshot 2026-07-22 194517" src="https://github.com/user-attachments/assets/10812ac8-05dd-413c-94f6-6d8d1a38b8f0" />



# 1. Connect to your AWS instance from your local computer
ssh -i /path/to/your-key.pem ec2-user@174.129.182.7

# 2. Check your home directory for the file (failed with 'No such file')
cat index.html

# 3. Try to create/open it in your home directory
nano index.html

# 4. Navigate into the proper Apache web server directory
cd /var/www/html/

# 5. List the directory contents to confirm the existing index.html file
ls -l

# 6. Try to edit the file directly in the web directory (threw permission error)
nano index.html

# 7. Edit the file with administrative privileges to write the CLOUDS club code
sudo nano index.html

# 8. Force write or overwrite the exact file path directly
sudo nano /var/www/html/index.html

# 9. Verify if your changes (your name) successfully saved to the file
cat /var/www/html/index.html | grep "Fayaz"

# 10. Restart the Apache web server to clear memory cache and force updates
sudo systemctl restart httpd

# 11. Alternative method: Copy a file from a home folder into the Apache web directory
sudo cp index.html /var/www/html/

# 12. Fix the file permissions so the Apache web server can read it
sudo chown ec2-user:ec2-user /var/www/html/index.html
sudo chmod 644 /var/www/html/index.html

# 13. Disconnect and close the remote AWS terminal session securely
exit

