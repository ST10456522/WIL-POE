READ ME
YouTube Link -  https://youtu.be/b48T4ZKGoDI

Empowering the Nation Web and Mobile App

Project Overview
Empowering the Nation has asked us to develop this product for the local SME that upskills domestic workers and gardeners. We have created a mobile application and website that enables domestic workers and gardeners to view courses, calculate fees with discounts, and contact the organization to enroll. 

Features/Functionalities
Navigation
Responsive Layouts
Quick Links
Display Six-Month courses
Display Six-Weeks courses
Course Details
Fee Calculator
Contact Information
Search Engine Optimization
Error Handling


Tools 
Frontend – Android Studio Kotlin for mobile app, and HTML, CSS with VS code for the web.
Backend: Firebase or equivalent for form handling and data storage.
Design: User Interface (UI) created using Canva.
Version Control: GitHub repository for collaboration and submission.




App Logging
toggleSelection()  Method
Handles the selection/deselection of course and keeps track of them for calculations.


updateAmounts() Function
Calculates and displays the total price of selected courses, including discount and tax.



calculateTotal() Function
Calculates and displays the final payable amount.



Web Log
The selected courses' values will later be used to calculate the total fee.
Discount and other operations (not shown in this snippet) will be applied based on the selected courses.

// Calculate total fee on button click
        document.getElementById('calculateBtn').addEventListener('click', function () {
            const courses = document.querySelectorAll('input[name="course"]:checked');
            let fullAmount = 0;
            let discount = 0;


to compute the total cost of the selected courses before any discounts or taxes are applied.
This forms the base value for further calculations, such as applying discounts or VAT.

// Calculate the full amount of selected courses
            courses.forEach(function(course) {
                fullAmount += parseFloat(course.value);
            });

 Calculates the total cost of selected courses, including discounts and taxes.
 Offers incentives based on the number of courses selected.
 Adds VAT to simulate real-world pricing structures.
 Prepares discountAmount, vatAmount, and finalTotal values for display or further use.

// Apply discount based on the number of selected courses
            const selectedCoursesCount = courses.length;

            if (selectedCoursesCount === 2) {
                discount = 0.05; // 5% discount
            } else if (selectedCoursesCount === 3) {
                discount = 0.10; // 10% discount
            } else if (selectedCoursesCount > 3) {
                discount = 0.15; // 15% discount
            }

            const discountAmount = fullAmount * discount;
            const discountedTotal = fullAmount - discountAmount;

            // Apply VAT (15%)
            const vat = 0.15;
            const vatAmount = discountedTotal * vat;
            const finalTotal = discountedTotal + vatAmount;


 Shows the user the calculated breakdown of the total fee.
  // Display the amounts
            document.getElementById('fullAmount').textContent = fullAmount.toFixed(2);
            document.getElementById('discountAmount').textContent = discountAmount.toFixed(2);
            document.getElementById('vatAmount').textContent = vatAmount.toFixed(2);
            document.getElementById('totalAmount').textContent = finalTotal.toFixed(2);
        });

 Prevents the default submission and allows for controlled behavior, such as validating inputs or processing data before redirection.
 Sends the user to a confirmation or success page after form submission.
 Provides a clear endpoint (the success page) for the user's interaction with the form.

// Handle form submission and redirect to the success page
        document.getElementById('courseForm').addEventListener('submit', function (event) {
            event.preventDefault(); // Prevent form submission
            window.location.href = "success.html"; // Redirect to the success page
        });



Bibliography 

1. The IIE. 2024. Mobile App Scripting [MAST5112/d/p/w]. MODULE MANUAL 2024. The Independent Institute of Education: Unpublished.

2. The IIE. 2024. INTRODUCTION TO PROGRAMMING LOGIC [MODULE 
MANUAL]. The Independent Institute of Education: Unpublished.

3.  Canva. 2024. Canva.com
Available at: https://www.canva.com/   [Accessed: 17 August 2024].

4. Perplexity.ai. 2024. Perplexity (version 2.25.1). [Large language model]. 
Available at: https://www.perplexity.ai/ [Accessed: 17 August 2024].

5. Robles, M. M.2012. ‘Executive Perceptions of the Top 10 Soft Skills Needed in Today’s Workplace’, Business Communication Quarterly, 75(4), pp. 453–465. doi: 10.1177/1080569912460400 
