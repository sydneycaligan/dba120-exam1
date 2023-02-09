# dba120-exam1
INSERT INTO terms (terms_id, terms_description, terms_due_days) VALUES (6, 'Net due 120 days', 120)
Ex 1 The SQL query added a record to the terms table.
![2023-02-08](https://user-images.githubusercontent.com/122293091/217681256-63805e6a-6685-4f91-ae8c-48cb50b061e7.png)

UPDATE terms
SET terms_description = 'Net due 125 days',
    terms_due_days = 125
WHERE terms_id = 6
Ex 2 The SQL query updated a record in the terms table.
![2023-02-08 (1)](https://user-images.githubusercontent.com/122293091/217686073-fa5e0719-136a-4734-a162-e18d1cebce52.png)

DELETE FROM terms
WHERE terms_id = 6
Ex 3 The SQL query deleted a record in the terms table.
![2023-02-08 (2)](https://user-images.githubusercontent.com/122293091/217687039-096dfbd5-2565-44aa-b068-25228fe6a117.png)

INSERT INTO invoices
VALUES (DEFAULT, 32, 'AX-014-027', '2018-08-01', 434.58, 0, 0,
        2, '2018-08-31', NULL)

Ex 4 The SQL query inserted a record in the Invoices table.
![2023-02-08 (4)](https://user-images.githubusercontent.com/122293091/217689248-bcb36f79-70b6-4a76-b2a8-b4c3f9ba2664.png)

INSERT INTO invoice_line_items VALUES
    (115, 1, 160, 180.23, 'Hard drive'),
    (115, 2, 527, 254.35, 'Exchange Server update')

Ex 5 The SQL query inserted 2 rows into Invoice_Line_Items.
![2023-02-08 (5)](https://user-images.githubusercontent.com/122293091/217691003-89fdc9bf-1553-45a1-accd-5fb203c1d1b1.png)

UPDATE invoices
SET credit_total = invoice_total * .1,
    payment_total = invoice_total - credit_total
WHERE invoice_id = 115
Ex 6 The SQL query updated the statement from ex 4 in the Invoices table.
![2023-02-08 (6)](https://user-images.githubusercontent.com/122293091/217692105-e2eb8a43-350f-4c46-8e2b-8f06a6abc3d6.png)

UPDATE vendors
SET default_account_number = 403
WHERE vendor_id = 44
Ex 7 The SQL query updates a row in the Vendors table.
![2023-02-08 (7)](https://user-images.githubusercontent.com/122293091/217692795-9b7e6ec7-b854-4a84-bc9b-65f9e5dcaec1.png)

UPDATE invoices
SET terms_id = 2
WHERE vendor_id IN
    (SELECT vendor_id
     FROM vendors
     WHERE default_terms_id = 2)

Ex 8 The SQL query updates the Invoices table.
![2023-02-08 (8)](https://user-images.githubusercontent.com/122293091/217694200-1caf44ee-a5db-4c26-b545-034c88b60207.png)

DELETE FROM invoice_line_items
WHERE invoice_id = 115;

DELETE FROM invoices
WHERE invoice_id = 115;

Ex 9 The SQL query deletes a row from Invoice_Line_Items and deletes a row from Invoices.
![2023-02-08 (9)](https://user-images.githubusercontent.com/122293091/217696324-5dbbe7d7-f311-4c2f-9cd2-882c9885b3c6.png)
