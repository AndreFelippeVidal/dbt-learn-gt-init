Welcome to your new dbt project!

### Using the starter project

Try running the following commands:
- dbt build


### Resources:
- Learn more about dbt [in the docs](https://docs.getdbt.com/docs/introduction)
- Check out [Discourse](https://discourse.getdbt.com/) for commonly asked questions and answers
- Join the [chat](http://slack.getdbt.com/) on Slack for live discussions and support
- Find [dbt events](https://events.getdbt.com) near you
- Check out [the blog](https://blog.getdbt.com/) for the latest news on dbt's development and best practices


## Commands:

dbt init -> setup profile
dbt compile -> checks if the files compile without errors
dbt run -> runs the sql inside the data platfotrm

dbt source freshness -> check freshness
dbt deps -> install packages


leverage codegen package from dbtlabs - command below generates the source yaml for the tables inside the database and schema
dbt run-operation generate_source --args '{"schema_name": "jaffle_shop", "database_name": "raw"}'

This one below leverages the codegen package as the one before, to generate the source model based on the parameters
dbt run-operation generate_base_model --args '{"source_name": "jaffle_shop", "table_name": "customers"}'

dbt test -> runs all the tests
dbt test --select stg_stripe___payments -> testing specific model
dbt test -s source:jaffle_shop -> testing specific source

Rule for tets:
test sources for data integrity and test models for transformation integrity
