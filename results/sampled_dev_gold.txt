SELECT DISTINCT T1.name FROM Sailors AS T1 JOIN Reserves AS T2 ON T1.sid  =  T2.sid WHERE  T2.bid  =  103	boat_1
SELECT T1.name FROM Sailors AS T1 JOIN Reserves AS T2 ON T1.sid  =  T2.sid JOIN Boats AS T3 ON T3.bid  =  T2.bid WHERE T3.name  =  'Melon'	boat_1
SELECT avg(Units_sold_Millions) FROM game AS T1 JOIN game_player AS T2 ON T1.Game_ID  =  T2.Game_ID JOIN player AS T3 ON T2.Player_ID  =  T3.Player_ID WHERE T3.Position  =  "Guard"	video_game
SELECT DISTINCT T4.Collection_Name FROM Collection_Subset_Members AS T1 JOIN Collection_Subset_Members AS T2 ON T1.Related_Collection_ID = T2.Collection_ID JOIN Collections AS T3 ON T1.Collection_ID = T3.Collection_ID JOIN Collections AS T4 ON T2.Collection_ID = T4.Collection_ID WHERE T3.Collection_Name = "Best";	cre_Doc_and_collections
SELECT analytical_layer_type_code FROM analytical_layer GROUP BY analytical_layer_type_code ORDER BY count(*) DESC LIMIT 1	government_shift
SELECT Nationality ,  COUNT(*) FROM customer GROUP BY Nationality	restaurant_bills
SELECT T1.customer_id ,  T2.customer_name ,  T2.customer_phone ,  T2.customer_email FROM Customer_orders AS T1 JOIN Customers AS T2 ON T1.customer_id  =  T2.customer_id GROUP BY T1.customer_id ORDER BY count(*) DESC LIMIT 1	customers_and_orders
SELECT name FROM staff WHERE age  >  (SELECT avg(age) FROM staff)	conference
SELECT T1.invoice_id ,  T2.invoice_status ,  T2.invoice_details FROM Payments AS T1 JOIN Invoices AS T2 ON T1.invoice_id  =  T2.invoice_id GROUP BY T1.invoice_id ORDER BY count(*) DESC LIMIT 1	advertising_agencies
SELECT product_name FROM Products WHERE product_price  >  (SELECT avg(product_price) FROM Products)	customers_and_orders
SELECT sum(T1.Weight) FROM PACKAGE AS T1 JOIN Client AS T2 ON T1.Sender  =  T2.AccountNumber WHERE T2.Name  =  "Leo Wong";	planet_1
SELECT pilot_name ,  age FROM pilotskills WHERE plane_name  =  'Piper Cub' AND age  >  35 UNION SELECT pilot_name ,  age FROM pilotskills WHERE plane_name  =  'F-14 Fighter' AND age  <  30	pilot_1
SELECT client_id FROM Invoices GROUP BY client_id HAVING count(*)  >=  2	advertising_agencies
SELECT DISTINCT T1.Document_Subset_Name FROM Document_Subsets AS T1 JOIN Document_Subset_Members AS T2 ON T1.Document_Subset_ID =  T2.Document_Subset_ID JOIN Document_Objects AS T3 ON T2.Document_Object_ID  =  T3.Document_Object_ID WHERE T3.owner  =  'Braeden'	cre_Doc_and_collections
SELECT avg(distance) FROM Direct_distance AS T1 JOIN City AS T2 ON T1.city1_code  =  T2.city_code WHERE T2.city_name  =  "Boston"	address_1
SELECT count(DISTINCT T1.code) FROM movies AS T1 JOIN movietheaters AS T2 ON T1.code  =  T2.movie	movie_2
SELECT T2.age_category_code FROM Ref_User_Categories AS T1 JOIN Users AS T2 ON T1.user_category_code  =  T2.user_category_code WHERE T1.User_category_description LIKE "%Mother";	real_estate_rentals
SELECT isbn ,  count(*) FROM Books_Order GROUP BY isbn	book_1
SELECT T1.pilot_name FROM pilotskills AS T1 JOIN hangar AS T2 ON T1.plane_name  =  T2.plane_name WHERE T2.location  =  "Austin" INTERSECT SELECT T1.pilot_name FROM pilotskills AS T1 JOIN hangar AS T2 ON T1.plane_name  =  T2.plane_name WHERE T2.LOCATION  =  "Boston"	pilot_1
SELECT t1.name ,  t1.gender FROM author AS t1 JOIN book AS t2 ON t1.author_id  =  t2.author_id GROUP BY t2.author_id ORDER BY count(*) DESC LIMIT 1	book_press
SELECT count(DISTINCT T1.pilot_name) FROM pilotskills AS T1 JOIN hangar AS T2 ON T1.plane_name  =  T2.plane_name WHERE T2.location  =  'Chicago'	pilot_1
SELECT t1.customer_details FROM customers AS t1 JOIN customers_and_services AS t2 ON t1.customer_id  =  t2.customer_id GROUP BY t1.customer_details ORDER BY count(*) DESC LIMIT 1	government_shift
SELECT T3.CustomerId FROM goods AS T1 JOIN items AS T2 ON T1.id  =  T2.item JOIN receipts AS T3 ON T2.receipt  =  T3.ReceiptNumber GROUP BY T3.CustomerId HAVING avg(T1.price)  >  5	bakery_1
SELECT product_name FROM Products EXCEPT SELECT T1.product_name FROM Products AS t1 JOIN Order_items AS T2 ON T1.product_id  =  T2.product_id	customers_and_orders
select document_object_id , count(*) from document_subset_members group by document_object_id having count(*) between 2 and 4;	cre_Doc_and_collections
SELECT T1.detention_type_code ,  T2.detention_type_description FROM Detention AS T1 JOIN Ref_Detention_Type AS T2 ON T1.detention_type_code  =  T2.detention_type_code GROUP BY T1.detention_type_code ORDER BY count(*) ASC LIMIT 1	cre_Students_Information_Systems
SELECT Student_Answer_Text FROM Student_Answers GROUP BY Student_Answer_Text ORDER BY COUNT(*) DESC	online_exams
SELECT Collection_Name FROM Collections EXCEPT SELECT T2.Collection_Name FROM Collections AS T1 JOIN Collections AS T2 ON T1.Parent_Collection_ID = T2.Collection_ID;	cre_Doc_and_collections
SELECT T1.Name ,  T2.Dish_Name FROM customer AS T1 JOIN customer_order AS T2 ON T1.Customer_ID  =  T2.Customer_ID	restaurant_bills
SELECT T1.lname ,  T1.fname FROM artists AS T1 JOIN paintings AS T2 ON T1.artistID  =  T2.painterID EXCEPT SELECT T3.lname ,  T3.fname FROM artists AS T3 JOIN sculptures AS T4 ON T3.artistID  =  T4.sculptorID	art_1
SELECT T2.Email_Adress ,  T1.Date_of_Answer FROM Student_Answers AS T1 JOIN Students AS T2 ON T1.Student_ID  =  T2.Student_ID ORDER BY T1.Date_of_Answer DESC	online_exams
SELECT T2.Transmitter ,  COUNT(*) FROM city_channel_radio AS T1 JOIN radio AS T2 ON T1.Radio_ID  =  T2.Radio_ID GROUP BY T2.Transmitter	tv_shows
SELECT count(T1.pilot_name) ,  avg(T1.age) ,  T2.location FROM pilotskills AS T1 JOIN hangar AS T2 ON T1.plane_name  =  T2.plane_name GROUP BY T2.location	pilot_1
SELECT T3.name FROM Paper AS T1 JOIN Author_list AS T2 ON T1.paper_id  =  T2.paper_id JOIN Affiliation AS T3 ON T2.affiliation_id  =  T3.affiliation_id WHERE T1.year  =  2009 GROUP BY T2.affiliation_id ORDER BY count(*) DESC LIMIT 3	aan_1
SELECT T1.start_date_time ,  T1.end_date_time ,  T2.client_details ,  T4.staff_details FROM meetings AS T1 JOIN clients AS T2 ON T1.client_id  =  T2.client_id JOIN staff_in_meetings AS T3 ON T1.meeting_id  =  T3.meeting_id JOIN staff AS T4 ON T3.staff_id  =  T4.staff_id	advertising_agencies
SELECT T2.First_Name ,  T1.Date_of_Answer FROM Student_Answers AS T1 JOIN Students AS T2 ON T1.Student_ID  =  T2.Student_ID	online_exams
SELECT count(DISTINCT T1.pilot_name) FROM pilotskills AS T1 JOIN hangar AS T2 ON T1.plane_name  =  T2.plane_name WHERE T2.location  =  'Chicago'	pilot_1
SELECT DISTINCT T1.title FROM book AS T1 JOIN books_order AS T2 ON T1.isbn  =  T2.isbn	book_1
SELECT T1.date_of_transcript FROM Transcripts AS T1 JOIN Student_Loans AS T2 ON T1.student_id  =  T2.student_id ORDER BY T2.amount_of_loan DESC LIMIT 1	cre_Students_Information_Systems
SELECT agency_id FROM Agencies EXCEPT SELECT agency_id FROM Clients	advertising_agencies
SELECT conference_name ,  count(*) FROM conference GROUP BY conference_name	conference
SELECT DISTINCT OWNER FROM Document_Subset_Members AS T1 JOIN Document_Objects AS T2 ON T1.Related_Document_Object_ID  =  T2.Document_Object_ID WHERE T2.Owner  =  'Braeden';	cre_Doc_and_collections
SELECT sum(population) ,  avg(population) FROM district WHERE district_id IN (SELECT district_id FROM spokesman_district)	district_spokesman
SELECT pilot_name FROM pilotskills WHERE plane_name  =  'Piper Cub' EXCEPT SELECT pilot_name FROM pilotskills WHERE plane_name  =  'B-52 Bomber'	pilot_1
SELECT T1.conference_name FROM Conference AS T1 JOIN Conference_participation AS T2 ON T1.conference_id  =  T2.conference_id GROUP BY T2.conference_id ORDER BY count(*) DESC LIMIT 2	conference
SELECT sum(value) ,  count(*) ,  CONTENTS FROM boxes GROUP BY CONTENTS	warehouse_1
SELECT T1.PackageNumber ,  max(T1.Weight) FROM PACKAGE AS T1 JOIN Client AS T2 ON T1.Sender  =  T2.AccountNumber WHERE T2.Name LIKE "John";	planet_1
SELECT DISTINCT T2.stage_presence FROM songs AS T1 JOIN performance_score AS T2 ON T1.id  =  T2.songs_id WHERE T1.language  =  'English'	sing_contest
SELECT T2.First_Name ,  T1.Date_of_Answer FROM Student_Answers AS T1 JOIN Students AS T2 ON T1.Student_ID  =  T2.Student_ID	online_exams
SELECT avg(age) ,  plane_name FROM pilotskills GROUP BY plane_name	pilot_1
SELECT T2.width_mm FROM artists AS T1 JOIN paintings AS T2 ON T1.artistID  =  T2.painterID WHERE T1.birthYear  <  1850	art_1
SELECT Neighborhood FROM store EXCEPT SELECT t1.Neighborhood FROM store AS t1 JOIN stock AS t2 ON t1.store_id  =  t2.store_id	headphone_store
SELECT T1.Title FROM game AS T1 JOIN platform AS T2 ON T1.Platform_ID  =  T2.Platform_ID WHERE T2.Market_district  =  "Asia" OR T2.Market_district  =  "USA"	video_game
SELECT T1.bio_data ,  T1.student_details FROM Students AS T1 JOIN Student_Loans AS T2 ON T1.student_id  =  T2.student_id WHERE T2.amount_of_loan  >  ( SELECT avg(amount_of_loan) FROM Student_Loans )	cre_Students_Information_Systems
SELECT name FROM Client EXCEPT SELECT T1.name FROM Client AS T1 JOIN Orders AS T2 ON T1.idClient  =  T2.idClient	book_1
SELECT make FROM team GROUP BY team HAVING count(*)  >  1	car_racing
SELECT sum(capacity) ,  avg(capacity) ,  max(capacity) ,  LOCATION FROM warehouses GROUP BY LOCATION	warehouse_1
SELECT Player_name FROM player WHERE Player_ID NOT IN (SELECT Player_ID FROM game_player)	video_game
SELECT T1.meeting_id ,  T1.meeting_outcome ,  T1.meeting_type ,  T2.client_details FROM meetings AS T1 JOIN clients AS T2 ON T1.client_id  =  T2.client_id	advertising_agencies
SELECT TYPE FROM book GROUP BY TYPE HAVING COUNT(*)  >=  3	book_review
SELECT DISTINCT T1.birthYear FROM artists AS T1 JOIN sculptures AS T2 ON T1.artistID  =  T2.sculptorID WHERE T2.year  >  1920	art_1
SELECT author_name FROM Documents GROUP BY author_name HAVING count(*)  >=  2	cre_Doc_Workflow
SELECT earpads FROM headphone GROUP BY earpads ORDER BY count(*) DESC LIMIT 2	headphone_store
SELECT T1.fname ,  count(*) FROM artists AS T1 JOIN paintings AS T2 ON T1.artistID  =  T2.painterID GROUP BY T2.painterID HAVING count(*)  >=  2	art_1
SELECT Country FROM player GROUP BY Country HAVING COUNT(*)  >  1	soccer_3
SELECT analytical_layer_type_code FROM analytical_layer GROUP BY analytical_layer_type_code ORDER BY count(*) DESC LIMIT 1	government_shift
SELECT T1.name FROM staff AS T1 JOIN conference_participation AS T2 ON T1.staff_id  =  T2.staff_id WHERE T2.role  =  'Speaker' INTERSECT SELECT T1.name FROM staff AS T1 JOIN conference_participation AS T2 ON T1.staff_id  =  T2.staff_id WHERE T2.role  =  'Sponsor'	conference
SELECT construction ,  avg(price) FROM headphone GROUP BY construction	headphone_store
SELECT Manufacturer FROM club GROUP BY Manufacturer ORDER BY COUNT(*) DESC LIMIT 1	soccer_3
SELECT state FROM Student AS T1 JOIN City AS T2 ON T1.city_code  =  T2.city_code WHERE T1.Fname  =  "Linda"	address_1
SELECT DISTINCT T1.Name FROM driver AS T1 JOIN vehicle_driver AS T2 ON T1.driver_id  =  T2.driver_id JOIN vehicle AS T3 ON T2.vehicle_id  =  T3.vehicle_id WHERE T3.power  >  5000	vehicle_driver
SELECT count(DISTINCT T1.driver_id) FROM vehicle_driver AS T1 JOIN vehicle AS T2 ON T1.vehicle_id  =  T2.vehicle_id WHERE T2.build_year  =  2012	vehicle_driver
SELECT DISTINCT T1.birthYear FROM artists AS T1 JOIN sculptures AS T2 ON T1.artistID  =  T2.sculptorID WHERE T2.year  >  1920	art_1
SELECT T2.code FROM boxes AS T1 JOIN Warehouses AS T2 ON T1.warehouse  =  T2.code GROUP BY T2.code HAVING count(*)  >  T2.capacity	warehouse_1
select count (distinct t2.author_id) from author_list as t1 join author_list as t2 on t1.paper_id  =  t2.paper_id and t1.author_id != t2.author_id join author as t3 on t1.author_id  =  t3.author_id where t3.name = "mckeown ,  kathleen"	aan_1
SELECT T1.code FROM boxes AS T1 JOIN warehouses AS T2 ON T1.warehouse  =  T2.code WHERE T2.location  =  'Chicago' OR T2.location  =  'New York'	warehouse_1
SELECT T1.datestamp ,  T2.property_name FROM User_Property_History AS T1 JOIN Properties AS T2 ON T1.property_id  =  T2.property_id ORDER BY datestamp;	real_estate_rentals
SELECT T1.PackageNumber FROM PACKAGE AS T1 JOIN Client AS T2 ON T1.Recipient  =  T2.AccountNumber WHERE T2.Name = "Leo Wong";	planet_1
SELECT T2.name ,  sum(T1.total_hours) FROM renting_history AS T1 JOIN vehicles AS T2 ON T1.vehicles_id  =  T2.id GROUP BY T2.id	vehicle_rent
SELECT invoice_id ,  count(*) FROM Payments GROUP BY invoice_id	advertising_agencies
SELECT T1.lname ,  T1.fname FROM artists AS T1 JOIN sculptures AS T2 ON T1.artistID  =  T2.sculptorID INTERSECT SELECT T3.lname ,  T3.fname FROM artists AS T3 JOIN paintings AS T4 ON T3.artistID  =  T4.painterID	art_1
SELECT count(*) FROM Products WHERE product_id NOT IN ( SELECT product_id FROM Order_items )	e_commerce
SELECT pilot_name FROM PilotSkills WHERE age  <  (SELECT avg(age) FROM PilotSkills) ORDER BY age	pilot_1
SELECT t3.service_details FROM customers AS t1 JOIN customers_and_services AS t2 ON t1.customer_id  =  t2.customer_id JOIN services AS t3 ON t2.service_id  =  t3.service_id WHERE t1.customer_details  =  "Hardy Kutch"	government_shift
SELECT product_price ,  product_size FROM Products WHERE product_price  >  ( SELECT avg(product_price) FROM Products )	e_commerce
SELECT T2.Rank FROM book AS T1 JOIN review AS T2 ON T1.Book_ID  =  T2.Book_ID ORDER BY T1.Pages ASC LIMIT 1	book_review
SELECT Name FROM club WHERE Club_ID NOT IN (SELECT Club_ID FROM player)	soccer_3
SELECT model FROM headphone WHERE headphone_id NOT IN (SELECT headphone_id FROM stock)	headphone_store
SELECT t1.name ,  t1.internet FROM channel AS t1 JOIN director_admin AS t2 ON t1.channel_id  =  t2.channel_id GROUP BY t1.channel_id ORDER BY count(*) DESC LIMIT 1	bbc_channels
SELECT distance FROM Direct_distance AS T1 JOIN City AS T2 ON T1.city1_code  =  T2.city_code JOIN City AS T3 ON T1.city2_code  =  T3.city_code WHERE T2.city_name  =  "Boston" AND T3.city_name  =  "Newark"	address_1
SELECT T2.name FROM renting_history AS T1 JOIN vehicles AS T2 ON T1.vehicles_id  =  T2.id GROUP BY T2.id ORDER BY sum(T1.total_hours) DESC	vehicle_rent
SELECT DISTINCT T1.name ,  T1.sid FROM Sailors AS T1 JOIN Reserves AS T2 ON T1.sid  =  T2.sid GROUP BY T2.sid HAVING COUNT(*)  >  1	boat_1
SELECT Completed_Year FROM building GROUP BY Completed_Year ORDER BY COUNT(*) DESC LIMIT 1	region_building
SELECT t1.name ,  t1.gender FROM author AS t1 JOIN book AS t2 ON t1.author_id  =  t2.author_id GROUP BY t2.author_id ORDER BY count(*) DESC LIMIT 1	book_press
SELECT T1.agency_id ,  T1.agency_details FROM Agencies AS T1 JOIN Clients AS T2 ON T1.agency_id  =  T2.agency_id GROUP BY T1.agency_id HAVING count(*)  >=  2	advertising_agencies
SELECT T2.Name ,  T1.Nickname FROM championship AS T1 JOIN institution AS T2 ON T1.Institution_ID  =  T2.Institution_ID	institution_sports
SELECT product_color ,  product_description ,  product_size FROM Products WHERE product_price  <  ( SELECT max(product_price) FROM products )	e_commerce
SELECT count(*) FROM Properties GROUP BY property_id HAVING count(*)  >= 2;	real_estate_rentals
SELECT avg(age) ,  Make FROM driver GROUP BY make	car_racing
SELECT food ,  avg(price) ,  max(price) ,  min(price) FROM goods GROUP BY food	bakery_1
SELECT min(price) ,  max(price) ,  food FROM goods GROUP BY food ORDER BY food	bakery_1
SELECT T1.title ,  T1.paper_id FROM Paper AS T1 JOIN Author_list AS T2 ON T1.paper_id  =  T2.paper_id JOIN Author AS T3 ON T2.author_id  =  T3.author_id WHERE T3.name LIKE "%Mckeown ,  Kathleen%" INTERSECT SELECT T1.title ,  T1.paper_id FROM Paper AS T1 JOIN Author_list AS T2 ON T1.paper_id  =  T2.paper_id JOIN Author AS T3 ON T2.author_id  =  T3.author_id WHERE T3.name LIKE "%Rambow ,  Owen%"	aan_1
SELECT T1.address_type_code ,  T2.address_type_description FROM Students_Addresses AS T1 JOIN Ref_Address_Types AS T2 WHERE T1.address_type_code  =  T2.address_type_code GROUP BY T1.address_type_code ORDER BY count(*) DESC LIMIT 1	cre_Students_Information_Systems
SELECT T1.order_id ,  T1.order_status_code ,  count(*) FROM Orders AS T1 JOIN Order_items AS T2 ON T1.order_id  =  T2.order_id GROUP BY T1.order_id	e_commerce
select t1.product_id ,  t1.product_name ,  t1.product_price ,  t1.product_color from products as t1 join order_items as t2 on t1.product_id  =  t2.product_id join orders as t3 on t2.order_id  =  t3.order_id group by t1.product_id having count(*) < 2	e_commerce
SELECT count(DISTINCT LOCATION) FROM boxes AS T1 JOIN warehouses AS T2 ON T1.warehouse  =  T2.code WHERE T1.contents  =  'Rocks'	warehouse_1
SELECT T1.fname ,  count(*) FROM artists AS T1 JOIN paintings AS T2 ON T1.artistID  =  T2.painterID GROUP BY T2.painterID HAVING count(*)  >=  2	art_1
SELECT T1.rank ,  T3.major_name FROM Major_Ranking AS T1 JOIN University AS T2 JOIN Major AS T3 ON T1.university_id  =  T2.university_id AND T1.major_id  =  T3.major_id WHERE T2.university_name  =  'Augustana College'	university_rank
SELECT Name FROM club WHERE Club_ID NOT IN (SELECT Club_ID FROM player)	soccer_3
SELECT state ,  count(*) FROM City GROUP BY state	address_1
SELECT T1.PackageNumber FROM PACKAGE AS T1 JOIN Client AS T2 ON T1.Sender  =  T2.AccountNumber WHERE T2.Name = "Ogden Wernstrom" INTERSECT SELECT T1.PackageNumber FROM PACKAGE AS T1 JOIN Client AS T2 ON T1.Recipient  =  T2.AccountNumber WHERE T2.Name = "Leo Wong"	planet_1
SELECT Name FROM region WHERE Region_ID NOT IN (SELECT Region_ID FROM building)	region_building
SELECT T4.title FROM Orders AS T1 JOIN Books_Order AS T2 ON T1.idOrder  =  T2.idOrder JOIN Client AS T3 ON T1.idClient  =  T3.idClient JOIN book AS T4 ON T2.ISBN  =  T4.isbn WHERE T3.name  =  "Peter Doe" EXCEPT SELECT T4.title FROM Orders AS T1 JOIN Books_Order AS T2 ON T1.idOrder  =  T2.idOrder JOIN Client AS T3 ON T1.idClient  =  T3.idClient JOIN book AS T4 ON T2.ISBN  =  T4.isbn WHERE T3.name  =  "James Smith"	book_1
SELECT earpads FROM headphone EXCEPT SELECT earpads FROM headphone WHERE construction  =  'Plastic'	headphone_store
SELECT T1.Capital FROM country AS T1 JOIN driver AS T2 ON T1.Country_ID  =  T2.Country ORDER BY T2.Points DESC LIMIT 1	car_racing
select t4.name from author_list as t1 join author_list as t2 on t1.paper_id  =  t2.paper_id and t1.author_id != t2.author_id join author as t3 on t1.author_id  =  t3.author_id join author as t4 on t2.author_id  =  t4.author_id where t3.name = "mckeown ,  kathleen" group by t2.author_id order by count(*) desc limit 1	aan_1
SELECT T3.Name FROM PACKAGE AS T1 JOIN Shipment AS T2 ON T1.Shipment = T2.ShipmentID JOIN Planet AS T3 ON T2.Planet = T3.PlanetID GROUP BY T2.Planet HAVING sum(T1.Weight)  >  30;	planet_1
SELECT T3.city_name FROM Direct_distance AS T1 JOIN City AS T2 ON T1.city1_code  =  T2.city_code JOIN City AS T3 ON T1.city2_code  =  T3.city_code WHERE T2.city_name  =  "Boston" ORDER BY distance DESC LIMIT 1	address_1
SELECT T1.feature_name ,  T1.feature_description FROM Features AS T1 JOIN Property_Features AS T2 ON T1.feature_id  =  T2.feature_id GROUP BY T1.feature_name ORDER BY count(*) DESC LIMIT 1;	real_estate_rentals
SELECT T1.title ,  T2.name FROM movies AS T1 JOIN movietheaters AS T2 ON T1.code  =  T2.movie	movie_2
SELECT T1.product_id ,  T1.product_description FROM Products AS T1 JOIN Order_items AS T2 ON T1.product_id  =  T2.product_id GROUP BY T1.product_id HAVING count(*)  >  3	e_commerce
SELECT process_name FROM Business_processes WHERE process_id  =  (SELECT next_process_id FROM Business_processes WHERE process_id  =  9)	cre_Doc_Workflow
SELECT state FROM university WHERE enrollment  <  3000 GROUP BY state HAVING count(*)  >  2	university_rank
SELECT DISTINCT T1.PackageNumber FROM PACKAGE AS T1 JOIN Client AS T2 ON T1.Sender  =  T2.AccountNumber OR T1.Recipient  =  T2.AccountNumber WHERE T2.Name = "Leo Wong"	planet_1
SELECT DISTINCT T2.Document_Object_ID FROM Collections AS T1 JOIN Documents_in_Collections AS T2 ON T1.Collection_ID = T2.Collection_ID WHERE T1.Collection_Name = "Best" EXCEPT SELECT DISTINCT T3.Document_Object_ID FROM Document_Subset_Members AS T3 JOIN Document_Subsets AS T4 ON T3.Document_Subset_ID =  T4.Document_Subset_ID WHERE T4.Document_Subset_Name = "Best for 2000"	cre_Doc_and_collections
SELECT T1.customer_first_name ,  T4.product_name FROM Customers AS T1 JOIN Orders AS T2 ON T1.customer_id  =  T2.customer_id JOIN Order_items AS T3 ON T2.order_id  =  T3.order_id JOIN Products AS T4 ON T3.product_id  =  T4.product_id	e_commerce
SELECT pilot_name ,  plane_name ,  max(age) FROM pilotskills GROUP BY plane_name	pilot_1
SELECT T1.name FROM Affiliation AS T1 JOIN Author_list AS T2 ON T1.affiliation_id  =  T2.affiliation_id GROUP BY T1.affiliation_id ORDER BY count(*) DESC	aan_1
SELECT count(DISTINCT CONTENTS) ,  warehouse FROM boxes GROUP BY warehouse	warehouse_1
SELECT Nationality FROM member WHERE Age  >  22 INTERSECT SELECT Nationality FROM member WHERE Age  <  19	club_leader
SELECT T2.university_name FROM Major_Ranking AS T1 JOIN University AS T2 JOIN Major AS T3 ON T1.university_id  =  T2.university_id AND T1.major_id  =  T3.major_id WHERE T3.major_name  =  'Accounting' INTERSECT SELECT T2.university_name FROM Major_Ranking AS T1 JOIN University AS T2 JOIN Major AS T3 ON T1.university_id  =  T2.university_id AND T1.major_id  =  T3.major_id WHERE T3.major_name  =  'Urban Education'	university_rank
SELECT T1.bio_data FROM Students AS T1 JOIN Behaviour_Monitoring AS T2 ON T1.student_id  =  T2.student_id WHERE T2.behaviour_monitoring_details IN ( SELECT behaviour_monitoring_details FROM Behaviour_Monitoring GROUP BY behaviour_monitoring_details ORDER BY count(*) DESC LIMIT 1 ) EXCEPT SELECT T1.bio_data FROM Students AS T1 JOIN Behaviour_Monitoring AS T2 ON T1.student_id  =  T2.student_id WHERE T2.behaviour_monitoring_details NOT IN ( SELECT behaviour_monitoring_details FROM Behaviour_Monitoring GROUP BY behaviour_monitoring_details ORDER BY count(*) DESC LIMIT 1 )	cre_Students_Information_Systems
SELECT T4.title FROM Orders AS T1 JOIN Books_Order AS T2 ON T1.idOrder  =  T2.idOrder JOIN Client AS T3 ON T1.idClient  =  T3.idClient JOIN book AS T4 ON T2.ISBN  =  T4.isbn WHERE T3.name  =  "Peter Doe" EXCEPT SELECT T4.title FROM Orders AS T1 JOIN Books_Order AS T2 ON T1.idOrder  =  T2.idOrder JOIN Client AS T3 ON T1.idClient  =  T3.idClient JOIN book AS T4 ON T2.ISBN  =  T4.isbn WHERE T3.name  =  "James Smith"	book_1
SELECT meeting_outcome ,  count(*) FROM Meetings GROUP BY meeting_outcome	advertising_agencies
SELECT Name FROM Employee WHERE Salary  >  5000 OR Salary  >  (SELECT avg(salary) FROM employee)	planet_1
SELECT T1.Title FROM game AS T1 JOIN platform AS T2 ON T1.Platform_ID  =  T2.Platform_ID WHERE T2.Market_district  =  "Asia" OR T2.Market_district  =  "USA"	video_game
SELECT T1.Institution_Name ,  T1.location FROM institution AS T1 JOIN staff AS T2 ON T1.institution_id  =  T2.institution_id WHERE T2.staff_id NOT IN (SELECT T4.staff_id FROM Conference AS T3 JOIN Conference_participation AS T4 ON T3.conference_id  =  T4.conference_id WHERE T3.year  =  2004)	conference
SELECT T1.property_type_description ,  T1.property_type_code FROM Ref_Property_Types AS T1 JOIN Properties AS T2 ON T1.property_type_code  =  T2.property_type_code GROUP BY T1.property_type_code ORDER BY count(*) DESC LIMIT 1;	real_estate_rentals
SELECT CONSTRUCTOR FROM driver WHERE Age  <  20 INTERSECT SELECT CONSTRUCTOR FROM driver WHERE Age  >  30	car_road_race
SELECT StuID FROM City AS T1 JOIN Student AS T2 ON T1.city_code  =  T2.city_code WHERE T1.state  =  "PA"  AND T2.sex  =  'F'	address_1
SELECT DISTINCT T2.sid ,  T3.name FROM Boats AS T1 JOIN Reserves AS T2 ON  T1.bid  =  T2.bid JOIN Sailors AS T3 ON T2.sid  =  T3.sid WHERE T1.color  =  'red' OR T1.color  =  "blue"	boat_1
select count(*) from citation as t1 join author_list as t2 on t1.paper_id  =  t2.paper_id join author as t3 on t2.author_id  =  t3.author_id where t3.name = "mckeown ,  kathleen"	aan_1
SELECT T3.name ,  count(*) FROM Citation AS T1 JOIN Author_list AS T2 ON T1.cited_paper_id  =  T2.paper_id JOIN Author AS T3 ON T2.author_id  =  T3.author_id GROUP BY T2.author_id ORDER BY count(*) DESC LIMIT 1	aan_1
SELECT DISTINCT t1.service_details FROM services AS t1 JOIN customers_and_services AS t2 ON t1.service_id  =  t2.service_id WHERE t2.customers_and_services_details  =  "Unsatisfied"	government_shift
SELECT T1.address_details ,  T3.bio_data FROM Addresses AS T1 JOIN Students_Addresses AS T2 ON T1.address_id  =  T2.address_id JOIN Students AS T3 ON T2.student_id  =  T3.student_id	cre_Students_Information_Systems
SELECT Nationality FROM customer GROUP BY Nationality ORDER BY COUNT(*) DESC LIMIT 1	restaurant_bills
SELECT t1.name ,  sum(t2.quantity) FROM store AS t1 JOIN stock AS t2 ON t1.store_id  =  t2.store_id GROUP BY t2.store_id ORDER BY sum(t2.quantity) DESC LIMIT 1	headphone_store
SELECT YEAR FROM conference GROUP BY YEAR ORDER BY count(*) LIMIT 1	conference
SELECT T1.client_id ,  T1.sic_code ,  T1.agency_id FROM clients AS T1 JOIN meetings AS T2 ON T1.client_id  =  T2.client_id GROUP BY T1.client_id HAVING count(*)  =  1 INTERSECT SELECT T1.client_id ,  T1.sic_code ,  T1.agency_id FROM clients AS T1 JOIN invoices AS T2 ON T1.client_id  =  T2.client_id	advertising_agencies
SELECT T1.ShipmentID FROM Shipment AS T1 JOIN Employee AS T2 ON T1.Manager = T2.EmployeeID WHERE T2.Name = "Phillip J. Fry";	planet_1
SELECT avg(value) ,  sum(value) FROM boxes	warehouse_1
SELECT max(Rank_of_the_year) ,  min(Rank_of_the_year) FROM player	video_game
SELECT count(*) FROM customer	restaurant_bills
SELECT model FROM vehicle WHERE power  >  6000 ORDER BY top_speed DESC LIMIT 1	vehicle_driver
select count(*) from sailors where name like 'd%'	boat_1
SELECT name FROM countries ORDER BY education_score DESC	country_language
SELECT count(DISTINCT customers_and_services_details) FROM customers_and_services	government_shift
SELECT count(DISTINCT room_size) FROM Rooms;	real_estate_rentals
SELECT date_of_loan FROM Student_Loans ORDER BY date_of_loan ASC LIMIT 1	cre_Students_Information_Systems
SELECT City ,  Station_name FROM city_channel ORDER BY Station_name ASC	tv_shows
SELECT client_id ,  client_details FROM Clients WHERE sic_code  =  "Bad";	advertising_agencies
SELECT login_name FROM Users WHERE user_category_code  =  'Senior Citizen' ORDER BY first_name	real_estate_rentals
SELECT Name FROM club ORDER BY Name ASC	soccer_3
SELECT Name ,  Nationality FROM member	club_leader
SELECT author_name FROM Documents WHERE document_id  =  4	cre_Doc_Workflow
SELECT max(Age) ,  min(Age) FROM driver	car_road_race
select distinct state from city	address_1
SELECT bio_data FROM Students WHERE student_details LIKE '%Suite%'	cre_Students_Information_Systems
SELECT Name FROM institution ORDER BY Founded ASC	institution_sports
SELECT DISTINCT state FROM City	address_1
SELECT id FROM goods WHERE food  =  "Cookie" OR food  =  "Cake" AND price BETWEEN 3 AND 7	bakery_1
SELECT count(*) FROM Addresses	customers_and_orders
SELECT count(*) FROM Book	book_1
SELECT Document_Subset_Name FROM Document_Subsets;	cre_Doc_and_collections
SELECT count(*) FROM Document_Objects WHERE OWNER = "Marlin";	cre_Doc_and_collections
SELECT Title FROM book ORDER BY Title ASC	book_review
SELECT distance FROM Direct_distance WHERE city1_code  =  "BAL" AND city2_code  =  "CHI"	address_1
SELECT Title ,  Developers FROM game ORDER BY Units_sold_Millions DESC	video_game
SELECT DISTINCT rating FROM movies	movie_2
SELECT PackageNumber ,  Weight FROM PACKAGE WHERE Weight BETWEEN 10 AND 30;	planet_1
SELECT count(*) FROM Boats WHERE color  =  'red'	boat_1
SELECT title ,  LOCATION ,  YEAR FROM paintings WHERE height_mm  >  1000 ORDER BY title	art_1
SELECT avg(amount_of_loan) FROM Student_Loans	cre_Students_Information_Systems
SELECT university_name ,  city ,  state FROM University ORDER BY university_name	university_rank
SELECT CONTENTS FROM boxes ORDER BY value DESC LIMIT 1	warehouse_1
SELECT Name FROM region ORDER BY Area DESC LIMIT 5	region_building
SELECT city1_code ,  city2_code FROM Direct_distance WHERE distance  <  1000	address_1
SELECT top_speed ,  power FROM vehicle WHERE build_year  =  1996	vehicle_driver
SELECT avg(height_mm) ,  avg(width_mm) FROM paintings WHERE medium  =  "oil" AND LOCATION  =  "Gallery 241"	art_1
SELECT avg(justice_score) FROM countries	country_language
SELECT avg(Salary) FROM Employee WHERE POSITION  =  "Intern";	planet_1
SELECT DISTINCT bid FROM Reserves WHERE sid = 1	boat_1
SELECT name ,  Government_website ,  district_id FROM district ORDER BY Population	district_spokesman
SELECT plane_name FROM pilotskills WHERE pilot_name  =  'Jones'  AND age  =  32	pilot_1
SELECT Name FROM region ORDER BY Name ASC	region_building
SELECT paintingID FROM paintings WHERE height_mm  >  500 AND height_mm  <  2000	art_1
SELECT count(*) FROM Citation WHERE paper_id  =  "D12-1027"	aan_1
SELECT count(*) FROM Invoices	advertising_agencies
SELECT Exam_Date FROM Exams WHERE Subject_Code LIKE '%data%' ORDER BY Exam_Date DESC	online_exams
SELECT count(DISTINCT customer_id) FROM Orders	e_commerce
SELECT Exam_Date ,  Exam_Name FROM Exams WHERE Subject_Code != 'Database'	online_exams
SELECT id ,  price FROM goods WHERE id LIKE "%70%"	bakery_1
SELECT DISTINCT conference_name FROM conference	conference
SELECT count(*) FROM race	car_road_race
SELECT name FROM countries ORDER BY overall_score DESC	country_language
SELECT Stadium FROM institution ORDER BY Capacity DESC	institution_sports
SELECT DISTINCT LOCATION FROM paintings WHERE YEAR  <  1885 AND mediumOn != "canvas"	art_1
SELECT Name FROM customer ORDER BY Level_of_Membership ASC	restaurant_bills
SELECT pilot_name FROM PilotSkills ORDER BY age DESC LIMIT 1	pilot_1
SELECT count(*) FROM University WHERE state  =  'Illinois' OR state  =  'Ohio'	university_rank
select title from sculptures order by year desc limit 1	art_1
SELECT name ,  address FROM Client	book_1
SELECT avg(Card_Credit) FROM customer WHERE Level_of_Membership  >  1	restaurant_bills
select title from book order by saleprice asc limit 1	book_1
SELECT count(DISTINCT country) FROM City	address_1
SELECT name FROM driver WHERE citizenship  =  'United States'	vehicle_driver
SELECT Transmitter FROM radio WHERE ERP_kW  >  150 OR ERP_kW  <  30	tv_shows
SELECT Driver_Name FROM driver ORDER BY Driver_Name DESC	car_road_race
SELECT Driver_Name FROM driver WHERE CONSTRUCTOR != "Bugatti"	car_road_race
SELECT count(*) FROM Author	aan_1
SELECT DISTINCT Entrant FROM driver WHERE Age  >=  20	car_road_race
SELECT city1_code ,  city2_code FROM Direct_distance ORDER BY distance DESC LIMIT 1	address_1
SELECT count(*) FROM Customers	customers_and_orders
SELECT count(*) FROM Citation WHERE cited_paper_id  =  "A00-1002"	aan_1
SELECT address_id ,  address_details FROM Addresses	customers_and_orders
SELECT LOCATION FROM hangar ORDER BY plane_name	pilot_1
SELECT max(Rank_of_the_year) ,  min(Rank_of_the_year) FROM player	video_game
SELECT lname ,  fname FROM artists WHERE birthYear  >  1850	art_1
SELECT Collection_Subset_Name FROM Collection_Subsets;	cre_Doc_and_collections
SELECT count(*) FROM Boats WHERE color  =  'red'	boat_1
SELECT achievement_type_code ,  achievement_details ,  date_achievement FROM Achievements	cre_Students_Information_Systems
SELECT count(DISTINCT Payment_method_code) FROM Customer_Payment_Methods	e_commerce
SELECT COUNT (DISTINCT Country) FROM player	soccer_3
SELECT max(saleprice) ,  min(saleprice) FROM Book	book_1
SELECT max(height_mm) ,  paintingID FROM paintings WHERE YEAR  <  1900	art_1
SELECT count(*) FROM Process_status	cre_Doc_Workflow
SELECT product_name FROM Products WHERE product_type_code  =  "Clothes" ORDER BY product_price DESC LIMIT 1	customers_and_orders
SELECT pilot_name FROM pilotskills WHERE age BETWEEN 30 AND 40 ORDER BY age	pilot_1
SELECT pilot_name FROM pilotskills WHERE plane_name  =  'Piper Cub' ORDER BY age LIMIT 1	pilot_1
SELECT max(Number_of_Stories) FROM building WHERE Completed_Year != "1980"	region_building
SELECT name FROM songs ORDER BY name	sing_contest
SELECT author_name ,  other_details FROM Authors	cre_Doc_Workflow
SELECT fname  ,  deathYear - birthYear FROM artists ORDER BY deathYear - birthYear DESC LIMIT 1	art_1
SELECT Transmitter FROM radio ORDER BY ERP_kW DESC LIMIT 1	tv_shows
SELECT max(Chapters) ,  min(Chapters) FROM book	book_review
SELECT name ,  age FROM customers ORDER BY membership_credit DESC LIMIT 1	vehicle_rent
SELECT date_registered FROM Users WHERE login_name  =  'ratione';	real_estate_rentals
SELECT count(*) FROM Paper WHERE venue  =  "NAACL" AND YEAR  =  2000	aan_1
SELECT count(*) FROM paintings WHERE LOCATION  =  "Gallery 240"	art_1
SELECT count(DISTINCT Engine) FROM driver WHERE Age  >  30 OR Age  <  20	car_road_race
SELECT COUNT (DISTINCT Country) FROM player	soccer_3
SELECT count(*) FROM Business_processes	cre_Doc_Workflow
SELECT CONTENTS FROM boxes ORDER BY value DESC LIMIT 1	warehouse_1
SELECT max(weight) ,  min(weight) FROM bike	bike_racing
SELECT product_id ,  product_type_code ,  product_name FROM Products	customers_and_orders
SELECT count(*) FROM institution WHERE founded BETWEEN 1850 AND 1900	conference
SELECT count(*) FROM services	government_shift
SELECT Player_name FROM player ORDER BY Player_name ASC	video_game
SELECT name FROM district WHERE Government_website LIKE "%gov%"	district_spokesman
SELECT OWNER FROM Document_Objects WHERE Description  =  'Braeden Collection'	cre_Doc_and_collections
SELECT title FROM paintings WHERE width_mm  <  600 OR height_mm  >  800	art_1
SELECT title FROM paintings WHERE YEAR  >  1910 AND medium  =  "oil"	art_1
SELECT count(*) FROM Properties WHERE parking_lots  =  1 OR garage_yn  =  1;	real_estate_rentals
SELECT Coordinates FROM Planet WHERE Name  =  "Mars";	planet_1
SELECT Exam_Date ,  Exam_Name FROM Exams WHERE Subject_Code != 'Database'	online_exams
SELECT DISTINCT bid FROM Reserves	boat_1
SELECT count(DISTINCT Comments) FROM Student_Answers	online_exams
SELECT avg(distance) ,  min(distance) ,  max(distance) FROM Direct_distance	address_1
SELECT meeting_type ,  other_details FROM meetings	advertising_agencies
SELECT model ,  CLASS ,  construction FROM headphone ORDER BY price LIMIT 1	headphone_store
SELECT count(DISTINCT student_id) FROM Detention	cre_Students_Information_Systems
SELECT DISTINCT title FROM paintings ORDER BY title	art_1
SELECT count(*) FROM player WHERE Rank_of_the_year  <=  3	video_game
SELECT count(*) FROM Client	book_1
SELECT Name FROM region ORDER BY Area DESC LIMIT 5	region_building
SELECT title FROM movies WHERE rating  =  'G' OR rating  =  'PG'	movie_2
SELECT avg(value) FROM boxes	warehouse_1
SELECT agency_id ,  agency_details FROM Agencies	advertising_agencies
SELECT name ,  age FROM Sailors ORDER BY rating DESC	boat_1
SELECT product_name ,  weight FROM bike ORDER BY price ASC	bike_racing
SELECT count(*) FROM Paper	aan_1
select title from book order by saleprice asc limit 1	book_1
SELECT customer_details FROM customers WHERE customer_details LIKE "%Kutch%"	government_shift
SELECT DISTINCT payment_method_code FROM Customers	customers_and_orders
SELECT count(*) FROM Staff	cre_Doc_Workflow
SELECT count(*) FROM pilotskills WHERE age  >  40	pilot_1
SELECT flavor FROM goods WHERE food  =  "Cake" AND price  >  10	bakery_1
SELECT city_name FROM City WHERE state  =  "PA"	address_1
SELECT count(*) FROM performance_score WHERE stage_presence  <  7 OR stage_presence  >  9	sing_contest
SELECT DISTINCT title FROM paintings ORDER BY height_mm	art_1
SELECT fname  ,  deathYear - birthYear FROM artists ORDER BY deathYear - birthYear DESC LIMIT 1	art_1
SELECT customer_address ,  customer_phone ,  customer_email FROM Customers WHERE customer_name  =  "Jeromy"	customers_and_orders
SELECT paintingID ,  height_mm FROM paintings WHERE LOCATION  =  'Gallery 240' ORDER BY width_mm DESC LIMIT 1	art_1
SELECT count(DISTINCT CONTENTS) FROM boxes	warehouse_1
SELECT count(*) FROM author WHERE age  <  30	book_press
SELECT avg(product_price) FROM Products	e_commerce
SELECT Name FROM player ORDER BY Wins_count ASC	soccer_3
SELECT address_id ,  address_details FROM Addresses	customers_and_orders
SELECT DISTINCT LOCATION FROM paintings WHERE YEAR  < 1885 OR YEAR  >  1930	art_1
SELECT name ,  address FROM Client ORDER BY name	book_1
