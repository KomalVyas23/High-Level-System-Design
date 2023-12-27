What is Quad Trees?

A quadtree is a **tree data structure** in which **each internal node has exactly four children**. A two-dimensional space is repeatedly divided into four quadrants where each of which acts as a node with spatial information. The longitude and latitude are represented as cartesian coordinates (x, y), and search the points efficiently.

Why do we need quad Trees, when we already have Latitude and Longitude?

While using coordinates of latitude and longitude, we need to use Euclidean distance to calculate close location points. However, when there are large data sets, it shows CPU-intensive nature. This makes the use of coordinates in the real-time system not scalable.

Geohashing also helps us save extra computational operations because it only divides a node after a certain threshold. In addition, with the use of some mapping algorithms like the Hilbert Curve, the range query performance is also improved.

**Types of Quad Trees?**

Types of Quadtrees
The types of quadtrees depend on the data that needs to be represented like areas, points, lines, curves, etc. Some of the most common quadtrees types are listed below: -

Edge Quadtrees
Point Quadtrees
Point-region (PR) Quadtrees
Compressed Quadtrees
Polygonal Map (PM) Quadtrees

**Use Cases of Quad Trees:**

Spatial Indexing
Range Queries
InDriver, Pathao, etc. (location-based services)
Mesh Generation
Computer Graphics
Sparse Data Storage
Image representation, processing, and compression
