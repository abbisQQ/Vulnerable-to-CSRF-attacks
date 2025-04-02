# Vulnerable-to-CSRF-attacks

It was identified that the https://github.com/Volmarg/personal-management-system application is
vulnerable to CSRF attacks, one of the many action an attacker can perform is trick a legitimate
user to run a cross site request that will alter his/her password, allowing the attacker access to the
application. The vulnerability requires browsers that have the “SameSite” cookie attribute defaults
value to none such as Firefox.

Vektor String: CVSS:3.1/AV:N/AC:H/PR:N/UI:R/S:C/C:L/I:L/A:N

CVSS Score: 4.7

Please note that the tests were made in my own local environment.

Proof of concept
For the demonstration I will use the username tester and change that user password to “missingcsrf”
Note that the attacker can change other values such as the nickname and the lock password.
The application is generally vulnerable to CSRF, meaning a malicious user can trick users to upload
files change password mess records etc.

![image](https://github.com/user-attachments/assets/a14d92ca-2f81-4041-9ae9-3bbadbbb77af)

This is a simple html page that will make the cross-site request when the user visit the malicious URL.
![image](https://github.com/user-attachments/assets/ef41c253-a9a6-449e-bbdd-9b03f5833773)

Running the above in a Firefox browser, the password changed successfully.
![image](https://github.com/user-attachments/assets/d1458787-85c9-428e-b0c1-32aa4a3d4978)

Finally, we log in with the modifies password and we can see we getting redirected to the dashboard page, which means the login was successful.
![image](https://github.com/user-attachments/assets/643b5c40-83d9-417f-beca-32717789cd01)

