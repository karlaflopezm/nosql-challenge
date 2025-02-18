UK Food Standards Database Analysis

Project Overview

The UK Food Standards Agency evaluates various establishments across the United Kingdom and assigns food hygiene ratings. This project involves analyzing the hygiene ratings data to assist the Eat Safe, Love magazine editors and food critics in determining where to focus their articles.

This project is divided into three main parts:

Database and Jupyter Notebook Setup - Import and configure MongoDB.

Updating the Database - Modify and clean the data as per the magazine's requirements.

Exploratory Data Analysis - Answer key questions to guide the magazine's editorial decisions.

Table of Contents

Installation

Usage

Project Breakdown

Part 1: Database and Jupyter Notebook Setup

Part 2: Updating the Database

Part 3: Exploratory Data Analysis

Requirements

Deployment and Submission

License

Installation

Follow these steps to set up the project:

1. Clone the Repository

git clone https://github.com/your-username/uk-food-standards.git
cd uk-food-standards

2. Install Dependencies

Ensure you have Python and MongoDB installed. Install the required Python libraries:

pip install pymongo pandas notebook

3. Import the Data into MongoDB

Run the following command in your terminal to import the data:

mongoimport --db uk_food --collection establishments --drop --file establishments.json --jsonArray

This command:

Creates a database named uk_food

Creates a collection named establishments

Drops any existing establishments collection before importing

Loads the provided JSON dataset

Usage

Start Jupyter Notebook

To run the analysis, start Jupyter Notebook and open the provided .ipynb files:

jupyter notebook

Project Breakdown

Part 1: Database and Jupyter Notebook Setup

Import pymongo and pprint.

Create a MongoDB client instance.

Confirm that the database and collection are properly loaded:

List the databases to confirm uk_food is present.

List the collections within uk_food to ensure establishments is present.

Retrieve and display one document using find_one() and pprint.

Assign the establishments collection to a variable for further use.

Part 2: Updating the Database

The magazine editors requested modifications to the database before analysis. Tasks include:

Adding a New Restaurant:

Insert "Penang Flavours", a new halal restaurant in Greenwich, into the database.

Updating BusinessTypeID:

Find the BusinessTypeID for "Restaurant/Cafe/Canteen" and update "Penang Flavours".

Removing Dover Establishments:

Identify and delete all records from Dover Local Authority.

Data Type Conversions:

Convert latitude and longitude to decimal numbers.

Convert RatingValue to integers.

Part 3: Exploratory Data Analysis

To assist the magazine in its decision-making, we answer these key questions:

Which establishments have a hygiene score of 20?

Which establishments in London have a RatingValue greater than or equal to 4?

Uses $regex to match London authorities.

What are the top 5 highest-rated establishments near "Penang Flavours"?

Sorted by lowest hygiene score.

Located within 0.01 degrees of latitude and longitude.

Which Local Authorities have the most establishments with a hygiene score of 0?

Uses aggregation to group and count.

Results are sorted from highest to lowest.

Requirements

This project requires:

Python 3.x

MongoDB

Jupyter Notebook

Libraries: pymongo, pandas, pprint

Deployment and Submission

To submit your project:

Upload all files to GitHub.

Use the command line to add and commit files:

git add .
git commit -m "Initial commit - UK Food Standards Analysis"
git push origin main

Include appropriate commit messages.

Submit the GitHub repository link.
