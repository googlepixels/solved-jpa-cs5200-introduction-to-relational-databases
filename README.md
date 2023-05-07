Download Link: https://assignmentchef.com/product/solved-jpa-cs5200-introduction-to-relational-databases
<br>
<span style="font-size: 2.61792em; letter-spacing: -1px; font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen-Sans, Ubuntu, Cantarell, 'Helvetica Neue', sans-serif;">Introduction</span>

Consider the class diagram below. This assignment will map the following classes to equivalent JPA entities: Person, Faculty, Student, Course, Section and Enrollment. Feel free to add additional fields and ​<strong>do not rename the existing variable names. </strong>

<strong> </strong>




<h1>Implement JPA data model (40pts)</h1>

Annotate all classes as JPA entities where appropriate. Name all primary keys as “id” and configure them to auto increment. All JPA entities must have corresponding JPA repositories.

<h2>Implement JPA inheritance</h2>

Create base class Person and derived classes Faculty and Student. Use JPA’s single table strategy to implement the inheritance relationship.

<h2>Implement JPA one to many</h2>

Create classes Course and Section annotating them as JPA entities implementing their one to many relationship using JPA. Also implement the one to many relationship between Faculty and Course.

<h2>Implement JPA many to many</h2>

Create classes Student and Section, annotating them as JPA entities and implementing association class Enrollment as a JPA mapping table between Student and Section.

<h1>Create DAOs for each of the entities (40pts)</h1>

In a class called UniversityDao, create a DAO that implements the following methods. If you prefer, feel free to breakup the DAO into several DAOs. The DAOs must use the JPA repositories implemented earlier. Do not use JDBC. Feel free to modify the signature of the methods if appropriate and create additional methods if needed. Implement the following update methods:




<ol>

 <li>void truncateDatabase() – removes all the data from the database. Note that you might need to remove records in a particular order</li>

 <li>Faculty createFaculty(Faculty faculty)</li>

 <li>Student createStudent(Student student)</li>

 <li>Course createCourse(Course course)</li>

 <li>Section createSection(Section section)</li>

 <li>Course addSectionToCourse(Section section, Course course)</li>

 <li>Course setAuthorForCourse(Faculty faculty, Course course)</li>

 <li>Boolean enrollStudentInSection(Student student, Section section) – enrolls a student in a section updating the number of seats available and returning true. If the current available seats is zero then the enrollment is refused and method returns false</li>

</ol>




Implement the following finder methods




<ol>

 <li>List&lt;Person&gt; findAllUsers()</li>

 <li>List&lt;Faculty&gt; findAllFaculty()</li>

 <li>List&lt;Students&gt; findAllStudents()</li>

 <li>List&lt;Course&gt; findAllCourses()</li>

 <li>List&lt;Section&gt; findAllSections()</li>

 <li>List&lt;Course&gt; findCoursesForAuthor(Faculty faculty)</li>

 <li>List&lt;Section&gt; findSectionForCourse(Course course)</li>

 <li>List&lt;Student&gt; findStudentsInSection(Section section)</li>

 <li>List&lt;Section&gt; findSectionsForStudent(Student student)</li>

</ol>

<h1>Create a test suite that tests your code (20pts)</h1>

Create a test suite that uses the DAO(s) creates earlier to test the JPA data model as follows. All passwords are “password” and all usernames are the lowercase of the corresponding first name

<ol>

 <li>Empty the database – the test suite must remove all data from the database before running the rest of the tests</li>

 <li>Creates faculties – the test suite must insert the following faculties before running the tests in the test suite</li>

</ol>




<table width="576">

 <tbody>

  <tr>

   <td width="151"><strong>First Name </strong></td>

   <td width="144"><strong>Last Name </strong></td>

   <td width="144"><strong>Office </strong></td>

   <td width="137"><strong>Tenured </strong></td>

  </tr>

  <tr>

   <td width="151">Alan</td>

   <td width="144">Turin</td>

   <td width="144">123A</td>

   <td width="137">True</td>

  </tr>

  <tr>

   <td width="151">Ada</td>

   <td width="144">Lovelace</td>

   <td width="144">123B</td>

   <td width="137">True</td>

  </tr>

 </tbody>

</table>




<ol start="10">

 <li>Creates students – the test suite must insert the following students before running the tests in the test suite</li>

</ol>




