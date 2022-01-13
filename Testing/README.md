# Testing
[Unit test bascis](https://docs.microsoft.com/en-us/visualstudio/test/unit-test-basics)

## Unit Testing by Vladimir Khorikov - Takeaways
### Refresher
#### AAA pattern (arrange, act, assert), also called 3A pattern
- Arrange -> Bring the system under test (SUT) and it's dependencies into a desired state
- Act -> Call methods on SUT, pass dependencies and capture outcome
- Assert -> Verify the outcome (return value, final state of SUT, ...)

***Note:*** 
1. There is also the Given-When-Then pattern which is pretty much the same but more readable for non-technical people.
2. For TDD it might not be possible to start with the arrange section as you don't know enough about the SUT yet. In that case one would start with the assert section (i.e. with the expected behavior) 
3. Do not use multiple arrange/act/assert sections. If doing so, the test is not a unit test anymore.

#### xUnit
- unit testing framework - xUnit
- naming conventionns
- 
