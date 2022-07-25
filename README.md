# StrapiGallery

ArtCatalog

If the server is not already running, in your terminal, cd into the strapiGallery folder and run 'npm run develop' (or yarn develop) to launch it.

The admin panel of Strapi runs at
http://localhost:1337/admin

The APIs are available at
http://localhost:1337/api/categories
http://localhost:1337/api/art-projects

Start your app and open your browser at
http://localhost:1337/graphql
(opens new window). You should now be able to access the GraphQL Playground that will help you to write your GraphQL queries and mutations.

Helpful guidance on querying API:
v=https://docs.strapi.io/developer-docs/latest/developer-resources/database-apis-reference/graphql-api.html#filters

API query for all categories:
query{
categories{
data{
id
attributes{
Name
}
}
}}

API query for single category, in this instance id:1 :
query{
category (id:1){
data{
id
attributes{
Name
}
}
}}

API query for single category, in this instance Name:Painting :
query{
categories(filters: {Name: {eq: "Painting"}}){
data{
id
attributes{
Name
}
}
}}

API query for all art-projects:
query{
artProjects{
data{
id
attributes{
Name
Medium
}
}
}}

API query for single art-project, in this instance id:1 :
query{
artProject (id:1){
data{
id
attributes{
Name
Medium
}
}
}}

API query for single art-project, Name:"Shiba Frog 🐸 " :
query{
artProjects(filters: {Name: {eq:"Shiba Frog 🐸 "}}){
data{
id
attributes{
Name
Medium
}
}
}}

API query for single art-project, Medium:"Shiba Frog 🐸 " :
query{
artProjects(filters: {Medium: {contains:"FH_4_K_6515042512.png"}}){
data{
id
attributes{
Name
Medium
}
}
}}
