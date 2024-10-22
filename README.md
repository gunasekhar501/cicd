+--------------------+                 +---------------------------+
|  Frontend          |  <----->  API   |                           |
|  akyrian-prod-     |                 |                           |
|  frontend          |                 |  akyrian-prod-be-api       |
+--------------------+                 +---------------------------+
                                          |        |        |
                                          |        |        |
                       +------------------+        |        +------------------+
                       |                           |                           |
   +-------------------v---+               +-------v---------+         +-------v-------------------+
   |   Redis Master         |              |   Elasticsearch  |         |   PostgreSQL (assumed)   |
   |   akyrian-backend-     |              |   akyrian-backend|         |                           |
   |   redis-master         |              |   elasticsearch  |         |                           |
   +------------------------+              +------------------+         +--------------------------+
            ^      ^                    ^                       ^
            |      |                    |                       |
   +--------+      +--------------------+            +----------+------------------+
   |                                    |            |                             |
   |                                    |            |                             |
   v                                    v            v                             v
+---------------------------+    +---------------------------+          +---------------------------+
| Reminder Deployment        |    | Image Processing          |          | Redis Replicas             |
| akyrian-prod-be-reminder    |    | akyrian-prod-be-image-    |          | akyrian-backend-redis-     |
+---------------------------+    +---------------------------+          +---------------------------+

  + Twilio (external)                   + S3 (external)
