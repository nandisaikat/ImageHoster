# ImageHoster
An Image hosting web application that hosts images uploaded by users and allows tagging and writing comments.

## Tech Stack
- Java Springboot
- PostgreSQL
- Spring JPA
- ThymeLeaf
- JUnit

## Pre-requisites
- You must manually create a database named ‘imageHoster’ in PostgreSQL with the user as ‘postgres’ using pgAdmin as the UI.
- Change the username and password in the stub file in the ‘src/main/java/imageHoster/config/JpaConfig.java’ file and ‘src/main/resources/META-INF/persistence.xml’ file according to your PostgreSQL username and password. 

## Compile and Run
```bash
mvn package / mvn install
mvn spring-boot:run
```

## Features
- The application runs on localhost and the user is redirected to the landing page of the application displaying all the images in the application.
- A new user can register in the application by entering the details such as username, password, full name, email address, and mobile number, and after the successful registration, he is redirected to the login page.
- The user can log in the application by entering the username and password, and after successful login to the application, the user is redirected to the user homepage, displaying all the images in the application.
- After a user successfully logs in the application, he can click on the title of any image and the image details will be displayed including the description and tags of the image, along with the option to edit and delete the image.
- A user can also upload the image by entering the details such as image title, description, image file, and tags related to the image.

## New Features
- The application checks for the password strength at the time of user registration. The password must contain at least 1 alphabet (a-z or A-Z), 1 number (0-9) and 1 special character (any character other than a-z, A-Z and 0-9).

## Bugs (Fixed)
- Application throws a HTTP 500 error if there are images with the same title. Resolved by passing the imageId and fetching image data based on imageId instead of imageTitle.
- Application allows users to edit/delete images that has not been uploaded by the user. Resolved by implementing a check for logged in userId and the Image owner userId before allowing edit/delete operations.