# Answers

*1. Explain the relationship between the "Product" and "Product_Category" entities from the above diagram.*

**Ans: The relationship between Product and product_category is Many-to-One.**

*2.How could you ensure that each product in the "Product" table has a valid category assigned to it?*

**Ans: The "Product" table should have a foreign key constraint on the "category_id" column, which references the "id" column in the "product_category" table. This constraint ensures that every value in the "category_id" column of the "Product" table must exist in the "id" column of the "product_category" table.**

 *CREATE TABLE product (
  id INT PRIMARY KEY AUTO_INCREMENT,
  name VARCHAR(255) NOT NULL,
  description TEXT,
  SKU VARCHAR(50) UNIQUE NOT NULL,
  category_id INT NOT NULL,
  inventory_id INT UNIQUE,  
  price DECIMAL(10,2) NOT NULL,
  discount_id INT,  
  created_at TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP,
  modified_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  deleted_at TIMESTAMP DEFAULT NULL,
  FOREIGN KEY (category_id) REFERENCES product_category(id),
  FOREIGN KEY (inventory_id) REFERENCES product_inventory(id) 
);*
