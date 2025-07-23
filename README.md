
# RestoBot

RestoBot simplifies the dining experience by providing a user-friendly chat interface for various restaurant-related services. It helps users find restaurants, browse menus, make reservations, place orders, and more.


## Features

1. **Restaurant Discovery**:
   - Search for restaurants by cuisine, location, or price range.
   - Implemented in `api.js` using the `/api/restaurants` endpoint.
   - Uses MySQL queries to filter restaurants based on cuisine, price, and location.
   - Calculates average ratings for each restaurant.

2. **Menu Exploration**:
   - View digital menus with descriptions and ratings.
   - The `/api/restaurant/menu` endpoint in `api.js` fetches menu information.
   - Menus are stored as image URLs in the `restaurants` table, as an image-based menu is more visually appealing to a user than a  plain text-based menu.

3. **Reservation Management**:
   - Make and manage reservations with special requests.
   - Handled by the `handleReservation`, `processReservationDetails`, and `confirmReservation` functions in `index.js`.
   - Uses the `/api/reservations` endpoint to interact with the database.
   - Checks table availability and assigns tables based on party size.

4. **Ordering System**:
   - Place orders for delivery or pickup directly through the bot, adding or removing items with ease.
   - Implemented through `handleOrder`, `processOrderItems`, and `confirmOrder` functions in `index.js`.
   - Utilizes `/api/orders` and `/api/menu` endpoints for database interactions.
   - Allows adding/removing items and calculates total price accordingly.

5. **Payment Integration**:
   - Secure payment processing within the chat interface.
   - Uses Razorpay API (Only simulated in this version).
   - `initiatePayment` and `confirmPayment` functions in `index.js` handle the payment flow.
   - Integrates with `/api/create-razorpay-order` and `/api/verify-razorpay-payment` endpoints.

6. **Order Tracking**:
   - Real-time updates on order status.
   - Implemented using the `trackOrder` function in `index.js`.
   - Uses the `/api/order-status/:orderId` endpoint to fetch real-time status updates.

7. **Personalized Recommendations**:
   - Suggest restaurants based on user preferences and order history.
   - The `getPersonalizedRecommendations` function in `index.js` handles this feature.
   - Utilizes the `/api/recommendations` endpoint, which queries the `user_order_history` table.

8. **Additional Features**:
   - Customer reviews: Implemented with `/api/reviews/positive` and `/api/reviews/negative` endpoints.
   - Restaurant descriptions: Fetched using the `/api/restaurant/description` endpoint.



## Technology Stack

- Node.js
- Express.js
- MySQL
- Microsoft Bot Framework SDK
- Axios for HTTP requests
- HTML
- CSS
  
