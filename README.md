# 【flask-migrate】

#### Autogenerate will detect:

    Table additions, removals.
    Column additions, removals.
    Change of nullable status on columns.
    Change indexes and unique constraints
    Change foreign key constraints

#### Autogenerate optional detect：
	Change of column type
    Change of server default

	two switches：
	EnvironmentContext.configure.compare_type
    EnvironmentContext.configure.compare_server_default

    in env.py add compare_type=True, compare_server_default=True to context.configure.
    example:
        context.configure(connection=connection,
                      target_metadata=target_metadata,
                      process_revision_directives=process_revision_directives,
                      compare_type=True,
                      compare_server_default=True,
                      **current_app.extensions['migrate'].configure_args)