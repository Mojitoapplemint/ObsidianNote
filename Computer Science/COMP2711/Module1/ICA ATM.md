
Entity Objects: Class that is not actual component of ATM, but eventually comes up when considering the use-cases of ATM

| Components | Possible Event | Object Entity |
| ---------- | -------------- | ------------- |
| - Card Reader<br>- Log<br>- Receipt Printer<br>- Cash Dispenser<br>- Network To Bank<br>- Operating Panel<br>- Customer Console           | - Session<br>- Transaction<br>	- Withdraw<br>	- Deposit<br>	- Transfer<br>	- Inquiry               | - Balance<br>- Card<br>- Message<br>- Receipt<br>- Status              |
# Sequence Diagram
Go to [[2-2. Sequence Diagram|Sequence Diagram]]

![[Pasted image 20240115044639.png|400]]

# Use cases Diagram
Go to [[3. User Journey & User Use Cases|Use Cases Diagram]]
 ![[Pasted image 20240125180220.png|600]]

## Description
Use Case descriptions
- System Startup The system starts when the operator turns the switch to the "on" position. The operator will be asked to enter the amount of money currently in the cash dispenser, and a connection to the bank will be established. Then, the servicing of customers can begin. 

System Shutdown 
- The system shuts down when the operator ensures no customer is using the machine and then turns the operator switch to the "off" position. The connection to the bank will be shut down. Then, the operator can remove deposited envelopes, replenish cash and paper, etc. 

Session 
- A session begins when a customer inserts an ATM card into the card reader slot of the machine. The ATM pulls the card into the machine and reads it. (If the reader cannot read the card due to improper insertion or a damaged stripe, the card is ejected, an error screen is displayed, and the session is aborted.) The customer is asked to enter their PIN and is then allowed to perform one or more transactions, choosing from a menu of possible types of transactions in each case. After each transaction, the customer is asked whether they want to perform another. When the customer is done conducting transactions, the card is ejected from the machine, and the session ends. If a transaction is aborted due to too many invalid PIN entries, the session is also aborted, with the card retained in the machine. The customer may abort the session by pressing the Cancel key when entering a PIN or choosing a transaction type.

Transaction
- Transaction is an abstract generalization. 
- Each specific concrete type of transaction appropriately implements certain operations. The flow of events given here describes the behaviour common to all kinds of transactions. The flows of events for the individual types of transaction (withdrawal, deposit, transfer, inquiry) give the specific features of that type of transaction. A transaction use case begins within a session when the customer chooses a transaction type from a menu of options. The customer will be asked to furnish appropriate details (e.g., account(s) involved and amount). The transaction will then be sent to the bank, along with information from the customer's card and the PIN the customer entered. If the bank approves the transaction, any steps needed to complete the transaction (e.g. dispensing cash or accepting an envelope) will be performed, and a receipt will be printed. Then, the customer is asked whether they wish to do another transaction. If the bank reports that the customer's PIN is invalid, the Invalid PIN extension will be performed, and then an attempt will be made to continue the transaction. If the customer's card is retained due to too many invalid PINs, the transaction will be aborted, and the customer will not be offered the option of doing another. Suppose the customer cancels a transaction or fails for any reason other than repeated entries of an invalid PIN. In that case, a screen will display a message informing the customer of the reason for the failure of the transaction, and then the customer will be offered the opportunity to do another. The customer may cancel a transaction by pressing the Cancel key as described for each type of transaction below. All messages to the bank and responses back are recorded in the ATM's log. 

Withdrawal Transaction Use Case 
- A withdrawal transaction asks the customer to choose a type of account to withdraw from (e.g. checking) from a menu of possible accounts and to choose a dollar amount from a menu of possible amounts. The system verifies that it has sufficient money to satisfy the request before sending the transaction to the bank. (If not, the customer is informed and asked to enter a different amount.) If the bank approves the transaction, the machine dispenses the appropriate amount of cash before issuing a receipt. (The money distributed is also recorded in the ATM's log.) The customer can cancel a withdrawal transaction by pressing the Cancel key before choosing the dollar amount. 
Deposit Transaction Use Case 
- A deposit transaction asks the customer to choose a type of account to deposit to (e.g. checking) from a menu of possible accounts and to type in a dollar amount on the keyboard. The transaction is initially sent to the bank to verify that the ATM can accept a deposit from this customer to this account. If the transaction is approved, the machine accepts an envelope from the customer containing cash and/or cheques before it issues a receipt. Once the envelope has been received, a second message is sent to the bank to confirm that the bank can credit the customer's account - contingent on manual verification of the deposit envelope contents by an operator later. (The receipt of an envelope is also recorded in the ATM's log.) The customer can cancel a deposit transaction by pressing the Cancel key before inserting the deposit envelope. The transaction is automatically cancelled if the customer fails to insert the deposit envelope within a reasonable period after being asked to do so. 

Transfer Transaction Use Case 
- A transfer transaction asks the customer to choose a type of account to transfer from (e.g. checking) from a menu of possible accounts, to choose a different account to transfer to, and to type in a dollar amount on the keyboard. Once the bank approves the transaction, no further action is required before printing the receipt. The customer can cancel a transfer transaction by pressing the Cancel key before entering a dollar amount. 

Inquiry Transaction Use Case 
- An inquiry transaction asks the customer to choose a type of account to inquire about from a menu of possible accounts. Once the bank approves the transaction, no further action is required before printing the receipt. The customer can cancel an inquiry transaction by pressing the Cancel key before choosing the account to inquire about. 

Invalid PIN Extension 
- An invalid PIN extension begins from within a transaction when the bank reports that the customer's transaction is not approved due to an invalid PIN. The customer is required to re-enter the PIN, and the original request is sent to the bank again. If the bank now approves the transaction or disapproves it for some other reason, the original use case is continued; otherwise, the process of re-entering the PIN is repeated. Once the PIN is successfully re-entered, it is used for both the current and subsequent transactions in the session. Suppose the customer fails three times to enter the correct PIN. In that case, the card is permanently retained, and a screen is displayed informing the customer of this and suggesting they contact the bank, and the entire customer session is aborted. The original transaction is cancelled if the customer presses Cancel instead of re-entering a PIN


