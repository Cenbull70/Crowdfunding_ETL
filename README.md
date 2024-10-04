# Crowdfunding Data Analysis
This project processes and transforms crowdfunding data from Excel files, extracting and cleaning various data points such as categories, subcategories, campaign details, and contact information. The cleaned data is then exported to CSV files for further analysis or use in other systems.

## Project Structure
The script reads data from Excel files and performs the following tasks:

Category and Subcategory Data Extraction
Extracts categories and subcategories from the crowdfunding_info_df and assigns them unique IDs.
The resulting DataFrames are exported as category.csv and subcategory.csv.

## Campaign DataFrame Creation
Creates a campaign DataFrame with several columns such as cf_id, contact_id, description, goal, pledged, backers_count, and dates.

## The goal and pledged columns are converted to float.
- The launch_date and end_date columns are converted to a datetime format.
- Category and subcategory information is merged into the campaign data.
- The cleaned campaign data is exported as campaign.csv.

## Contacts DataFrame Creation
Two methods are provided to extract contact information:

- Option 1: Using Pandas to parse the contact info field directly.
- Option 2: Using regular expressions (regex) to extract contact ID, name, and email.
- The resulting contact data is exported as contacts.csv.

## File Exports
- category.csv: Contains the unique categories and their corresponding IDs.
- subcategory.csv: Contains the unique subcategories and their corresponding IDs.
- campaign.csv: Contains the details of each crowdfunding campaign with category and subcategory information.
- contacts.csv: Contains the contact information for individuals associated with the campaigns.
## Notes
The script includes both Pandas-based and regex-based solutions for extracting contact information. You can use either based on your preference.
The dates are formatted as YYYY-MM-DD for consistency.

## Crowdfunding Data Management System
This project provides a comprehensive solution for managing crowdfunding data, including campaigns, categories, subcategories, and contacts. The system utilizes a relational database structure to organize and query the data efficiently.

## Database Schema
The database schema models the essential relationships between crowdfunding campaigns, contacts, categories, and subcategories.

### Table Overview
- Category Table
- Holds the unique IDs and names of all categories.
- Columns: category_id, category.

### Subcategory Table
- Contains unique subcategory information linked to categories.
- Columns: subcategory_id, subcategory.

### Contacts Table
- Stores details of individuals (contacts) involved in the crowdfunding campaigns.
- Columns: contact_id, first_name, last_name, email.

### Campaign Table
- Contains the main information for each crowdfunding campaign.
- Linked to contacts, category, and subcategory tables via foreign keys.
- Columns: cf_id, contact_id, company_name, description, goal, pledged, outcome, backers_count, country, currency, launch_date, end_date, category_id, subcategory_id.

### Relationships
- Campaign ↔ Contacts: Each campaign is associated with one contact, defined by the foreign key contact_id.
- Campaign ↔ Category/Subcategory: Each campaign is associated with one category and one subcategory, using the category_id and subcategory_id foreign keys.
