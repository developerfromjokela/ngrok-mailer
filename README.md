# Ngrok Mailer


This script starts ngrok forwarding with configured IP address or default localhost, and sends its public url to email. Usecases for example: Servers/NASes without port forwarding, IoT devices, other devices without port forwarding.

## Installation

Download or install Git command [git](https://git-scm.com/downloads) to install ngrok-mailer.

Clone repository master or download archived master

```bash
git clone https://github.com/developerfromjokela/ngrok-mailer.git
```
OR

```bash
wget https://github.com/developerfromjokela/ngrok-mailer/archive/master.zip
unzip master.zip
```
## Usage
Run script as root or using sudo
```bash
./ngrokmailer.sh
```
OR
```bash
sudo ./ngrokmailer.sh
```
Make script run on startup:
```bash
nano /etc/rc.local
# Then paste this below into rc.local:
./path/to/folder/ngrokmailer.sh
```

## Configuring
This script is configurable for your suites and usecases.
All parameters and usage:

``` forwarding_ip="192.168.100.69"``` 
- Set device IP, for ngrok to forward. Blank is locahost

``` forwarding_port="80"``` 
- Set device's port, for ngrok to forward using that exact protocol port.

``` forwarding_connectiontype="http"``` 
- Configure forwarding type, if your device is running http server, change parameter http, tcp, etc. More info in ngrok [documentation](https://ngrok.com/docs#websockets).

``` email_addr="youremail@example.com"``` 
- Email address where public url should be sent


``` ssmtp_root="example@gmail.com"``` 
- Email address which is used to send emails

``` ssmtp_mailhub="smtp.gmail.com:587"``` 
- SMTP address of mail server

```
ssmtp_authuser="example@gmail.com"
ssmtp_authpass="passwordforgmail" 
``` 
- Authentication for SMTP Server

``` ssmtp_usestarttls="YES"``` 
- Use STARTTLS for SMTP Communications (NO disables it)

``` ssmtp_autoconfig=true``` 
- This parameter enables or disables ssmtp.conf overwrite using ssmtp_* parameters (false disables it, and file ssmtp.conf will not be overwritten)


``` logging=false``` 
- This parameter enables or disables logging activities in script to file ngrokmailer.log (false disables logging, and file msg.txt, which are created for email sending, will be deleted after mail is sent)

``` ngrok_path="ngrok"``` 
- You can set custom ngrok path, and default is ngrok. By default, if file was not found, it will be downloaded and extracted.

```checkfordependencies=true``` 
- Disable or Enable dependencies check on script startup, if some packages are missing. (If checking is leading to problems, try to disable this, if you set script to run on startup)


## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)
