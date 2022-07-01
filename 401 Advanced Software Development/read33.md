## @Connection

- Allows you to specify the relationship
- one-to-one, one-to-many, and many-to-one
- Use two one-to-many relationships to make a many-to-many relationship

#### Has One

````Java
type Project @model {
  id: ID!
  name: String
  teamID: ID!
  team: Team @connection(fields: ["teamID"])
}

type Team @model {
  id: ID!
  name: String!

        mutation CreateProject {
        createProject(input: { name: "New Project", teamID: "a-team-id"}) {
        id
        name
        team {
        id
        name
        }
        }
        }
}
````
- [Credit](https://docs.amplify.aws/cli-legacy/graphql-transformer/directives/#connection)

#### Has Many


````Java
type Post @model {
  id: ID!
  title: String!
  comments: [Comment] @connection(keyName: "byPost", fields: ["id"])
}


````
- [Credit](https://docs.amplify.aws/cli-legacy/graphql-transformer/directives/#connection)

#### Has Many to Many

````Java
type Post @model {
  id: ID!
  title: String!
  editors: [PostEditor] @connection(keyName: "byPost", fields: ["id"])
}

# Create a join model and disable queries as you don't need them
# and can query through Post.editors and User.posts
type PostEditor
  @model(queries: null)
  @key(name: "byPost", fields: ["postID", "editorID"])
  @key(name: "byEditor", fields: ["editorID", "postID"]) {
  id: ID!
  postID: ID!
  editorID: ID!
  post: Post! @connection(fields: ["postID"])
  editor: User! @connection(fields: ["editorID"])
}

type User @model {
  id: ID!
  username: String!
  posts: [PostEditor] @connection(keyName: "byEditor", fields: ["id"])
}
````
- [Credit](https://docs.amplify.aws/cli-legacy/graphql-transformer/directives/#connection)

#### Limit

````Java
type Post @model {
  id: ID!
  title: String!
  comments: [Comment] @connection(limit: 50)
}

type Comment @model {
  id: ID!
  content: String!
}
````
- [Credit](https://docs.amplify.aws/cli-legacy/graphql-transformer/directives/#connection)



## GraphQL

- `@model` top level entities in generated API protected via `@auth`
- `@key` DynamoDB is a key value database
- `@auth` Authorization keys needed for GraphQL
- `@connection` Allows you to specify the relationship one-to-one, one-to-many, and many-to-one. Use two one-to-many relationships to make a many-to-many relationship
- `@function` Allows you to configure AWS Lambda resolvers within AWS AppSyncAPI
- `@http` HTTP resolvers 
- `@predictions` Queries an orchestration 
- `@searchable` directive handles streaming data of model you might observe duplicate records on search operations
- `@versioned` directive adds versioning and conflict detection


### Amplify GraphQL schemas

- `@aws_api_key`
- `@aws_iam`
- `@aws_oidc`
- `@aws_cognito_user_pools`
- `@aws_auth`
- `@aws_subscribe`

### 3rd party directives

- `@algolia` serverless search to Amplify
- `@ttl` auto delete features in Amplify
- `@firehose` simple interceptor for mutations and quereies
- `@retain` enables for DynamoDB

### Things I want to know more about

- AWS way of authentication and authorization


> ## Reference and Citation

> Joshua McCluskey