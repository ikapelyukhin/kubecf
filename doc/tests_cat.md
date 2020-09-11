# Acceptance tests

The `make cats` target starts a run of the [Cloud Foundry Acceptance Tests].

[Cloud Foundry Acceptance Tests]: https://github.com/SUSE/cf-acceptance-tests-release

See also the [entire set of available tests](tests.md).

## Limiting test suites

To limit the test groups to run, set the BOSH property
[`acceptance_tests.include`] as documented.  To do so, adjust the `properties`
key in [`values.yaml`] to specify the groups desired.  For example:

```yaml
properties:
  acceptance-tests:
    acceptance-tests:
      acceptance_tests:
        include: "+docker,-ssh"
```

[`acceptance_tests.include`]:  https://github.com/SUSE/cf-acceptance-tests-release/blob/0.0.1/jobs/acceptance-tests/spec#L47-L54
[`values.yaml`]: ../../dev/kubecf/values.yaml

Note that this is an example of how to use the second kind of
customization feature noted in the main
[README](Contribute.md#customization).
