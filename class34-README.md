# API Integration

**Dynamic API Server**

An Express/Node.js based server designed to be a “model agnostic” REST API server, which can perform CRUD operations on any data model.

**Support all REST/HTTP methods**

  *  GET: Retrieve record(s) from a data source 
  * POST: Create a new record in a data source
  * PUT: Update a single full record in a data source
  * PATCH: Update part of a single record in a data source
  * DELETE: Delete a record in a data source

**Development Process, Milestones**

  *  Phase 1: API Basics
       * Use JSON Server (non-express) to mock the routes for testing purposes
  *  Phase 2: Basic API
       * Create CRUD/ReST endpoints for categories and products
       * Separate route modules for each data model type
       * Store user created data in memory (no persistence)
       *  Integrates with an online CI framework
  *  Phase 3: Persistence
        Replace the in-memory data store with mongo
        Use Mongo Collections for each data model type
  *  Phase 4: Dynamic Models
      *  Create a single model class that all data models can inherit from to keep the interface simple
      * Use middleware to load models based on param
      * i.e. Replace app.get('/api/v1/categories') and app.get('/api/v1/products') with app.get('/api/v1/:model')
      * API is Fully Documented
      *  API is deployed and running live

It’s our intention to be able to “lift” the auth folder and “drop” it into any other server and be able to use authorization to “protect” those CRUD routes. This makes our entire auth system very modular. Think of index.js and server.js as nothing more than the basics to get a server started, with 100% of the actual logic living within the auth module 

**Bearer Authentication**

Re-Authentication can be achieved on any route in the express server, not just the authentication routes.


