# Veterinary Clinic Management System 
This system manages data about pets, their owners, doctors, and receptionists at a veterinary clinic. It allows receptionists to manage and view pet and owner information, while doctors can view medical histories and  treatments. The admin has access to all features, including user management and data reporting.

## Features
- Role-based access for receptionists, doctors, and admin
- Manage pet and owner information
- Manage doctor and receptionist information
- Prescribe treatments and view medical histories
- Dashboard for viewing total number of pets, doctors, and receptionists, and pet species (cat, dog, bird)

## Technology Stack
- SQL Server(SSMS)
- Windows .NET Framework

## Installation
1. Clone the repository
2. Install dependencies
3. Open the solution file in Visual Studio
4. Build and run the solution
5. Run these queries to create the Database PETDB and its tables.

create table RECEPTIONISTS(
rid varchar(10) not null,
rname varchar(50) not null,
rsex varchar(50) not null,
dob date not null,
rphone varchar(10) not null,
raddress varchar(max) not null,
username varchar(50) not null,
password varchar(50) not null

);

create table ADMINS(
username varchar(10) primary key not null ,
password varchar(10) not null
);


create table PETS(
pid varchar(50) primary key not null ,
pet_name varchar(10) not null,
category varchar(10) not null,
sex varchar(10) not null,
age_months varchar(50) not null,
allergies varchar(50) not null,
owner_address varchar(50) not null,
owner_phone varchar(10) not null,
owner_name varchar(50) not null
);


create table DOCTORS(
did varchar(50) primary key not null,
doc_name varchar(50) not null,
username varchar(50) not null,
password varchar(50) not null,
dob date not null,
sex varchar(10) not null,
specialisation varchar(20) not null,
experience_years varchar(10) not null,
doc_address varchar(max) not null,
doc_phone varchar(10) not null
);


create table TREATMENTS(
pid varchar (50) primary key references PETS(pid) on delete cascade on update cascade,
did varchar(50) references DOCTORS(did) on delete set null on update cascade,
diagnosis varchar(max) not null,
tests varchar(max) not null,
medicines varchar(max) not null,
diet varchar(max) not null,
remarks varchar(max) not null,
fees varchar(max) not null
);



## Usage
1. Create receptionist account
3. Login as a receptionist or doctor to manage and view pet/owner information
4. Login as an admin to manage users and view data reports

## Disclaimer
This project is not licensed and is intended for educational purposes only.
