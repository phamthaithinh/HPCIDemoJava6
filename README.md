HPCIDemoJava6 v1.0 Jan 2 2015
================

HostedPCI Demo App
Includes Web Checkout (iFrame) and Phone Session (IVR) services.

What is it?
============
HPCIDemo is a small app that will help customers implement the HostedPCI API when they want to use the 
HostedPCI Web Checkout and Phone Session services.
The HostedPCI Demo App is a small tool to help HostedPCI customers visualize the power, potential and how HostedPCI can help them become PCI compliant as affordable as possible and as easy as possible. 
Our motto is, your vision, our reality.
By installing HostedPCI Demo App you will see what it can do for you, how easy it is to implement it on your eCommerce site or call center and will show you how to do it if you get stuck implementing it.

What does this service do?
=========================

The HostedPCI Phone Session service designed to help companies who need to take credit card information from customers
over the phone. For example, insurance call centers who want to become PCI compliant.
The HostedPCI Web Checkout service is designed to help companies become PCI compliant with their eCommerce site while being customizeable for any situation.

How does it work?
=================

Web Checkout:
=============
1. eCommerce loads the page.
2. Page requests a new iframe from HostedPCI.
3. HostedPCI verifies the website and webpage are correct.
4. HostedPCI sends the iframe to the eCommerce page.
5. User fills the payment form and clicks “Submit”.
6. Iframe is being sent back to HostedPCI for tokenization of the credit card.
7. Token is delivered back to the form and populates all the required hidden fields (CC, CVV and BIN numbers) in the form.
8. eCommerce form submits payment request with credit card token, cvv token, expiry date and amount.
9. HostedPCI submits payment request with real credit card, real cvv, expiry date and amount.
10. HostedPCI gets the payment response from the bank.
11. HostedPCI sends the response along with other information back to the eCommerce site.
12. eCommerce page can then collect the response with all the information and display it back to the user.

Phone Session:
=============
1. The HPCIDemoIVRJava6 app makes a call to the HostedPCI server and creates a session.
2. The CSR (Customer Support Representitive) makes a 3 way phone call and enters the session key number.
3. The IVR asks the customer to punch in his credit card and cvv numbers.
4. The IVR verifies the information.
5. If everything checks out, the IVR returns a token back to the HPCIDemoIVRJava6 app.
6. The CSR takes all other required information from the client (name, address, phone number) and fills in the form
   and submits.
7. The application takes in the token and all other required information and calls HostedPCI to process payment.
8. The application reads back the answer from HostedPCI and displays it to the CSR.

Release information
===================
Version 1.0, Jan 2 2015

Java JDK 6
Jquery 2.1.1
Bootstrap 3.2
Jetty 8.1.2
Browser

Installation
============
There are 2 methods of running it:
Using RunJettyRun plugin within Eclipse, or using JettyRunner.jar and HPCIDemoJava6.jar from 
terminal/command prompt.
Using Eclipse:
==============
1. Set RunJettyRun to be assosiated with HPCIDemoJava6 and set it to 8799 port (If you want a different port you need to change the port in webCheckoutForm.jsp too).
2. Run using Jetty.
3. Open your browser and go to http://localhost:8799/home.jsp and choose one of the services you want to try.

Using Jetty Runner:
===================
1. Download HPCIDemoJava6.war and Jetty-runner.jar.
2. Open the terminal/command prompt and go to the folder where both files are.
3. Type “java -jar jetty-runner.jar --stats unsecure --log yyyy_mm_dd-requests.log --port 8799 --out yyyy_mm_dd-output.txt HPCIDemoJava6.war”
4. If everything went well, you should see something like this and a blinking cursor afterwards:
2014-10-08 10:33:36.843:INFO::main: Logging initialized @71ms
2014-10-08 10:33:36.848:INFO:oejr.Runner:main: Runner
2014-10-08 10:33:36.850:INFO:oejr.Runner:main: Redirecting stderr/stdout to yyyy_mm_dd-output.txt
5. Open any browser and type in http://localhost:8799/home.jsp and choose one of the services you want to try.

How to use the Web Checkout app:
================================
1. Fill in the payment form.
2. You can use VISA test number 4111-1111-1111-1111 cvv: any 3 digits.
3. Expiry date must be a date in the present or date in the future.
4. Press on Process Payment button.
5. You will be sent to the confirmation page with the transaction restults.

How to use the Phone Session app:
================================
1. Create a new session, call the HostedPCI IVR number and enter the session key.
2. Follow the instructions by the IVR (you can enter a test credit card number 4111-1111-1111-1111).
3. If everything checks out, when you click on the Update Progress button, the form will now update with the credit card token that was given by the IVR.
4. Fill the rest of the form (MM/YY expiration has to be a future date).
5. Press the Process Payment button.
6. You will see the results of the payment process at the bottom of the page.

Contacts
=========
HostedPCI Inc.
http://www.hostedpci.com/
sales@hostedpci.com
1-866-850-3608
