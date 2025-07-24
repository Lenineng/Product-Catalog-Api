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

Create a .env file in the root directory and add the following:

``` bash
PORT=5000
MONGO_URI=mongodb://localhost:27017/product_catalog
```

### Running the Server
``` bash
npm run dev
```

#### OR start normally
``` bash 
npm start
```

The API will be running at:
``` bash
http://localhost:5000/api-docs
```

### Product Schema
Each product supports the following structure:
``` bash
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
```

## API Endpoints

### Category Endpoints

| Method | Endpoint           | Description               |
|--------|--------------------|---------------------------|
| GET    | /categories      | Get all categories        |
| GET    | /categories/:id  | Get category by ID/slug   |
| POST   | /categories      | Create category           |
| PUT    | /categories/:id  | Update category           |
| DELETE | /categories/:id  | Delete category           |

### Product Endpoints

| Method | Endpoint                                              | Description                     |
|--------|-------------------------------------------------------|---------------------------------|
| GET    | /products                                           | Get all products                |
| GET    | /products/:id                                       | Get product by ID               |
| POST   | /products                                           | Create a product                |
| PUT    | /products/:id                                       | Update a product                |
| DELETE | /products/:id                                       | Delete a product                |
| GET    | /products?search=tv                                 | Search products by name/desc    |
| GET    | /products?category=ID                               | Filter by category              |
| GET    | /products?minPrice=10&maxPrice=100                  | Filter by price range           |

#### Example Create Request:
``` bash
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
```

### Error Handling
All errors are returned in the following format:
``` bash
{
  "message": "Product not found"
}
```
The API handles:
``` bash
- 404 Not Found

- 500 Internal Server Error

- Validation errors
```
### Project Structure
``` bash
product-catalog-api/
│
├── config/
│   └── db.js           # MongoDB connection
├── controllers/
│   └── productController.js
│   └── categoryController.js
├── models/
│   └── Product.js
│   └── Category.js
├── routes/
│   └── productRoutes.js
│   └── categoryRoutes.js
├── middlewares/
│   └── errorMiddleware.js
├── swagger/
│   └── swaggerDocs.js
├── .env
├── index.js
├── swagger.js
└── README.md
```


#### DEMO VIDEO: 
``` bash
https://www.loom.com/share/c8f4f2d7aa0e4729a648b97c41fab707?sid=729eea68-2a45-4f5a-908c-f3e8ded86bcc
```

#### License
This project is open-source and free to use under the MIT License.

