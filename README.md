# FakeStoreAPI Cart Test

This project contains automated tests for the cart endpoints of the FakeStoreAPI using Python and pytest. The tests cover common functionalities such as retrieving, adding, updating or deleting carts. 

### Prerequisites ###

- Python 3.8+
- `pip`

### Installation ###

1. Clone the repository:

    ```bash
    git clone https://github.com/hroonr/fakestore-cart-test.git
    cd fakestoreapi-cart-tests
    ```
    
2. Create a virtual environment:

    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3. Install the required Python packages:

    ```bash
    pip install -r requirements.txt
    ```

### Running the Tests ###

1. Run the tests using pytest:

    ```bash
    pytest test_carts.py
    ```
    
### Test Scenarios ###

The automated tests cover the following scenarios:

1. Retrieve All carts:
   - Retrieve all carts and verifies the response status and structure.
  
2. Retrieve a single cart:
   - Retrieve a specific cart by ID and verifies the response status and content.
  
### Example 'test_carts.py' ###

Here is an example of what 'test_carts.py' might look:

'''python
import requests

base_url = "https://fakestoreapi.com/carts"

def test_get_all_carts():
    response = requests.get(base_url)
    assert response.status_code == 200, "Failed to retrieve all carts"
    assert isinstance(response.json(), list), "Response is not a list of carts"

def test_get_single_cart():
    cart_id = 1  # Example cart ID
    response = requests.get(f"{base_url}/{cart_id}")
    assert response.status_code == 200, f"Failed to retrieve cart with ID {cart_id}"
    assert response.json()['id'] == cart_id, f"Cart ID does not match {cart_id}"

This project shows how to automate API endpoint tests for the FakeStoreAPI's cart section using python and pytest. You can setup the project locally by reading the README and run the tests to verify the API's functionality. 

### FUTURE IMPROVEMENTS ### 
Following improvements could be made if additional time and resources were available:

1. Enhanced Test Coverage: Expand the test coverage to include more edges cases, e.g. error scenarios, and integration tests to ensure robustness.
2. Performance Optimization: Analyze and optimize the performance to improve the overall scalability of the application.
3. User Interfaec Refinement: Refine the user interface to enhance usability and overall user experience.
4. Parallel Execution: Implement parallel execution of automated tests to reduce test execution time and improve efficiency, especially for large test suites, e.g. Selenium.
5. Continuous Learning and Skill Development: Stay updated on the latest advancements in automation testing tools, frameworks, and techniques through continuous learning and skill development. 
