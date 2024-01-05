---
problem: What are the best performing products month on month?
users:
- reporting     # people looking at overviews
- management    # people creating new products and looking at details
contributors:
- developer    # who made this originally and can be consulted
documents:
- transactions
- products
- customers
stories: ## sequences of actions, documents, and results for users
- view report dashboard with drill down
- change in product details (CRUD)
- monitoring transactions
  - filtering by customer, day, or product
---
# overview


### build patterns
1. CRUD
2. Reporting
3. Transactions

##### pages:
home page can be the dashboard page

- dashboard report
  - requests (view)
    - transactions
    - products
    - customers
  - blocks
    - table with filters for transction
    - sales total
      - filter by product
    - total by customer
- Admin edit page
  - edit products, add new
  - edit customers, add new (more detail)
- Transaction stream page
  - this should be captured elsewhere and imported in here, expect this to continually update
  - want view filters including date, customer, transaction type
  - want comment options for this

#### templates

1. colours
   1. for product types
   2. for statuses
2. blocks for inside the panels
3. right side panel:
   1. search filter
   2. top right button for admin mode switch
   3. filter with heading as a link to the page view
4. admin mode panel moves to left for make new.
5. variable settings (connections and references)
6. filter

### lowdefy.yaml

```
name: Sales Management Example application
lowdefy: 4.0.0-rc.15  # confirm the version number!
licence: MIT
```
cli:
  disableTelemetry: true
// not really necessary for now

config:
// if we want a login, we should add it in here, else homepage
  homePageId: welcome

auth:
// this is a premium feature, not needed for now

global:
  _ref: global.yaml

connections:
 mongodb

plugins:
  - name: ''
  - version ''
// none needed yet

menus:
  - Overview
  - Customers
  - Products
  - Transactions Stream

pages:
