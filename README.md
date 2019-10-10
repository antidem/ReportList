# ReportList
WEB API test service (net framework)
Тестовый сервис. Работа с MySQL.

DATABASE info:

connectionString="Datasource=localhost;Database=myprojectdb;uid=root;pwd=ruslan139"

Создание базы, таблицы и заполнение тестовыми данными:

CREATE DATABASE myprojectdb;

USE myprojectdb;
 
CREATE TABLE ReportList
(
    Id int auto_increment primary key,
    Name varchar(30),
    Author varchar(30),
    About varchar(150),
    Year int
);

INSERT INTO ReportList (Name, Author, About, Year) VALUES 
('report56511', 'Tom Rain', 'math report for AI unit', 2011),
('report56671', 'Roy Wilson', 'product report for AI unit', 2008),
('report26598', 'Serg Liman', 'tech report for AI unit', 2009);


Тестовые запросы(через Fiddler):

GET https://localhost:44376/api/Rep/ HTTP/1.1
User-Agent: Fiddler
Host: localhost:44376
Content-Length: 0
content-type: application/json;charset=utf-8



GET https://localhost:44376/api/Rep/2 HTTP/1.1
User-Agent: Fiddler
Host: localhost:44376
Content-Length: 0
content-type: application/json;charset=utf-8



POST https://localhost:44376/api/Rep/ HTTP/1.1
User-Agent: Fiddler
Host: localhost:44376
Content-Length: 89
content-type: application/json;charset=utf-8

{Name : "report8755", Author : "Gordon Freeman", About : "BlackMesa unit", Year : "1996"}


PUT https://localhost:44376/api/Rep/4 HTTP/1.1
User-Agent: Fiddler
Host: localhost:44376
Content-Length: 111
content-type: application/json;charset=utf-8

{Id : "4", Name : "report8755", Author : "Gordon Freeman", About : "BlackMesa unit new edition", Year : "1996"}


DELETE https://localhost:44376/api/Rep/4 HTTP/1.1
User-Agent: Fiddler
Host: localhost:44376
Content-Length: 0
content-type: application/json;charset=utf-8
