=================
Marco Polo Schema
=================

Marco Polo files (file extension ``.polo`` are `YAML <http://yaml.org/>`_ files with the following schema:

Top Level Schema
----------------

:schema_version: `Semantic Version <http://semver.org/>`_ based versioning of the schema.
:name: String. Primary identifier used when providing most generic view into your service.
:aliases: List of Strings. Alternate generic identifiers of your service.
:summary: String. Short description of your service.
:description: String. Long description of your service.
:source: String URI. Link to source code repository.
:tracker: String URI. Link to issue/bug tracking system for project.
:website: String URI. Link to web site/portal for system.
:owner: String SSO or List of Strings. SSO(s) of owner responsible for system.
:environment_name_template: String. Template for naming of environments.
:environments: List of Environment objects (See Environment). List of system environments.
:parent_application: String (optional). If this system is an independent component of a larger family of systems, name it here.
:status: String (optional - default to active). System status. Examples: "active", "decommissioned", "deprecated", "development"
:rackers_supported: Integer (optional). Number of Rackers supported by this system.
:customers_supported: Integer (optional). Number of Customers supported by this system.


Environment Schema
------------------

:tier: String. Name of environment tier. Examples: "dev", "staging", "prod".
:datacenters: List of Strings. Datacenter abbreviation containing the environment. Examples: "dc2", "dc2".
:aliases: List of String URIs. List of DNS names resolving to this environment.
:dependencies: List of Dependency Schema. List of DNS names this system is dependent on.
:infrastructure: String. Type of infrastructure this environment depends on. Examples: "publiccloud", "privatecloud", "dedicated".
:default: Boolean (optional). True for the default environment (usually production).

Dependency Schema
-----------------
:endpoint: URI of system this system is dependent on.
:auth_rules: String or List of Strings (optional). Fine grained authorization rules that this system requires to use the dependency.
