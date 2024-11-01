1. Entities: - For all entities, include Modified By (Person) and Modified On (DateTime) attributes
   - Project: Include attributes such as Title, Description, Start Date, End Date, Priority (Choice: High, Medium, Low), Health (Choice: Null, Green, Yellow, Red, Black), Status Date, Pct Complete, Pct Elapsed Time (Calculated), and Progress Rate (Calculated), Owner (Person or Group), Program, Section, Branch, and Notes (Multi-line text).  Calculate Pct Elapsed Time = If Start Date is in the future or Status Date is null or Status Date is not more recent than Start Date, 0, else (Status Date - Start Date)/(End Date - Start Date).  Calculate Progress Rate = If Pct Elapsed Time = 0, 0, else (Pct Complete / Pct Elapsed Time).
   - Program: Include attributes: Name, Section, Branch.
   - Project Fund: Include attributes: Fund (Lookup), Total Allocation, Amount Spent, Balance (Calculated). Calculate Balance = Total Allocation - Amount Spent.
   - Fund: Include attributes: Name, Fund Manager (Person).
   - User Roles: Include User (Person) and Role (Choice: Admin, User).
 
2. Relationships: 
   - Project has a one-to-many relationship with Project Fund.
   - Project has a many-to-one relationship with Program without cascading operations.
   - Project Fund has a many-to-one relationship with Fund.
 
3. Views and Dashboards:
   - Create view for Project, including filters by Health, Owner, Branch, Section, Program, and Priority.
   - Include a dashboard displaying (a) number/% projects by percentage complete, (b) number/% projects by health, (c) progress rate by project, and (d) fund metric summaries.  
 
4. Forms: 
   - Design user-friendly forms for creating and editing all entities with relevant fields.
   - Ensure that forms reuse components where possible for consistency.
 
5. Business Rules and Automation: 
   - Ensure that the default date for Status Date is null.
   - Ensure that the default for Health is Null, which is used when the project hasn't been started
   - Implement business rules to automatically update Health to Black when the project is 100% complete.
   - Implement cascading dropdowns, where selection of Program automatically fills Section and Branch.
 
6. Security Roles: 
   - Allow users with the Admin role to add, insert, update, and delete records for all entities
   - Allow users with the User role to add, insert, and update Project records
   - Allow users with the User role to add, insert, update, and delete Project Fund records
  
After generating the app, provide a brief summary of how to customize it further for specific needs and how to add additional functionality as necessary.
