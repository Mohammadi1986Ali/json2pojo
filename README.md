# json2pojo

Small Maven project that generates Java POJOs from JSON Schema files with
`jsonschema2pojo`, then packages the app as a runnable shaded JAR.

## Project Layout

```text
src/main/resources/schema/Address.json
```

JSON schemas live under `src/main/resources/schema`.

During the Maven build, `jsonschema2pojo` generates Java classes into:

```text
target/generated-sources/jsonschema2pojo
```

Generated classes use this package:

```text
com.nexora.software.schema
```

Do not edit generated Java files directly. Edit the JSON schema and rebuild.

## Common Commands

Generate POJOs:

```powershell
mvn generate-sources
```

## Notes

- The shaded JAR includes runtime dependencies.
- The original non-shaded JAR is also kept in `target/original-json2pojo-1.0.1.jar`.
- Logs are written to the relative `log/` directory.
