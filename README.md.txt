test-training

Dmitrieva Tatiana

1203867267
Вывести количество заказов каждого пикера:

SELECT Pickers.name, Pickord.orid FROM (SELECT picker_id AS pid, COUNT (Orders.id) AS orid
FROM Orders 
GROUP BY picker_id) PickOrd
JOIN Pickers ON Pickord.pid = Picker.id

Вывести имя пикера и количество заказов с количеством позиций меньше 10.

SELECT pickers.name, ordpickerID.
(SELECT orders.picker_id, count(positions.order_id)
FROM orders JOIN 
(SELECT Order_id, COUNT (Order_positions.id) AS Ordposid
FROM Order_positions
GROUP BY Order_id
HAVING Ordposid < 10) positions 
ON orders.id = positions.order_id
GROUP BY) ordpickerID


Update from 5.10.20

SELECT FirstName, LastName, City, State
FROM Person p
LEFT JOIN Address ad ON  ad.AddresId = p.PersonID;


# Write your MySQL query statement below
SELECT Employee.Name AS Employee, Salary, Department.Name as Department
FROM Employee

JOIN Department 
ON Department.Id = Employee.DepartmentId
WHERE (Salary, DepartmentId)
 IN
(SELECT max(Salary) AS ms, DepartmentId
FROM Employee
GROUP BY DepartmentId);





















New update 3!