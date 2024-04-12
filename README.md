# Lego Analysis Challenge

Here is my solution to this challenge:

### Table Creation and Replacement:
I used the CREATE OR REPLACE TABLE statements to create tables in my schema. This technique ensures that if the table already exists, it will be replaced with the new definition, which is useful for managing schema changes or updating table structures without causing conflicts.

Example:


    CREATE OR REPLACE TABLE TIL_PORTFOLIO_PROJECTS.nad_lego_project.lego_colors (
    
    ID NUMBER(4,0),
    
    NAME VARCHAR(28),
    
    RGB VARCHAR(6), 
    
    IS_TRANS VARCHAR(1)
    
    );


### Data Insertion from Staging Tables:
I used the INSERT INTO ... SELECT ... FROM ... statements to populate my newly created tables with data from staging tables. This technique allows me to transfer data efficiently between tables and schemas, facilitating data migration or consolidation processes.

Example:


    INSERT INTO TIL_PORTFOLIO_PROJECTS.nad_lego_project.lego_colors
    
    SELECT *
    
    FROM  TIL_PORTFOLIO_PROJECTS.STAGING.LEGO_COLORS;


### Defining Primary and Foreign Keys:
I used ALTER TABLE statements to add primary and foreign key constraints to my tables. This technique ensures data integrity by enforcing uniqueness and referential integrity between related tables, which is crucial for maintaining data consistency and accuracy.

Example:


    ALTER TABLE lego_inventories ADD PRIMARY KEY (id);
    
    ALTER TABLE lego_inventory_sets ADD FOREIGN KEY (inventory_id) REFERENCES lego_inventories(id);

    These techniques demonstrate fundamental operations in database management, including table creation, data manipulation, and defining constraints for data integrity.
