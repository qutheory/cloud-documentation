# Load testing

When running production workloads, you can find yourself in a situation where you need to run a load test. This describes the general requirements when running load tests on applications in the Vapor Cloud environment.

!! note
   It is NOT allowed to do load tests when using "Get started" database.

## Test types

We have different test types, depending on the scale of your load test, see below, for the different requirements.

### Low/medium tests

**Requests:** < 20.000 requests/min.
**Allowed replicas:** Small and higher
**Requires permission:** No

Our low/medium test, allows you to always run a load test against your application for up to **10.000 requests/min**. This does not require prior acceptance from Vapor Cloud.

### High tests

**Requests:** > 20.000 requests/min.
**Allowed replicas:** Medium and higher
**Requres permission:** Yes

Our high test, is meant if you run larger production workloads. There is in theory no top level of how large these can be. **BUT** they require prior permission from Vapor Cloud. To be allowed to run this test, contact our support, and tell us why you require the test, how many requests, and other useful details.

!! note
   Running High tests without prior permission can result in your account be deactivated, and all your applications to be terminated.
