# Task Management Application

## Project Description
A full-stack task management application that allows users to create, update, delete, and filter tasks by status. The application is built using React for the front-end, Node.js with Express for the back-end, and MySQL for the database.

## Table of Contents
- [Task Management Application](#task-management-application)
  - [Project Description](#project-description)
  - [Table of Contents](#table-of-contents)
  - [Setup Instructions](#setup-instructions)
    - [Database Setup](#database-setup)
    - [Backend Setup](#backend-setup)
    - [Frontend Setup](#frontend-setup)
  - [Running the Application](#running-the-application)
  - [API Endpoints](#api-endpoints)
  - [Frontend Components](#frontend-components)
  - [How to Run Tests](#how-to-run-tests)
  - [Assumptions and Decisions](#assumptions-and-decisions)
  - [Bonus Features](#bonus-features)

## Setup Instructions

### Database Setup
1. Open MySQL and run the following commands to set up the database:

   ```sql
   CREATE DATABASE task_management;

   USE task_management;

   CREATE TABLE tasks (
       id INT AUTO_INCREMENT PRIMARY KEY,
       title VARCHAR(255) NOT NULL,
       description TEXT,
       status ENUM('To Do', 'In Progress', 'Done') DEFAULT 'To Do',
       created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
       updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
   );