<table width="576">

 <tbody>

  <tr>

   <td width="151"><strong>First Name </strong></td>

   <td width="144"><strong>Last Name </strong></td>

   <td width="144"><strong>Grad Year </strong></td>

   <td width="137"><strong>Scholarship </strong></td>

  </tr>

  <tr>

   <td width="151">Alice</td>

   <td width="144">Wonderland</td>

   <td width="144">2020</td>

   <td width="137">12000</td>

  </tr>

  <tr>

   <td width="151">Bob</td>

   <td width="144">Hope</td>

   <td width="144">2021</td>

   <td width="137">23000</td>

  </tr>

  <tr>

   <td width="151">Charlie</td>

   <td width="144">Brown</td>

   <td width="144">2019</td>

   <td width="137">21000</td>

  </tr>

  <tr>

   <td width="151">Dan</td>

   <td width="144">Craig</td>

   <td width="144">2019</td>

   <td width="137">0</td>

  </tr>

  <tr>

   <td width="151">Edward</td>

   <td width="144">Scissorhands</td>

   <td width="144">2022</td>

   <td width="137">11000</td>

  </tr>

  <tr>

   <td width="151">Frank</td>

   <td width="144">Herbert</td>

   <td width="144">2018</td>

   <td width="137">0</td>

  </tr>

  <tr>

   <td width="151">Gregory</td>

   <td width="144">Peck</td>

   <td width="144">2023</td>

   <td width="137">10000</td>

  </tr>

 </tbody>

</table>




<ol start="11">

 <li>Create courses – the test suite must create the following courses authored by the faculty shown</li>

</ol>




<table width="576">

 <tbody>

  <tr>

   <td width="105"><strong>Title (Label) </strong></td>

   <td width="35"> </td>

   <td width="60"> </td>

   <td colspan="2" width="376"><strong>Author </strong></td>

  </tr>

  <tr>

   <td width="105">CS1234</td>

   <td width="35"> </td>

   <td width="60"> </td>

   <td colspan="2" width="376">Alan</td>

  </tr>

  <tr>

   <td width="105">CS2345</td>

   <td width="35"> </td>

   <td width="60"> </td>

   <td colspan="2" width="376">Alan</td>

  </tr>

  <tr>

   <td colspan="4" width="295">CS3456</td>

   <td width="281">Ada</td>

  </tr>

  <tr>

   <td colspan="4" width="295">CS4567</td>

   <td width="281">Ada</td>

  </tr>

  <tr>

   <td width="105"></td>

   <td width="35"></td>

   <td width="60"></td>

   <td width="94"></td>

   <td width="281"></td>

  </tr>

 </tbody>

</table>




<ol start="12">

 <li>Create sections – the test suite must insert the following sections for the courses shown</li>

</ol>




<table width="576">

 <tbody>

  <tr>

   <td width="199"><strong>Title </strong></td>

   <td width="192"><strong>Seats </strong></td>

   <td width="185"><strong>Course </strong></td>

  </tr>

  <tr>

   <td width="199">SEC4321</td>

   <td width="192">50</td>

   <td width="185">CS1234</td>

  </tr>

  <tr>

   <td width="199">SEC5432</td>

   <td width="192">50</td>

   <td width="185">CS1234</td>

  </tr>

  <tr>

   <td width="199">SEC6543</td>

   <td width="192">50</td>

   <td width="185">CS2345</td>

  </tr>

  <tr>

   <td width="199">SEC7654</td>

   <td width="192">50</td>

   <td width="185">CS3456</td>

  </tr>

 </tbody>

</table>




<ol start="13">

 <li>Enroll students in sections – the test suite must enroll the following students in the sections shown</li>

</ol>




<table width="576">

 <tbody>

  <tr>

   <td width="100"><strong>Student </strong></td>

   <td width="20"> </td>

   <td width="83"> </td>

   <td width="373"><strong>Section </strong></td>

  </tr>

  <tr>

   <td width="100">Alice</td>

   <td width="20"> </td>

   <td width="83"> </td>

   <td width="373">SEC4321</td>

  </tr>

  <tr>

   <td width="100">Alice</td>

   <td width="20"> </td>

   <td width="83"> </td>

   <td width="373">SEC5432</td>

  </tr>

  <tr>

   <td width="100">Bob</td>

   <td width="20"> </td>

   <td width="83"> </td>

   <td width="373">SEC5432</td>

  </tr>

  <tr>

   <td width="100">Charlie</td>

   <td width="20"> </td>

   <td width="83"> </td>

   <td width="373">SEC6543</td>

  </tr>

 </tbody>

</table>




<h2>Validate data</h2>

<ol start="14">

 <li>Validates uses – write a test that validates the total number of users</li>

 <li>Validates faculty – write a test that validates the total number of faculty</li>

 <li>Validates students – write a test that validates the total number of students</li>

 <li>Validates courses – write a test that validates the total number of courses</li>

 <li>Validates sections – write a test that validates the total number of sections</li>

 <li>Validates Course authorship – write a test that validates the total number of courses authored by each faculty</li>

 <li>Validates Section per Course – write a test that validates the total number of sections per each course</li>

 <li>Validates Section enrollments – write a test that validates the total number of students in each section</li>

 <li>Validates student enrollments – write a test that validates the total number of sections for each student</li>

 <li>Validates Section seats – write a test that validates the number of section seats</li>

</ol>








