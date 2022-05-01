# graphql-test
graphQL test project, schema first using gqlgen tool

## reference
[article](https://www.apollographql.com/blog/graphql/golang/using-graphql-with-golang/)

## regen the code
```shell
go run github.com/99designs/gqlgen generate
```

## query sample
```graphql
#create new character, name and cliqueType must provided, isHero default is false if not provide
mutation {
    upsertCharacter(input: { name: "shawnzxx", isHero: true, cliqueType: POGUES }) {
        id
        name
        isHero
        cliqueType
    }
}
```
```graphql
#get character via id
query {
  character(id: 1) {
      id
      name
      isHero
      cliqueType
  }
}
```

```graphql
#get character list filter by CliqueType
query {
    characters (cliqueType: POGUES){
        id
        name
        isHero
    }
}
```
