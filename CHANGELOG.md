## 1.2.0 (March 22, 2023)

NOTES:

* This Go module has been updated to Go 1.19 per the [Go support policy](https://golang.org/doc/devel/release.html#policy). Any consumers building on earlier Go versions may experience errors. ([#91](https://github.com/hashicorp/terraform-plugin-testing/issues/91))
* helper/resource: Deprecated `PrefixedUniqueId()` and `UniqueId()`. Use the `github.com/hashicorp/terraform-plugin-sdk/v2/helper/id` package instead. ([#96](https://github.com/hashicorp/terraform-plugin-testing/issues/96))
* helper/resource: Deprecated `RetryContext()`, `StateChangeConf`, and associated `*Error` types. Use the `github.com/hashicorp/terraform-plugin-sdk/v2/helper/retry` package instead. ([#96](https://github.com/hashicorp/terraform-plugin-testing/issues/96))
* helper/resource: Deprecated Terraform module-based `TestCheckFunc`, such as `TestCheckModuleResourceAttr`. Provider testing should always be possible within the root module of a Terraform configuration. Terraform module testing should be performed with Terraform core functionality or using tooling outside this Go module. ([#109](https://github.com/hashicorp/terraform-plugin-testing/issues/109))

FEATURES:

* plancheck: Introduced new `plancheck` package with interface and built-in plan check functionality ([#63](https://github.com/hashicorp/terraform-plugin-testing/issues/63))
* plancheck: Added `ExpectResourceAction` built-in plan check, which asserts that a given resource will have a specific resource change type in the plan ([#63](https://github.com/hashicorp/terraform-plugin-testing/issues/63))
* plancheck: Added `ExpectEmptyPlan` built-in plan check, which asserts that there are no resource changes in the plan ([#63](https://github.com/hashicorp/terraform-plugin-testing/issues/63))
* plancheck: Added `ExpectNonEmptyPlan` built-in plan check, which asserts that there is at least one resource change in the plan ([#63](https://github.com/hashicorp/terraform-plugin-testing/issues/63))

ENHANCEMENTS:

* helper/resource: Added plan check functionality to config and refresh modes with new fields `TestStep.ConfigPlanChecks` and `TestStep.RefreshPlanChecks` ([#63](https://github.com/hashicorp/terraform-plugin-testing/issues/63))

## 1.1.0 (February 06, 2023)

FEATURES:

* helper/resource: Added `TF_ACC_PERSIST_WORKING_DIR` environment variable to allow persisting of Terraform files generated during each test step ([#18](https://github.com/hashicorp/terraform-plugin-testing/issues/18))
* helper/resource: Added `TestCase` type `WorkingDir` field to allow specifying the base directory where testing files used by the testing module are generated ([#18](https://github.com/hashicorp/terraform-plugin-testing/issues/18))

## 1.0.0 (January 10, 2023)

NOTES:

* Same testing functionality as that of terraform-plugin-sdk v2.24.1, repacked in a standalone repository ([#24](https://github.com/hashicorp/terraform-plugin-testing/issues/24))

