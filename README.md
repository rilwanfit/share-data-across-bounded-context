# Share data across bounded context
## components
- symfony/event-dispatcher:^4.2
- phpunit/phpunit:^7.5

Practise how to share data across bounded context (system).

### Sample scenario: Sharing a customer list. 
System A - Customer maintenance
System B - Order management
System A is dedicated to customer maintenance. Here, users can maintain customer data, along with plenty of other data.  This system interacts with a data storage mechanism, but that isn’t important to the sample. The second system B is designed for taking orders. In that system, users need access to customers, but really only to identify the customer making the order. That means this bounded context needs just a read-only list of customer names and identifiers. Therefore, the database connected to the second system needs an up-to-date list of customer names and IDs based on the customers that are maintained in the first system. The approach I chose to accomplish this is to mirror in the second system those two pieces of data for each customer that’s maintained in the first system.
### Approach: Mirroring data from one bounded context to another 
