This is a python 3 package meant to make managing emails easier.
It will probably help to add readability and reduce lines. Here's an example of how much it reduces lines:

Regular is on the left.	With emailHelpers is on the right.
```python3
import smtplib					from emailHelpers import *
from email.MIMEMultipart import MIMEMultipart	(Reduction)
from email.MIMEText import MIMEText		(Reduction)
fromaddr = "YOUR ADDRESS"			fromaddr = "YOUR ADDRESS"
toaddr = "ADDRESS YOU WANT TO SEND TO"		toaddr = "ADDRESS YOU WANT TO SEND TO"
msg = MIMEMultipart()				email = Email(fromaddr)
msg['From'] = fromaddr				(Reduction)
msg['To'] = toaddr				email.setTo(toaddr)
msg['Subject'] = "SUBJECT OF THE MAIL"		email.setSubject("SUBJECT OF THE MAIL")
 						
body = "YOUR MESSAGE HERE"			body = "YOUR MESSAGE HERE"
msg.attach(MIMEText(body, 'plain'))		(Reduction)
 						
server = smtplib.SMTP('smtp.gmail.com', 587)	mailer = Mailer(fromaddr, "YOUR PASSWORD")
server.starttls()				(Reduction)
server.login(fromaddr, "YOUR PASSWORD")		(Reduction)
text = msg.as_string()				text = email.as_string()
server.sendmail(fromaddr, toaddr, text)		mailer.sendMail(text,toaddr)
server.quit()					mailer.quitSelf()
```

Look! We reduced the number of lines by 6 lines! Also, which makes more sense to someone who's learning python:
```python3
server = smtplib.SMTP('smtp.gmail.com', 587)
server.starttls()
server.login(fromaddr, "YOUR PASSWORD")
```
or
```python3
mailer = Mailer(fromaddr, "YOUR PASSWORD")
```
I'd go for the 1-line option myself. I don't think everybody knows what tls and smtp is, and asking the computer to login sounds kind of creepy. (Sorry if your feelings are hurt, naelshiab and everybody who worked on the libraries that I used. Yeah, I use the original libraries.)  
  
That's a couple of reasons to use emailHelpers. Complete with docstrings and (mostly)self-explanatory function names, get started now.  
Instructions to install are down.
To install emailHelpers:  
First, download this repo. Then, navigate in your terminal/shell into the repo. Now, follow the following instructions.  
If you are a Linux/Ubuntu/Raspberry Pi user:  
	Type in your terminal/shell "python3".  
	IMPORTANT: You have to say "install" in the next step, or else there will be an error.  
	If that works, type "sudo python3 setup.py install".  
	If typing in "python3" didn't work, try typing "python".  
	If that doesn't work, install python 3. Look at this page for the files: https://www.python.org/downloads/source  
	After installing python 3, type "sudo python3 setup.py install".  
	But if typing in "python" did work, check and see if it says after "Python " a 3 or a 2.  
	If it's a 3, type "sudo python setup.py install"  
	If it's a 2, install python 3. Look at this page for the files: https://www.python.org/downloads/source/  
	After installing python 3, type "sudo python3 setup.py install".  
If you are a Windows user:  
	Type in your terminal/shell "python3".  
	IMPORTANT: When you run setup.py, you have to say "install" and "--user", or else there will be an error.  
	If that works, type "python3 setup.py install --user".  
	If typing in "python3" didn't work, try typing "python".  
	If that doesn't work, install python 3. Look at this page for the files: https://www.python.org/downloads/windows/  
	After installing python 3, type "python3 setup.py install --user".  
	But if typing in "python" did work, check and see if it says after "Python " a 3 or a 2.  
	If it's a 3, type "python setup.py install --user"  
	If it's a 2, install python 3. Look at this page for the files: https://www.python.org/downloads/windows/  
	After installing python 3, type "python3 setup.py install --user".  
Apple and other platforms are coming. If you have a platform that isn't listed, please let the authors know.  
See INTERFACE for more info about how to use this package.  
