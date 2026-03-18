## CI/CD and Building Orbot
-CI Pull request pushes to `master`)
- automatically built
-while PR forks must be approved 
-protect secrets
-prevent abusing
-build server
```config.build.c```
```#~$./build.c```

## Build will do a few things:
```
* Build a universal APK and make it available for download under "Artifacts"(`nightlyDebug`).
* Run tests
    * Unit tests are run (and results are available) right in bitrise under "Tests".
        * If these fail, the checks on the Pull Request will automatically fail.
    * Espresso tests are run in Browserstack App Automate on real devices.
        * While the logs will show summary results, including failures, the build will not fail nor will github's UI show failure
* Make the app available for testing on real devices via Browserstack.
    * Accessing this requires a login to our browserstack account.
```
### Secrets
```
 Browserstack credentials. 
Build a PR, be sure that PR isn't trying to log credentials from environment variables.
```