Download Link: https://assignmentchef.com/product/solved-cmput-291-assignment-2-writing-declarative-queries-on-a-relational-database
<br>
<table width="988">

 <tbody>

  <tr>

   <td width="988">The goal of this assignment is to improve your skills of writing declarative queries on a relational database, in general, and also to improve your fluency in SQL (and SQLite).You have been provided with the following relational schema.persons(fname, lname, bdate, bplace, address, phone) births(regno, fname, lname, regdate, regplace, gender, f_fname, f_lname, m_fname, m_lname) marriages (regno, regdate, regplace, p1_fname, p1_lname, p2_fname, p2_lname) vehicles(vin,make,model,year,color)registrations(regno, regdate, expiry, plate, vin, fname, lname) tickets(tno,regno,fine,violation,vdate)demeritNotices(ddate, fname, lname, points, desc)The tables are derived from the specification of Assignment 1 and the names of the tables and columns should give the semantics, except minor differences which are explicit in table definitions, insert statements or queries.Creating the databaseUsing <a href="https://eclass.srv.ualberta.ca/pluginfile.php/5149346/mod_page/content/34/a2-tables.sql?time=1569564409666">the SQL statements provided</a><a href="https://eclass.srv.ualberta.ca/pluginfile.php/5149346/mod_page/content/34/a2-tables.sql?time=1569564409666">,</a> create the above tables in SQLite3 on Lab machines with some data. Here is <a href="https://eclass.srv.ualberta.ca/pluginfile.php/5149346/mod_page/content/34/a2-initial-data.sql?time=1569564429004">a small initial data</a> to get you started.(90 marks) QueriesWrite down the following queries in SQL and run them in SQLite3 over the database created. You will be writing ONE SQL statement for every query (here One SQL statement starts with a SELECT and ends with a semicolon but may include multiple select statements combined in the form of subqueries and/or using set operations). Your SQL queries for questions 1-3 cannot use any of aggregation, grouping, or nesting (set operations are ok). When the query asks for name of a person, it means both first name and last name.1.   Find the names and the phone numbers of persons who have had a 1969 Chevrolet Camaro registered under their names at some point.2.   Find the names of people other than Michael Fox who are born to the same parent as Michael Fox.3.   Find the names of persons who have the same grandfather as Michael Fox. If X and Y denote the grandfathers of Michael Fox (from mother and father sides respectively), then we want to find all grand children of X and Y. The result should exclude Michael Fox.4.   Who is the oldest child of Michael Fox. In case of ties, return all those ties.5.   Find the names of persons who have accumulated 15 or more demerit points within the past two years, i.e. the sum of their demerit points within the past two years is more than 15. Hint: Check out the date and time functions in SQLite.6.   Who is the partner of Michael Fox. In case of multiple marriages, return the one from the latest marriage.Hint: Check out the limit clause for sqlite.You may also find subqueries in the from clause useful.7.   For each color of a car with a registration that does not expire at least for another month, find the average number of tickets issued per registration, the average amount of fine given, and the maximum amount of fine given. Include colors with no tickets in the output with zero counts (if applicable) or null values. Hint: you may find outer join useful.8.   For each year of a car, find the most frequent make and the most frequent car color. In case of ties, list all those ties.</td>

  </tr>

  <tr>

   <td width="988">9.       Create a view called personDetails with columns fname, lname, bdate, bplace, carsowned, and ticketsRcvd. The view includes for each person, fname, lname, bdate, bplace, the number of different cars registered under the person name in the past year, and the number of different tickets given to those registered cars within the past year. Include people who have no cars registered under their names or no tickets with zero values.10.   Using the view created in Q9, for every person who has received at least 3 different tickets within the past year and one of those tickets involves a ‘red light’ violation (i.e. ‘red light’ appears in the violation text, e.g. ‘red light crossing’, ‘crossing red light at 114 St and 87 Ave’), list the name of the person and the make and the model of the car for which the red violation ticket is given.(upto 5 bonus marks for the first 3 people ) Preparing test dataWritten queries should be tested for correctness and bug fixes, very much like programs written in any programming language. For testing, you need to have enough data in your tables such that all your queries are meaningful and non-trivial (e.g. the returned answers are not empty). You are encouraged to share your data with your classmates or use data prepared by them. To make this collaboration happen, there will be up to 5 bonus marks (at the instructor’s discretion) to the first 3 people who prepare a test data and share it with the rest of the class. Make sure your data is correct and meets the expectation of the assignment. If you are sharing your test data, please post it to the course discussion forum. Put all your insert statements in a file called a2-data.sql. Make sure to put down your name, email and a date when it is published or revised at the beginning of the file as a comment line (e.g. — Data prepared by &lt;firstname lastname&gt;, &lt;email address&gt;, and published on &lt;date&gt;). If you are using data prepared by someone else, leave the identification line unchanged.(10 marks) Testing and reportStarting from scratch, create your database as

    <table width="951">

     <tbody>

      <tr>

       <td width="951">sqlite3   a2.db   &lt;a2-tables.sql</td>

      </tr>

     </tbody>

    </table>and populate your tables using data file a2-data.sql (prepared in the previous step) as

    <table width="951">

     <tbody>

      <tr>

       <td width="951">sqlite3   a2.db   &lt;a2-data.sql</td>

      </tr>

     </tbody>

    </table>Put all your SQL queries in a file named a2-queries.sql; Add the following line at the beginning of the file

    <table width="951">

     <tbody>

      <tr>

       <td width="951">.echo on</td>

      </tr>

     </tbody>

    </table>and the following line before each SQL query (replacing X with the query number).

    <table width="951">

     <tbody>

      <tr>

       <td width="951">–Question X</td>

      </tr>

     </tbody>

    </table>Run your queries on your data file as

    <table width="951">

     <tbody>

      <tr>

       <td width="951">sqlite3   a2.db   &lt;a2-queries.sql &gt;a2-script.txt</td>

      </tr>

     </tbody>

    </table>You will be submitting both a2-data.sql and a2-script.txt electronically as described in the instructions for submissions.

    <table width="911">

     <tbody>

      <tr>

       <td width="911"></td>

      </tr>

     </tbody>

    </table>


    <table width="911">

     <tbody>

      <tr>

       <td width="911"></td>

      </tr>

     </tbody>

    </table> </td>

  </tr>

 </tbody>

</table>