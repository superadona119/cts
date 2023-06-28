**Instructions:**
1. Fork this repository to create your own copy.
2. Complete the code test within 45 minutes.
3. The code test consists of 10 multiple-choice questions and one OOP code challenge.
4. For multiple-choice questions, select the correct option (a, b, c, or d).
5. For the OOP code challenge, write the code based on the given requirements using an object-oriented approach.
6. Modify the `README.md` file to provide your answers and code solution.
7. Commit your changes to your forked repository.
8. Once you've completed the code test, share the link to your forked repository for evaluation.
9. You have 45 minutes to complete the test.
10. Good luck!

**Multiple-Choice Questions:**

1. Explain the difference between `wp_query()` and `get_posts()` in WordPress.
   - [ ] a) `wp_query()` is used for complex queries, while `get_posts()` is used for simpler queries.
   - [ ] b) `wp_query()` returns an instance of `WP_Query`, while `get_posts()` returns an array of post objects.
   - [x] c) `wp_query()` allows more customization options, while `get_posts()` is simpler to use.
   - [ ] d) There is no difference; they can be used interchangeably.

2. What is the purpose of WordPress transients? Give an example use case.
   - [x] a) Transients are used to store temporary data across requests.
   - [ ] b) Transients are used to secure communication between the server and the database.
   - [ ] c) Transients are used to handle user authentication in WordPress.
   - [ ] d) Transients are used to optimize database queries in WordPress.

3. Which of the following statements about custom post types in WordPress is true?
   - [ ] a) Custom post types allow you to create custom database tables in WordPress.
   - [x] b) Custom post types are a way to extend WordPress beyond blog posts and pages.
   - [ ] c) Custom post types are only used for displaying images and media files in WordPress.
   - [ ] d) Custom post types are pre-defined post formats available in WordPress.

4. In WordPress, which file is responsible for displaying the content of a single blog post?
   - [x] a) `single.php`
   - [ ] b) `page.php`
   - [ ] c) `archive.php`
   - [ ] d) `index.php`

5. How can you optimize the performance of a WordPress website? Select all that apply.
   - [x] a) Caching
   - [x] b) Minification of CSS and JavaScript files
   - [x] c) Using a CDN (Content Delivery Network)
   - [x] d) Implementing lazy loading of images

6. What is the difference between a shortcode and a widget in WordPress?
   - [ ] a) Shortcodes are used to create dynamic content, while widgets are used for static content.
   - [x] b) Shortcodes are used in posts and pages, while widgets are used in sidebars and other widget areas.
   - [ ] c) Shortcodes can only be used by administrators, while widgets are available to all users.
   - [ ] d) There is no difference; they can be used interchangeably.

7. What are the main security considerations when developing a WordPress plugin or theme? Select all that apply.
   - [x] a) Validating and sanitizing user input
   - [x] b) Escaping output data
   - [x] c) Using secure coding practices
   - [ ] d) Hiding the WordPress version number

8. Which of the following statements about the `wpdb` class in WordPress is true?
   - [ ] a) The `wpdb` class is used to create custom database tables in WordPress.
   - [x] b) The `wpdb` class is used to interact with the WordPress database using SQL queries.
   - [ ] c) The `wpdb` class is used to implement AJAX functionality in WordPress.
   - [ ] d) The `wpdb` class is used to handle user authentication in WordPress.

9. What is the purpose of the `__construct()` method in a PHP class?
   - [ ] a) It is used to define class constants.
   - [x] b) It is used to initialize class properties.
   - [ ] c) It is used to define static methods.
   - [ ] d) It is used to declare class interfaces.

10. Which of the following statements about namespaces in PHP is true?
    - [ ] a) Namespaces are used to define global variables.
    - [x] b) Namespaces are used to organize classes, functions, and constants into logical groups.
    - [ ] c) Namespaces are used to define CSS styles for HTML elements.
    - [ ] d) Namespaces are used to define database tables in WordPress.


**OOP Code Challenge (WordPress):**

Implement a WordPress plugin using an object-oriented approach that manages a list of employees in a company. The plugin should have the following features:

**Prerequisites:**
- A WordPress environment is set up with the necessary post type and taxonomy already registered for managing employees (e.g., `employees` post type).
- The focus of this code test is on implementing the `Employee` and `Company` classes within a WordPress plugin and their functionalities.

1. Create a class named `Employee` with the following properties:
   - `name` (string): The name of the employee.
   - `position` (string): The position of the employee.
   - `salary` (float): The salary of the employee.

2. Implement the following methods in the `Employee` class:
   - `__construct()`: Initializes the `name`, `position`, and `salary` properties.
   - `get_name()`: Returns the name of the employee.
   - `get_position()`: Returns the position of the employee.
   - `get_salary()`: Returns the salary of the employee.
   - `get_employee_info()`: Returns a formatted string with the employee's name, position, and salary.

3. Create an additional class named `Company` with the following properties:
   - `employees` (array): An array to store instances of the `Employee` class.

4. Implement the following methods in the `Company` class:
   - `add_employee($employee)`: Adds an employee object to the `employees` array.
   - `get_employees()`: Returns the array of employees in the company.
   - `get_employee_count()`: Returns the total number of employees in the company.
   - `get_average_salary()`: Returns the average salary of all employees in the company.

Please provide the complete code for the plugin implementation, including the `Employee` and `Company` classes within the plugin file.

**Submission:**
- Modify the `README.md` file in your forked repository to include your answers to the multiple-choice questions and your code solution to the OOP code challenge.
- Commit and push your changes to your forked repository.
- Share the link to your forked repository for evaluation.


This is code solution.
  
<?php

/**
 * Employee class file
 */

class Employee {
    /**
     * 
     */
    private $name;
    private $position;
    private $salary;

    public function __construct($name, $position, $salary) {
        $this->name = $name;
        $this->position = $position;
        $this->salary = $salary;
    }
    /**
     * Get Name
     */
    public function get_name() {
        return $this->name;
    }
    /**
     * Get Position
     */
    public function get_position() {
        return $this->position;
    }
    /**
     * Get Salary
     */
    public function get_salary() {
        return $this->salary;
    }
    /**
     * Get Employee Information
     */
    public function get_employee_info() {
        return "Name: {$this->name}, Position: {$this->position}, Salary: {$this->salary}";
    }
}


/**
 * Company class file
 */

class Company {
    private $employees = [];

    /**
     * Add Employee
     */
    public function add_employee(Employee $employee) {
        array_push($this->employees, $employee);
    }

    /**
     * Get All Employees
     */
    public function get_employees() {
        return $this->employees;
    }

    /**
     * Get Employee Count
     */
    public function get_employee_count() {
        return count($this->employees);
    }

    /**
     * Get Average Salary
     */
    public function get_average_salary() {
        $total_salary = 0;
        foreach ($this->employees as $employee) {
            $total_salary += $employee->get_salary();
        }
        return $total_salary / $this->get_employee_count();
    }
}


$employee_1 = new Employee('Dusan Simic', 'Manager', 40000.0);
$employee_2 = new Employee('Patrick', 'Norris', 30000.0);

$company = new Company();
$company->add_employee($employee_1);
$company->add_employee($employee_2);

echo 'Total Employees: ' . $company->get_employee_count();
echo 'Average Salary: ' . $company->get_average_salary();

foreach ($company->get_employees() as $employee) {
    echo '<h2>' . $employee->get_employee_info() . '</h2>';
}
