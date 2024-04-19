<h1>Database Management System (DBMS):</h1>
<h3><li>Database Normalization in Relational Schema</li></h3>
<p>

Database normalization is a technique of organizing the data into multiple related narrower tables with the purpose of minimizing DATA REDUNDANCY.<br>

<strong> Advantages of data normalization: </strong><br>
1) Improving overall database organization<br>
2) Increasing data consistency<br>
3) Reducing redundancy<br>
4) Reducing data management cost<br>
5) Making it easier to deal with larger amounts of data<br>


<strong> Types of data normalization: </strong><br>
<br>
<img src="./nf.png" width="250"/><br>

1- First normal form (1NF):<br>
1) Each row in the table have a unique identifier (primary key).<br>
2) Each cell in the table hold an atomic (indivisible) value.<br>
</ul>
2- Second normal form (2NF):<br>
<ul>
1) The table should be in the 1st normal form.<br>
2) There should be a <strong>Functional Dependency (FD)</strong> between the PK and every non-key column in the table. There should be <ins>no <strong>Partial Dependencies</strong></ins> in the table.<br>
<ul>
&rarr;&rarr; What is <strong>Functional Dependency (FD)</strong>?<br>
A functional dependency (FD) is a relationship between two attributes, typically between the primary key (PK) and other non-key attributes within a table. For any relation R, attribute Y is functionally dependent on attribute X (usually the PK), if for every valid instance of X, that value of X uniquely determines the value of Y.

</br>

        X ———–> Y
        In above example X is the determinant and Y is the dependent.

        SIN ———-> Name, Address, DoB
        A given valid SIN number determines the value of name, address and date of birth.

&rarr;&rarr; What is <strong>Partial Dependency</strong>? <br>
A partial dependency exists when a non-primary column depends upon a single column that is a part of <strong>a composite primary key</strong>. Note <ins>partial dependency cannot occur when there is a simple primary key.</ins>


        student_id      subject_id      marks   teacher_name
        10              1               70      Java Teacher
        10              2               75      C++ Teacher
        11              1               80      Java Teacher


In the above table, student_id and subject_id forms a composite primary key. If you need to get the mark for the students_id 10 you need to enter the subject_id too. Therefore, we need student_id + subject_id to uniquely identify any row. However, teacher_name depends only on subject_id, this causes partial dependency.

{student_id + subject_id} (composite primary key) → {marks} <br>
{subject_id} → {teacher_name} <br>
<ins>Therefore {subject_id} → {teacher_name} is a partial dependency.</ins><br>
</ul>
</ul>
3- Third normal form (3NF)<br>
<ul>
1- The table should be in the 2nd normal form.<br>
2- There should be <ins>no <strong>Transitive Dependencies</strong></ins> in the table.<br>
<ul>
&rarr;&rarr; What is <strong>Transitive Dependency</strong>?
A transitive dependency exists when you have the following functional dependency pattern.

</br>

        A ———–> B   and   B ———–> C;    therefore A ———–> C

<br>


        Book                                    Genre           Author          Author_Nationality
        Anna Karenina                           fiction         Leo TolstoY     Russian
        Leaves of Grass                         Poetry          Walt Whitman	American
        Journey to the Center of the Earth      Sci-Fi          Jules Verne     French


{Book} → {Author} <br>
{Author} → {Author nationality} <br>
<ins>Therefore {Book} → {Author nationality} is a transitive dependency.</ins><br>
</ul>
</ul>
4- Boyce-Codd normal form (BCNF)<br>
</p>