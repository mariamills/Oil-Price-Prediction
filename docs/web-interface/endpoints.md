# Web Interface: Endpoints Documentation
The web interface for our oil price prediction and analysis tool is powered by a Flask application, providing a series of endpoints to interact with the underlying data and models. Below is a documentation of the current endpoints and their functionalities.

1. ### Home Page Endpoint (`/`)
     - **Method**: GET
     - **Description**: This endpoint renders the home page of the web interface.
     - **Response**: HTML content of the `index.html` page.
2. ### Feature Names Endpoint (`/features`)
    - **Method**: GET
    - **Description**: This endpoint provides the names of the features available in the dataset, which are used to populate the dropdown menu in the user interface.
    - **Response**: A JSON array of feature names.
3. ### Data Endpoint (`/data`)
    - **Method**: POST
    - **Description**: This endpoint filters the dataset based on the selected features received in the request and returns the filtered data.
    - **Request Body**: A JSON object with a key `selected_features` containing an array of selected feature names.
    - **Response**: A JSON object representing the filtered dataset.
4. ### Plot Endpoint (`/plot`)
    - **Method**: POST
    - **Description**: This endpoint generates a plot based on the selected features and plot type. It returns the plot and its legend as base64-encoded PNG images.
    - **Request Body**: A JSON object with keys `selected_features` (array of feature names) and `plot_type` (string specifying the type of plot, e.g., 'line' or 'scatter').
    - **Response**: A JSON object with keys `plot_url` and `legend_url`, containing base64-encoded PNG images of the plot and legend, respectively.
5. ### Data Explorer Page Endpoint (`/data_explorer`)
    - **Method**: GET
    - **Description**: This endpoint renders the Data Explorer page of the web interface.
    - **Response**: HTML content of the `data_explorer.html` page.
6. ### Prediction Page Endpoint (`/predict`)
    - **Method**: GET
    - **Description**: This endpoint renders the Prediction page of the web interface.
    - **Response**: HTML content of the `predict.html` page.
   
### Usage Example:
- To retrieve feature names:
    - Access the `/features` endpoint.

## Conclusion
These endpoints collectively form the backbone of the web interface, enabling users to interactively explore data, generate plots, and perform predictions. The Flask application ensures that these functionalities are seamlessly integrated, providing a user-friendly experience.