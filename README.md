# Bike Service Centre

## Overview
This Bike Service Centre application is designed to streamline the process of booking, managing, and reporting on bike services. The application is built using the Frappe framework and includes several DocTypes, webpages, and reports to facilitate efficient service management.

## Table of Contents
- [DocTypes](#doctypes)
  - [Customer](#customer)
  - [Bike](#bike)
  - [Service Booking](#service-booking)
  - [Service Type](#service-type)
  - [Service Technician](#service-technician)
  - [Service Report](#service-report)
- [Reports](#reports)
  - [Daily Service Report](#daily-service-report)
  - [Monthly Revenue Report](#monthly-revenue-report)
  - [Customer Service History](#customer-service-history)
  - [Technician Performance Report](#technician-performance-report)
- [Webpages](#webpages)
  - [Home Page](#home-page)
  - [Book Service Page](#book-service-page)
  - [Service Status Page](#service-status-page)
  - [Customer Portal](#customer-portal)
  - [Admin Panel](#admin-panel)
- [Implementation Steps](#implementation-steps)
  - [Set Up Development Environment](#set-up-development-environment)
  - [Create DocTypes](#create-doctypes)
  - [Develop Forms and Logic](#develop-forms-and-logic)
  - [Design and Implement Reports](#design-and-implement-reports)
  - [Design Webpages](#design-webpages)
  - [Testing and Deployment](#testing-and-deployment)
- [Workflow](#workflow)
  - [Customer Books a Service](#customer-books-a-service)
  - [Service Center Manages Bookings](#service-center-manages-bookings)
  - [Service Technician Completes Service](#service-technician-completes-service)
  - [Customer Checks Status](#customer-checks-status)
  - [Admin Generates Reports](#admin-generates-reports)

## DocTypes

### Customer
- **Fields:** 
  - Customer ID
  - Name
  - Contact Number
  - Email
  - Address
- **Relationships:** One-to-Many with Service Booking

### Bike
- **Fields:** 
  - Bike ID
  - Model
  - Brand
  - Year
  - Customer ID (Link to Customer)
- **Relationships:** 
  - Many-to-One with Customer
  - One-to-Many with Service Booking

### Service Booking
- **Fields:** 
  - Booking ID
  - Customer ID (Link to Customer)
  - Bike ID (Link to Bike)
  - Service Date
  - Service Type
  - Status
- **Relationships:** 
  - Many-to-One with Customer
  - Many-to-One with Bike

### Service Type
- **Fields:** 
  - Service Type ID
  - Name
  - Description
  - Price
- **Relationships:** One-to-Many with Service Booking

### Service Technician
- **Fields:** 
  - Technician ID
  - Name
  - Contact Number
  - Specialization
- **Relationships:** One-to-Many with Service Booking

### Service Report
- **Fields:** 
  - Report ID
  - Service Booking ID (Link to Service Booking)
  - Technician ID (Link to Service Technician)
  - Report Details
  - Service Date
- **Relationships:** 
  - Many-to-One with Service Booking
  - Many-to-One with Service Technician

## Reports

### Daily Service Report
- **Columns:** 
  - Service Date
  - Booking ID
  - Customer Name
  - Bike Model
  - Service Type
  - Technician Name
  - Status

### Monthly Revenue Report
- **Columns:** 
  - Month
  - Total Revenue
  - Number of Services
  - Average Service Cost

### Customer Service History
- **Columns:** 
  - Customer Name
  - Bike Model
  - Service Date
  - Service Type
  - Technician Name
  - Status

### Technician Performance Report
- **Columns:** 
  - Technician Name
  - Number of Services
  - Average Service Time
  - Customer Feedback Score

## Webpages

### Home Page
- Overview of services offered
- Link to book a service

### Book Service Page
- Form to capture customer details:
  - Name
  - Contact Number
  - Email
- Form to capture bike details:
  - Model
  - Brand
  - Year
- Select service type from a dropdown
- Select preferred date and time for service
- Submit button to create a new service booking

### Service Status Page
- Form to enter booking ID or customer ID
- Display the status of the service booking

### Customer Portal
- Login page for customers
- Dashboard showing past and upcoming services
- Option to download service reports

### Admin Panel
- Login page for admin/technicians
- Dashboard showing:
  - Today's bookings
  - Pending services
  - Completed services
- Manage DocTypes (Add/Edit/Delete records)
- Generate and view reports

## Implementation Steps

### Set Up Development Environment
- Install Frappe framework
- Create a new Frappe app
- Set up necessary configurations

### Create DocTypes
- Use Frappe's DocType creation tools to define each DocType
- Set up relationships and validation rules

### Develop Forms and Logic
- Create forms for each DocType
- Implement server-side logic and workflows

### Design and Implement Reports
- Create report queries
- Design report templates
- Implement report generation and export functionality

### Design Webpages
- Use Frappe's web page builder or custom HTML/CSS/JS
- Implement booking logic and form submissions

### Testing and Deployment
- Thoroughly test the application using frappe unit tests
- Set up monitoring and backups

## Workflow

### Customer Books a Service
- The customer visits the booking page and fills out the form
- The system creates a new Service Booking record

### Service Center Manages Bookings
- Admin/technician logs into the admin panel
- Views today's bookings and assigns technicians

### Service Technician Completes Service
- The technician updates the Service Booking status to "In Progress"
- Completes the service and updates the status to "Completed"
- Generates a Service Report

### Customer Checks Status
- The customer visits the status page and enters their booking ID
- The system displays the current status of the service

### Admin Generates Reports
- Admin logs into the admin panel
- Generates and views reports

### Team Members and their contribution
- Aman and Deep
- Aman: I worked on creating doctypes,Admin Panel and Home Page.
- Deep: I worked on all Reports,login/signup,Customer Portal
