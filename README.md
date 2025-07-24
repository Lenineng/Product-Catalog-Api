# Product-Catalog-Api
A RESTful API built with Node.js, Express, and MongoDB that allows you to manage products, their variants, pricing, and inventory. Ideal for e-commerce or inventory systems.

## Features
- Create, update, delete, and fetch products with ease

- Handle product variants such as size and color

- Track inventory for both main products and their variants

- Return meaningful error messages and use appropriate HTTP status codes

- Includes middleware for logging, JSON body parsing, and Cross-Origin Resource Sharing (CORS)

- Clean and modular codebase with well-organized routes and controllers
  
### Installation
```bash
git clone https://github.com/yourusername/product-catalog-api.git
cd product-catalog-api
npm install
```

### Environment Variables
``` bash
Create a .env file in the root directory and add the following:
```
PORT=5000
MONGO_URI=mongodb://localhost:27017/product_catalog

### Running the Server

``` bash
npm run dev
```

#### OR start normally
``` bash 
npm start
```

The API will be running at:
http://localhost:5000/api-docs

### Product Schema
Each product supports the following structure:

{
  name: String (required),

  description: String,
  
  price: Number (required if no variants),

  Discount: Number,
   
  category: String,
  
  quantity: Number,
  
  variants: [
  
    {
      
        color: String
        stock: number
      }
    }
  ]
}

### API Endpoints
- Method	Endpoint	Description
- GET	/api/products	Get all products
- GET	/api/products/:id	Get a single product
- POST	/api/products	Create new product
- PUT	/api/products/:id	Update a product
- DELETE	/api/products/:id	Delete a product

#### Example Create Request:

POST /api/products

{
"name": "TOYOTA",
	"description": "good quality and comfy car.",
	"price": 90000,
	"discount": 10,
	"category": "6881dbad126b5ffdf56bc04b",
	"variants": [
	{
	   "color": "white",
	   "stock": 5
},
{
	"color": "black",
	   "stock": 10
}
	]
}

### Error Handling
All errors are returned in the following format:

{
  "message": "Product not found"
}
The API handles:

- 404 Not Found

- 500 Internal Server Error

- Validation errors

### Project Structure

project-root/

├── controllers/

│   └── productController.js

├── routes/

│   └── productRoutes.js

├── models/

│   └── product.js

├── middlewares/

│   └── errorMiddleware.js

├── app.js

├── server.js

└── .env




#### DEMO VIDEO: 
https://www.loom.com/share/c8f4f2d7aa0e4729a648b97c41fab707?sid=729eea68-2a45-4f5a-908c-f3e8ded86bcc

#### License
This project is open-source and free to use under the MIT License.

