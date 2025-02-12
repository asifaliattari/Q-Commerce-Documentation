# Q-Commerce Food Restaurant Project

## Business Goals

1. **Deliver High-Quality Food Quickly**  
   - Ensure timely delivery with optimal food quality.

2. **Personalized Customer Experience**  
   - Tailored recommendations.  
   - Meal customizations.

3. **Streamlined Ordering Process**  
   - User-friendly platform for browsing menus and placing orders.

4. **Efficient Back-End Operations**  
   - Automate inventory management.  
   - Real-time order tracking.  
   - Delivery management.

5. **Customer Feedback Integration**  
   - Collect and analyze feedback.  
   - Enhance services based on insights.

6. **Marketing and Engagement**  
   - Promote business through blogs.  
   - Special offers and loyalty programs.

7. **Scalability**  
   - Expand to handle increased demand.  
   - Onboard new restaurant partners.

---

## Core Business Entities

### 1. **User**
   - **Attributes**:  
     - `user_id`: Unique identifier.  
     - `name`: Full name.  
     - `email`: Contact email.  
     - `phone_number`: Contact number.  
     - `address`: Delivery address.  
     - `preferences`: Dietary preferences (e.g., vegetarian, vegan, halal).  
     - `order_history`: Record of past orders.

### 2. **Menu**
   - **Attributes**:  
     - `menu_id`: Unique identifier.  
     - `restaurant_id`: Associated restaurant.  
     - `name`: Dish name.  
     - `description`: Description of the dish.  
     - `image_url`: Image link for the dish.  
     - `price`: Cost per unit.  
     - `category`: Food category (e.g., appetizers, desserts).  
     - `availability`: Boolean indicating availability.  
     - `ingredients`: List of ingredients.

### 3. **Restaurant**
   - **Attributes**:  
     - `restaurant_id`: Unique identifier.  
     - `name`: Restaurant name.  
     - `description`: Overview of the restaurant.  
     - `logo_url`: Logo link.  
     - `address`: Restaurant location.  
     - `contact_info`: Contact details.  
     - `operating_hours`: Business hours.  
     - `cuisine_type`: Cuisine category (e.g., Italian, Fast Food).

### 4. **Order**
   - **Attributes**:  
     - `order_id`: Unique identifier.  
     - `user_id`: Linked user.  
     - `restaurant_id`: Linked restaurant.  
     - `order_date`: Date of the order.  
     - `status`: Order status (e.g., Pending, Delivered).  
     - `total_price`: Total cost.  
     - `delivery_address`: Address for delivery.

### 5. **OrderItem**
   - **Attributes**:  
     - `order_item_id`: Unique identifier.  
     - `order_id`: Associated order.  
     - `menu_id`: Linked menu item.  
     - `quantity`: Number of units ordered.  
     - `price`: Price of the item.

### 6. **Review**
   - **Attributes**:  
     - `review_id`: Unique identifier.  
     - `user_id`: Reviewer.  
     - `restaurant_id`: Reviewed restaurant.  
     - `rating`: Rating (1-5).  
     - `comment`: Review comment.  
     - `date`: Review date.

### 7. **Blog/News**
   - **Attributes**:  
     - `blog_id`: Unique identifier.  
     - `title`: Blog title.  
     - `content`: Blog content.  
     - `image_url`: Image link.  
     - `author`: Author's name.  
     - `published_date`: Date published.  
     - `tags`: Associated tags.

### 8. **Promotions**
   - **Attributes**:  
     - `promotion_id`: Unique identifier.  
     - `title`: Promotion title.  
     - `description`: Details about the promotion.  
     - `discount_percentage`: Discount offered.  
     - `start_date`: Start date.  
     - `end_date`: End date.  
     - `applicable_restaurants`: Linked restaurants.

### 9. **Chef**
   - **Attributes**:  
     - `chef_id`: Unique identifier.  
     - `name`: Full name.  
     - `profile_picture_url`: Picture link.  
     - `specialty`: Area of expertise.  
     - `experience_years`: Years of experience.  
     - `bio`: Short biography.

---

## Workflow for Checkout

1. **Step 1: Cart Review**  
   - Display selected menu items.

2. **Step 2: Shipping and Billing Information**  
   - Collect user details (or fetch saved addresses).  
   - Validate form data.

3. **Step 3: Calculate Total**  
   - Backend computes:  
     - Subtotal.  
     - Discounts.  
     - Shipping fees.  
     - Tax.

4. **Step 4: Payment**  
   - Redirect to payment gateway.

5. **Step 5: Confirmation**  
   - Display confirmation screen or send email.

---

## API Endpoints

1. `GET /cart`: Retrieve cart items.  
2. `POST /checkout`: Submit shipping and billing info.  
3. `GET /order/summary/{id}`: Fetch order details.  
4. `POST /order/place`: Confirm and place the order.
