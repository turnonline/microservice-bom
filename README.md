# ConnecSys microservice on the Google AppEngine standard

ConnecSys microservice based on the Google App Engine standard for Java 17+ (`java21` runtime), providing access to
legacy bundled services. Bill of Materials: This component keeps track of dependency versions and ensures that
everything works well together.

## Versioning

The BOM version mirrors the pinned `com.google.appengine:*` version (1.9.x, 2.0.21, 2.0.22 did; 2.0.23 pinned
App Engine 2.0.39 and is the one exception).

## Releases

- **5.0.4** — App Engine `com.google.appengine:*` 2.0.39 → 5.0.4 (`appengine-api-1.0-sdk`, `appengine-api-legacy`,
  `appengine-remote-api`, `appengine-tools-sdk`, `appengine-testing`, `appengine-api-stubs`). Dropped the dead
  v1 pins `appengine-endpoints` / `appengine-local-endpoints` 1.9.86 (no consumer). Everything else unchanged
  (`endpoints-framework*` 2.2.7, ctoolkit-services 0.36, ctoolkit-rest-facade-* 0.39, jmockit, testng, truth).
  The 5.x App Engine jars are JDK 17 bytecode: consumers must build with `--release 17` and run on the `java17`
  or (target) `java21` runtime with `appengine.use.EE8=true`. Services still on `java11` must stay on
  `org.ctoolkit.maven:ctoolkit-microservice-bom` 2.0.22 until they move runtime.
- **2.0.23** — App Engine 2.0.39; REST-facade 0.39 (App Engine without the Orika mapper); parent
  `connecsys-private-parent` (ConnecSys internal Artifact Registry). #TOB-474
- **2.0.22** — App Engine standard 2.0.22 upgrade; renamed from `org.ctoolkit.maven:ctoolkit-microservice-bom`
  to `biz.turnonline.ecosystem:connecsys-microservice-bom`. #TOB-405
