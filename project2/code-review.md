# Code Review for Melvin Mok (Volenti)

## Project Repo

https://github.com/melvinthemok/volenti

## Review

#### Project Purpose

A volunteering platform on which users can:
    create programs for others to benefit from; and
    browse created programs and sign their loved ones up for any of them.

#### Project Organization

* 3 models:
    * Beneficiary, with fields: 
        * name, gender, age: strings; 
        * guardian and programs array: references to User and Program respectively
    * Program, with fields:
        * name, description, website, imageURL: strings;
        * subject: string with allowed values of disability, education, elderly, environment, health and poverty
        * commitment: five boolean subvalues for daily, weekly, fortnightly, monthly and quarterly
        * admin, guardians, beneficiaries, volunteers: references to User, User, Beneficiary and User respectively, with the latter    three being arrays
    * User, with fields:
        * name, gender, age, email, password: strings;
        * usertypes: three boolean subvalues for admin, guardian and volunteer;
        * createdPrograms, signedTheseBeneficiariesUp,
        * signedTheseBeneficiariesUpToThesePrograms, joinedPrograms:
        * references to Program,Beneficiary,Program and Program respectively, all four being arrays

* Four controllers: 
    * authentication controller;
    * beneficiary controller, with methods:
        * form for new;
        * create beneficiary (signup)
    * profile controller, with a method for showing profile
    * program controller, with methods:
        * show all programs;
        * show one program;
        * create program form;
        * create program;
        * edit admin form;
        * edit admin;
        * add guardian form;
        * add guardian;
        * add volunteer to program;
        * remove volunteer from program;
        * delete program;
        * and remove beneficiary from program.
        
* Views(all ejs):
    * Auth folder: 
        * edit form, login form and signup form
    * Beneficiary folder: 
        * new beneficiary form
    * Profile folder:
        * profile index view, includes info on programs and beneficiaries
    * Program folder:
        * Layout.ejs: 
            * includes navbar and alerts partials
            * adds bootstrap, jquery, tether.js(absolute positioning library)
        * index.ejs which acts as a landing page


#### Features

* User management
    Users can be admins(of programs), guardians or volunteer; beneficiaries are added by users to their own accounts
* Program management
    One can create programs, and browse existing programs to sign up their beneficiaries to them
* View other users
    One can review other users to see what programs they manage; beneficiary information of other users is hidden.
     

#### Areas of Success (Code, Organization)

* Clean and elegant presentation
  * Pleasant appearance of forms and views
* Good encapsulation of code
  * Routers are seperated from controllers, everything follows standard MVC pattern well
* Logical hiding of private information
  * Other users cannot see one's beneficiary information on either a program or user profile views

#### Areas for Improvement (Code, Organization)

* Volunteering for programs not added yet
  * probably as project was quite time-constrained; should be nominally doable as functionality would be similar to already implemented functionality 
* Age selector
  * Might be cleaner to implement as a number input field, admittedly not very significant

## Additional Notes

_Place any additional notes here_
