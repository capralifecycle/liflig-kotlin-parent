# liflig-kotlin-parent
Basic setup for kotlin projects.

The responsibility of the parent pom is to avoid duplication of configuration that is identical between all
Kotlin projects.

It should be minimal and non-intrusive - less is more.
The responsibility is limited to:

* Default distribution management: default OSS repositories for snapshots and releases (capra-releases/capra-snapshots).
  It is possible to override this setting to use a customer project repository instead of the default, shared OSS
  repository.


* Plugin management:  specify versions of build plugins to ensure build reproducibility.
  Only plugins used by _most_ projects should be added.
  See description of recommendation here: https://maven.apache.org/guides/mini/guide-configuring-plugins.html.


* Maven version enforcement: Ensure minimum maven version used  


* plugin to create flattened pom for automatic releases


* support for *Spec unit tests


* Kotlin bom (bill of materials), dependency and versioning


* Kotlin maven plugin for compilation (impl/test)


* Kotlin code style, compiler jvm-target and build source encoding properties


* Ktlint setup for code linting


The parent pom should NOT be used for:

* Dependency management: Dependencies will vary. Adding dependency management to the parent pom creates a lot
  of unnecessary tight couplings.


* Build configuration: Builds vary. Except for Kotlin (see kotlin-maven-plugin above), the parent pom should
  not be used for enforcing behaviour across projects.


* Reporting - maven reporting support is not that popular anymore


