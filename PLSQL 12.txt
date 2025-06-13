CREATE OR REPLACE PROCEDURE salary_by_dept (
  dept   IN  VARCHAR2,
  salary OUT NUMBER
) AS
BEGIN
   CASE LOWER(dept)
    WHEN 'sales' THEN
      salary := 20000;
    WHEN 'admin' THEN
      salary := 30000;
    WHEN 'it' THEN
      salary := 50000;
    ELSE
      salary := 0; 
  END CASE;
END;
/
DECLARE
  dept   VARCHAR2(20) := 'sales'; 
  salary NUMBER;
BEGIN
  salary_by_dept(dept, salary);
  DBMS_OUTPUT.PUT_LINE('Department: ' || dept);
  DBMS_OUTPUT.PUT_LINE('Salary: ' || salary);
END;
/