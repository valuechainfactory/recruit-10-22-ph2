# Simple Reorder Module

## Scenario

Kefis is a simple store that deals in FMCG. They desire a simple application that tracks inventory and makes automated reorders to their off-site warehouse when the stock level hits a predefined quantity.
The warehouse attendant can see all reorders coming in and dispatch them to the store. Processed reorders are marked as such.
Both the retailer and the warehouse can see pending and processed reorders.

## Requirements

**Hints:**
- **KEEP IT SIMPLE** - Notice that we didn’t ask for CRUD on products or users.
- In addition to other technical areas of interest, we are very keen on your thought process. 
- Feel free to be creative but do not complicate your solution in a bid to impress only to find it unfinished in the stipulated period. 
- Do not be too concerned with a fancy UI. We do however expect to be able to navigate the pages.

### Client Requirements

#### Store
- There can only be one unfulfilled order per product.
- Seed **10** test products into the database with a default amount of inventory and reorder level. (Product metadata required is only a name).
- In the product listing for the store, add a button that reduces inventory to simulate a sale. The table should have the columns below:-
	- Product Name
	- Outstanding Inventory
	- Number of fulfilled orders (0 if none)  
	  Ensure there are some products without orders  
	  *Hint: Take a look at window functions partitioning by product id*  
	- Order Number of currently unfulfilled order. N/A if none.  
    To generate an order number, pad the order id with leading 0s to make a string of a minimum of 6 characters, e.g `000001`, `000002` for order ids 1 and 2.
- When inventory hits the predefined reorder level, create an automated reorder in an unprocessed state.
- The store actor should have a view to see unprocessed and processed reorders.
- The store actor should be able to update the quantity of an order and also to delete it completely.

#### Warehouse
- The warehouse actor should have a view to see unprocessed reorders.
- On the reorder listing for the warehouse, have a dispatch button that simulates a dispatch to the store.
- The above dispatch action should increment inventory in the store.



### Technical Requirements

- The buttons should not trigger a page refresh. (hint: Javascript, in whatever from, will come in handy here)
- Separate your app into a RESTful API and a Javascript/HTML based frontend
- Write at least one unit test for each of the functions that simulate the sale and the dispatch
- Make API calls using the correct HTTP verbs
- Allow only for the domain of the front end app to access the API (CORS). Please note that a domain includes the port. We will verify that you can not access the APIs when running the frontend on a different port.


### Languages allowed

Feel free to use any language you feel most comfortable with.
