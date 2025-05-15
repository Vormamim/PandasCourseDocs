# Ext.1 - Using live API for testing

#### Understanding APIs

An **API** (Application Programming Interface) is a set of rules and protocols for building and interacting with software applications. It defines the methods and data formats that applications can use to communicate with each other, often over the internet. APIs enable different software systems to share data and functionality, making it easier to integrate and extend applications. For example, when a mobile app retrieves weather data from a web service, it often uses an API to accomplish this task seamlessly. APIs act as intermediaries that allow developers to leverage the capabilities of other software without needing to understand their underlying code in detail.

#### 1. **Dummy JSON API**

* **API:** `https://dummyjson.com/`

The website `https://dummyjson.com/` provides a dummy API service offering fake data for testing and prototyping purposes. It allows developers to practice making requests for various types of data without needing a real backend service. This dummy service includes endpoints for retrieving fake data related to products, carts, users, posts, and more, making it a useful tool for learning and demonstrating API interactions.

To do this, we need a library which can handle 'getting' the data (requesting)

```bash
pip import requests
```

S

{% code overflow="wrap" lineNumbers="true" %}
```python
import pandas as pd
import requests

url = 'https://dummyjson.com/carts'
r = requests.get(url, verify=False) # warning, this turns off the SSL, but school network will block request
r.raise_for_status()  # Raises an HTTP Error if the HTTP request returned an unsuccessful status code
data = r.json()

df = pd.DataFrame(data['carts'])
print(df.head)

```
{% endcode %}

Try this and see what data you get from the API.

<mark style="background-color:orange;">Your network might not allow SSL requests. In Line 5, I am turning off 'verfiy'. This may cause alarm bells to ring and definately warning message as it's NOT advised to be importing unknown data.</mark>

```python
import requests
import pandas as pd

# Step 1: Fetch data from the API
url = "https://dummyjson.com/posts"
response = requests.get(url)
# response = requests.get(url, verify=False) IF you get blocked
data = response.json()

# Step 2: Convert to DataFrame
posts = data['posts']
df = pd.DataFrame(posts)
df = df[['id', 'title', 'reactions', 'userId']]

# Step 3: Print the dataframe
print(df.head())

```

Explore the dummy files on offer from this resource

### Save the data you just requested as a CSV

```python
import requests
import pandas as pd

# Step 1: Fetch data from the API
url = "https://dummyjson.com/posts"
response = requests.get(url, verify=False) #remove Verify=False to increase security!
data = response.json()

# Step 2: Convert to DataFrame
posts = data['posts']
df = pd.DataFrame(posts)

# Optional: select only useful columns
df = df[['id', 'title', 'body', 'tags', 'reactions', 'userId']]

# Step 3: Save to CSV
df.to_csv("dummy_posts.csv", index=False)

print("CSV file 'dummy_posts.csv' has been created successfully!")

```

<mark style="background-color:orange;">Now you have instant access to plenty of fake data which you can save use in your own projects</mark>
