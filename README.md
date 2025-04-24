# E-Commerce Database Schema

This project defines the schema for an e-commerce database. Below is an overview of the tables and their relationships.

## Switch your github to darkmode for a better view

![group_work_erd](<PLP_GROUP_340.drawio (2).png>)

## Tables

1. **brand**
   - `brand_id` (Primary Key)
   - `name`

2. **product_category**
   - `product_category_id` (Primary Key)
   - `name`

3. **product**
   - `product_id` (Primary Key)
   - `name`
   - `brand_id` (Foreign Key referencing `brand(brand_id)`)
   - `product_category_id` (Foreign Key referencing `product_category(product_category_id)`)
   - `base_price`

4. **color**
   - `color_id` (Primary Key)
   - `name`

5. **size_category**
   - `size_category_id` (Primary Key)
   - `name`

6. **size_option**
   - `size_option_id` (Primary Key)
   - `size_category_id` (Foreign Key referencing `size_category(size_category_id)`)
   - `value`

7. **product_variation**
   - `product_variation_id` (Primary Key)
   - `product_id` (Foreign Key referencing `product(product_id)`)
   - `color_id` (Foreign Key referencing `color(color_id)`)
   - `size_option_id` (Foreign Key referencing `size_option(size_option_id)`)

8. **product_item**
   - `product_item_id` (Primary Key)
   - `product_variation_id` (Foreign Key referencing `product_variation(product_variation_id)`)
   - `SKU` (Unique)

9. **product_image**
   - `product_image_id` (Primary Key)
   - `product_id` (Foreign Key referencing `product(product_id)`)
   - `image_uri`

10. **attribute_category**
    - `attribute_category_id` (Primary Key)
    - `name`

11. **attribute_type**
    - `attribute_type_id` (Primary Key)
    - `attribute_category_id` (Foreign Key referencing `attribute_category(attribute_category_id)`)
    - `name`

12. **product_attribute**
    - `product_attribute_id` (Primary Key)
    - `product_id` (Foreign Key referencing `product(product_id)`)
    - `attribute_type_id` (Foreign Key referencing `attribute_type(attribute_type_id)`)
    - `value`

## Notes

- The database is named `e_commerce`.
- Tables are dropped if they already exist to allow for development and testing.
- Relationships between tables are established using foreign keys.