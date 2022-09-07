# 2nd edition uses sql methods

    Code
      expect_error(dbplyr_analyze(con), "db_method")
    Condition
      Warning:
      <Test> uses an old dbplyr interface
      i Please install a newer version of the package or contact the maintainer
      This warning is displayed once every 8 hours.

# handles DBI error

    Code
      (expect_error(db_analyze(con, "tbl")))
    Output
      <error/rlang_error>
      Error in `db_analyze()`:
      ! Can't analyze table "tbl".
      Caused by error:
      ! dummy DBI error
    Code
      (expect_error(db_create_index(con, "tbl", "col")))
    Output
      <error/rlang_error>
      Error in `db_create_index()`:
      ! Can't create index on "tbl".
      Caused by error:
      ! dummy DBI error
    Code
      (expect_error(db_explain(con, "invalid sql")))
    Output
      <error/rlang_error>
      Error in `db_explain()`:
      ! Can't explain query.
      Caused by error:
      ! dummy DBI error
    Code
      (expect_error(db_query_fields(con, "does not exist")))
    Output
      <error/rlang_error>
      Error in `db_query_fields()`:
      ! Can't query fields.
      Caused by error:
      ! dummy DBI error
    Code
      (expect_error(db_save_query(con, "invalid sql", "tbl")))
    Output
      <error/rlang_error>
      Error in `db_save_query()`:
      ! Can't save query to "tbl".
      Caused by error:
      ! dummy DBI error
