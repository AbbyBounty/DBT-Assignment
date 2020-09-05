# DAY 13

```C
PRN : 200243020003
```



## Sequence, Index and Synonyms
#### 1. Create a sequence to be used with the primary key column of the DEPT table. The sequence should start at 200 and have a maximum value of 1000. Have your sequence increment by ten numbers. Name the sequence DEPT_ID_SEQ
```sql
CREATE SEQUENCE dept_id_seq
	INCREMENT BY 10 START WITH 20
	MAXVALUE 1000 nocache nocycle;

INSERT INTO department (id)
		values(dept_id_seq.nextval);
```

#### 2. Write a query in a script to display the following information about your sequences: sequence name, maximum value, increment size, and last number. Name the script lab13_2.sql. Run the statement in your script
```sql
SELECT
	sequence_name,
	max_value,
	increment_by,
	last_number
FROM
	user_sequences
WHERE
	sequence_name = upper('dept_id_seq');
```

#### 3. Write a script to insert two rows into the DEPT table. Name your script lab13_3.sql. Be sure to use the sequence that you created for the ID column. Add two departments named Education and Administration. Confirm your additions. Run the commands in your script
```sql
INSERT INTO department
		values(dept_id_seq.nextval, 'Education');
INSERT INTO department
		values(dept_id_seq.nextval, 'Administration');
```

#### 4. Display the indexes and uniqueness that exist in the data dictionary for the EMP table.
```sql
SELECT
	index_name,
	index_type,
	table_name,
	uniqueness
FROM
	user_indexes
WHERE
	table_name = upper('emplo');
```

#### 5. Create a nonunique index on the foreign key column (DEPT_ID) in the EMP table.
```sql
CREATE INDEX dept_id_idx ON emplo (dept_id);
```




