# HyperledgerFabric

Supply Chain Management using HyperledgerFabric

===============================================

Environment:

Host: Windows 8.1 64-bit
With the use of Ubuntu 16.04 64-bit thru Virtual Box Version 5.2.26

Set-up:

Open fabric-samples/fabcar in Terminal.

Type ./openScm.sh and press enter

Type node enrollAdmin.js and press enter

Type node registerUser.js and press Enter

Type node rSupplier1.js and press Enter

Type node rOEM.js and press Enter

Type node rBank.js and press Enter

To test all functions, open a new terminal, type node app_scm.js and press Enter (port 3000)

To test as supplier1, open a new Terminal, type node appSupplier1.js and press Enter (port 3001)

To test as OEM, open a new Terminal, type node appOEM.js and press Enter (port 3002)

To test as a Bank, open a new Terminal, type node appBank.js and press Enter (port 3003)

Notes: Supplier1 can only raise an invoice and display invoices per supplier.
OEM can only set that goods are received and can pay to the Bank.
Bank can only pay to the supplier.

Testing it via Postman:

Install Postman. Open Postman.

To display invoices, set it to GET and type localhost:3000 in the address bar and click SEND.

To raise an invoice, add another bar in the tab, set it to POST, type localhost:3001/invoice in the address bar, go to Body tab, and tick x-www-form-urlencoded
	Type these following keys
	Key			Value (Samples)

	invoiceNumber		INV002
	billedTo		Lenovo
	invoiceDate		2/9/2019
	invoiceAmount		50000
	itemDescription		any description here
	gr			no
	isPaid			no
	paidAmount		0
	repaid			no
	repaymentAmount		0

After inputting these keys, press SEND. Go back to port 3000 and click SEND to check if it worked.

To set the goods that are received in an invoice, set it to PUT, type localhost:3002/invoice in the address bar, go to Body tab, and tick x-www-form-urlencoded

	Type these following keys

	Key			Value (sample)
	
	invoiceNumber		INV002
	gr			yes

After inputting these keys, press SEND. Go back to port 3000 and click SEND to check if it worked.

To repay the bank by OEM, set it to PUT, type localhost:3003 go to Body tab, and tick x-www-form-urlencoded

   Type in the following keys

	Key			Value (sample)
	
	invoiceNumber		INVxxx
	repaid			yes
	repaymentAmount		51000 (this must be greater than the paidAmount)

After inputting these keys, press SEND. Go back to port 3000 and click SEND to check if it worked.

**Created by :Tandang,Kevin Venson M.**

