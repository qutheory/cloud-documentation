# Architecture

Design notes and guidelines about Vapor Cloud's architecture.

## API Microservice

API microservices are named following the format `ModuleAPI`. The administrative module, for example, is named `AdminAPI`.

APIs are accessible via `api.vapor.cloud` followed by the module name in lower case. For example, `api.vapor.cloud/admin`.

GitHub repositories and folder names for the microservices follow the format `module-api`. For Example, `admin-api`.
