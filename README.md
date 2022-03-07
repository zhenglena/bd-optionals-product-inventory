### Optionals

Expected time required: 15 min

You will be implementing two methods in a class called `ProductInventory`.

The class has two fields:
- `ProductUtility` productUtility
- `List<Integer>` productIDs

The class has some completed methods, and two methods that you will be implementing:
- `Map<Integer, String> findProductNames() throws IllegalArgumentException`
- `Optional<Boolean> isProductReady(Integer packageID) throws IllegalArgumentException`

Skeletons of both of these methods exist with JavaDocs, but they currently return dummy results. This causes all JUnit
tests to fail. The goal is to get all of the JUnit tests to pass. There is no main method to run.

Here's what you need to do for these methods:

`isProductReady`:
1) Call `ProductUtility` productUtility's `isProductReady(Integer productId)` to get the status of the requested product.
2) If `ProductUtility` throws a `NullPointerException`, throw an `IllegalArgumentException` with the message "The
      productID was null"
3) If the `ProductUtility` returns null, return an empty Optional instead.
4) If the `ProductUtility` returns a Boolean, wrap that in the Optional you return.

`findProductNames`:
1) Put in guard statements so that `IllegalArgumentException` gets thrown if either instance variable is null. The
      message should be `"<instance variable> is null"`
2) Initialize an empty `Map` matching the return signature.
3) Loop over the list of Product IDs for steps 4) to 6):
4) Use the `ProductUtility` provided as an instance variable and call `findProductName(Integer ID)` to get the name.
5) If the `ProductUtility` throws a `NullPointerException`, throw an `IllegalArgumentException` instead with the
      message `"productID is null"`.
6) If the `ProductUtility` returns a null String, do not add it to the Map. If it returns a populated String, add the
      (`productID`, returned `String`) to the `Map`.
7) Return the `Map`, even if it is empty.

HINTS:
* [How can I concisely loop over a List?](./hints/hint-01.md)
* [I can't get the messages to match the expected test messages?](./hints/hint-02.md)
