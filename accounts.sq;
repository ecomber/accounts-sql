SET @START_YEAR = '2007';
SET @END_YEAR   = '2008';


# Create file of all transactions collated and summed
SELECT PAYEE, sum(amount) from transactions WHERE date BETWEEN CAST(CONCAT(@START_YEAR,'-07-01') AS DATE) AND CAST(CONCAT(@END_YEAR,'-06-30') AS DATE) group by payee order by sum(amount)
INTO OUTFILE 'C:\\Users\\ec\\Desktop\\Expenses\\EComberExpenses_2007-2008_collated.csv'
FIELDS TERMINATED BY ','
ENCLOSED BY '"' 
LINES TERMINATED BY '\n';

# Create file of all transactions sorted by date 
SELECT `transactions`.`BANK_ID`,
    `transactions`.`ACCOUNT_ID`,
    `transactions`.`DATE`,
    `transactions`.`PAYEE`,
    `transactions`.`TYPE`,
    `transactions`.`AMOUNT`,
    `transactions`.`MEMO`
FROM `bank`.`transactions`
WHERE date BETWEEN CAST(CONCAT(@START_YEAR,'-07-01') AS DATE) AND CAST(CONCAT(@END_YEAR,'-06-30') AS DATE) order by 'date'
INTO OUTFILE 'C:\\Users\\ec\\Desktop\\Expenses\\EComberExpenses_2007-2008_ByDate.csv'
FIELDS TERMINATED BY ','
ENCLOSED BY '"' 
LINES TERMINATED BY '\n';


# Create file of all transactions sorted by amount
SELECT `transactions`.`BANK_ID`,
    `transactions`.`ACCOUNT_ID`,
    `transactions`.`DATE`,
    `transactions`.`PAYEE`,
    `transactions`.`TYPE`,
    `transactions`.`AMOUNT`,
    `transactions`.`MEMO`
FROM `bank`.`transactions` WHERE date BETWEEN CAST(CONCAT(@START_YEAR,'-07-01') AS DATE) AND CAST(CONCAT(@END_YEAR,'-06-30') AS DATE) order by 'amount'
INTO OUTFILE 'C:\\Users\\ec\\Desktop\\Expenses\\EComberExpenses_2007-2008_ByAmount.csv'
FIELDS TERMINATED BY ','
ENCLOSED BY '"' 
LINES TERMINATED BY '\n';
