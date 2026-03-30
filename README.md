# sql-lab-3
Sql lab 3
DROP DATABASE IF EXISTS task1;
CREATE DATABASE task1;
use task1;
CREATE TABLE member(
 mem_id INT,
    mem_nam VARCHAR(50) NOT NULL UNIQUE,
    mem_age INT CHECK (mem_age>=12) ,
    CONSTRAINT pk_member PRIMARY KEY(mem_id)
    );
    CREATE TABLE book(
       mem_id INT,
        book_nam VARCHAR(20) NOT NULL,
        book_id INT,
        CONSTRAINT pk_book PRIMARY KEY(book_id),
        CONSTRAINT fk_book FOREIGN KEY(mem_id) REFERENCES member(mem_id)
        );
        INSERT INTO member VALUES
        (170,'sabit',22),
        (171,'mona',21),
        (178,'asif',20);
        INSERT INTO book VALUES
        (170,'phy',2),
        (178,'oo',11),
        (171,'eng',12);
        SELECT
        m.mem_id,
        m.mem_nam,
        b.book_nam
        FROM member m
        JOIN book b ON m.mem_id = b.mem_id;
        
        
