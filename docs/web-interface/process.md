## Our Process: Creating the Web Interface

The development of the web interface for our oil price prediction and analysis tool was a thorough process that involved several stages. We aimed to create an interface that was both user-friendly and easy to navigate, providing users with powerful tools for data exploration, visualization, and prediction. Below is an overview of our development process.

### 1. Planning and Design
- **Objective**: Define the purpose of the web interface, outline the key features, and design the user experience.
- **Actions**:
    - Conducted brainstorming sessions to list down all the potential features and functionalities.
    - Created wireframes to visualize the user interface and user experience.
    - Defined the workflow and interactions for different features.
- **Tools & Resources**: Paper & pencil for wireframing, GitHub for project tracking.

### 2. Setting Up the Development Environment
- **Objective**: Prepare all necessary tools and libraries for development.
- **Actions**:
    - Initialized a new Flask project as the framework for our web application.
    - Set up a virtual environment and installed necessary Python libraries like Pandas, NumPy, and Matplotlib.
    - Configured the development server for local testing.
- **Tools & Resources**: Flask, Conda for environment management, PyCharm as the code editor.

### 3. Data Integration
- **Objective**: Integrate the dataset and ensure it can be accessed and manipulated through the web interface.
- **Actions**:
    - Loaded the oil price dataset into a Pandas DataFrame.
    - Created endpoints in Flask to expose the data to the front end.
    - Ensured data integrity and handled any missing or infinite values.
- **Tools & Resources**: Pandas for data manipulation, Flask for creating API endpoints.

### 4. Developing Core Functionalities
- **Objective**: Implement the main features of the web interface.
- **Actions**:
    - Developed endpoints for data filtering, feature retrieval, and plotting.
    - Implemented the front-end logic to interact with these endpoints.
    - Created dynamic visualizations based on user input.
- **Tools & Resources**: JavaScript for front-end development, Matplotlib for plotting, Flask for API endpoints.

### 5. User Interface Development
- **Objective**: Develop and refine the user interface based on the design wireframes.
- **Actions**:
    - Implemented the layout, navigation, and user input elements.
    - Ensured a responsive design for accessibility on various devices.
    - Conducted user testing to identify and fix usability issues.
- **Tools & Resources**: HTML, CSS, TailwindCSS for styling, JavaScript for interactivity.

### 6. Testing and Debugging
- **Objective**: Ensure that all features work correctly and efficiently.
- **Actions**:
    - Conducted thorough testing of all features and user interactions.
    - Debugged any issues found during testing.
    - Integrated unit testing to ensure code quality and reliability.
    - Implemented continuous integration to automate testing upon code changes.
- **Tools & Resources**: Browser Developer Tools, Flask debugging tools, PyTest for unit testing and GitHub Actions for continuous integration.

### 7. Documentation and Deployment
- **Objective**: Prepare documentation for users and deploy the web interface.
- **Actions**:
    - Wrote comprehensive documentation on how to use the web interface.
    - Deployed the web application to a web server.
    - Ensured all dependencies were properly configured for deployment.
- **Tools & Resources**: GitHub Pages for deployment of documentation, Render for deployment of web application. MkDocs for documentation.

### 8. Continuous Improvement and Updates
- **Objective**: Keep the web interface up-to-date and continuously improve based on user feedback.
- **Actions**:
    - Implemented updates and new features as required.
    - Conducted regular performance and security audits.
- **Tools & Resources**: GitHub for version control.

### Conclusion
The development of the web interface is an ongoing collaborative effort that requires careful planning, development, and testing. By following this structured process, we were able to create an interface that is not only functional but also intuitive and user-friendly. The source code and additional documentation can be found on our [GitHub repository](https://github.com/mariamills/Oil-Price-Prediction-ML){:target="_blank"}.
