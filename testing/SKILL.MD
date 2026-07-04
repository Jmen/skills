# What Makes A Good Test Suite

1. Fast Runtime
- **When the whole test suite is run together it should be fast**
- For example: A few slow high-value tests are acceptable if the overall suite stays fast

2. Predictive Of Correctness
- **The full suite should provide evidence that the code will work in production**
- Each type of test may have different trade offs of how realistic they are vs how fast they are to run
- There maybe a combination of end to end, integration and unit tests, but they should provide an overlapping coverage of everything important to know that the code is safe to release

3. Low Cost of Ownership
- **Tests which are hard to understand have a high cost** - use either Behaviour Driven Development, or Arrange Act Assert to organise the tests
- **Tests which are coupled to the implementation are hard to change** - only interact with the System Under Test through its public interface, and prefer Outside-In testing to provide the largest possible opportunity for refactoring without needing to change the tests
- **Tests which are Flakey undermine confidence and are not Predictive** - invest extra time in figuring out these issues. If the system is flakey in the test environment, it's likely it's flakey in production as well

4. Test Driven Design
- Writing the tests first helps to get the intent clear, which acts as documentation of what the code should do
- Writing the tests first enables you to clearly write the minimum code to complete the required functionality
- Ensuring the test fails before the implementation is complete, ensures that your tests are not giving you false positives
