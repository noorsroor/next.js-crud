# next.js-crud
Sure! Here's a sample `README.md` for your Next.js CRUD application using MongoDB:

---

# Next.js CRUD Product Management with MongoDB

This is a simple Next.js application that demonstrates how to build a CRUD (Create, Read, Update, Delete) system for managing products with MongoDB. This is perfect for beginners who want to practice or learn how to handle CRUD operations in Next.js with a backend connected to MongoDB.

## Prerequisites

Before getting started, make sure you have the following installed on your machine:

- [Node.js](https://nodejs.org/) (Recommended version: v14 or later)
- [MongoDB Atlas Account](https://www.mongodb.com/cloud/atlas) (or local MongoDB instance)

## Getting Started

### 1. Clone the Repository

First, clone this repository to your local machine:

```bash
git clone https://github.com/your-username/nextjs-crud-mongodb.git
```

### 2. Install Dependencies

Navigate to the project folder and install the required dependencies:

```bash
cd nextjs-crud-mongodb
npm install
```

### 3. Configure MongoDB

You'll need a MongoDB connection string. You can use [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) (cloud database) or set up a local MongoDB instance. 

Once you have your MongoDB URI, create a `.env.local` file in the root of your project and add the following:

```plaintext
MONGODB_URI=mongodb+srv://<username>:<password>@cluster0.mongodb.net/products
```

### 4. Run the Development Server

Start the Next.js development server:

```bash
npm run dev
```

The application will be running on `http://localhost:3000`.

### 5. Visit the Products Page

Open your browser and visit:

```
http://localhost:3000/products
```

You should see a list of products along with options to add, update, and delete products.

---

## Endpoints

### 1. **Get All Products (Read)**

- **URL:** `/api/products`
- **Method:** `GET`
- **Description:** Retrieves a list of all products from the MongoDB database.

### 2. **Add a Product (Create)**

- **URL:** `/api/products`
- **Method:** `POST`
- **Body Parameters:** 
  ```json
  {
    "name": "Product Name",
    "description": "Product Description",
    "price": "Product Price",
    "image": "Product Image URL"
  }
  ```
- **Description:** Adds a new product to the database.

### 3. **Update a Product (Update)**

- **URL:** `/api/products/[slug]`
- **Method:** `PUT`
- **Body Parameters:**
  ```json
  {
    "name": "Updated Product Name",
    "description": "Updated Description",
    "price": "Updated Price",
    "image": "Updated Image URL"
  }
  ```
- **Description:** Updates the details of an existing product based on its `slug`.

### 4. **Delete a Product (Delete)**

- **URL:** `/api/products/[slug]`
- **Method:** `DELETE`
- **Description:** Deletes a product based on its `slug`.

---

## How the Application Works

### 1. **Product Management**

- The **Product Model** is a Mongoose schema that defines the structure of each product in the MongoDB database. Each product has fields like `name`, `description`, `price`, and `image`.
  
- The **API Routes** in `pages/api/products` handle the CRUD operations:
  - **GET**: Fetches all products from the database.
  - **POST**: Adds a new product to the database.
  - **PUT**: Updates an existing product by `slug`.
  - **DELETE**: Deletes a product by `slug`.

### 2. **Frontend**

- The **Products Page** displays all products in a grid. It allows you to add a new product through a form.
  
- Each product has two buttons for updating or deleting the product. You can update product details or remove it from the database.

---

## Project Structure

```plaintext
nextjs-crud-mongodb/
├── components/
│   ├── ProductForm.js         # Form to add new products
│   └── ProductList.js         # Displays the list of products
├── lib/
│   └── mongodb.js             # MongoDB connection utility
├── models/
│   └── Product.js             # Mongoose Product schema
├── pages/
│   ├── api/
│   │   └── products/          # API routes for CRUD operations
│   ├── products.js            # Product list and form page
│   └── index.js               # Home page
├── .env.local                 # MongoDB connection URI
├── package.json               # Project dependencies and scripts
└── README.md                  # This file
```

---

## Technologies Used

- **Next.js** (React-based framework)
- **MongoDB** (Database)
- **Axios** (For making HTTP requests)
- **Mongoose** (MongoDB object modeling)
- **Tailwind CSS** (Styling)

---

## How to Contribute

If you'd like to contribute to this project, feel free to fork it, make changes, and submit a pull request.

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

Let me know if you'd like to adjust anything!