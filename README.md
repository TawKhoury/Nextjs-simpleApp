# Nextjs-simpleApp 

ReactJs+NodeJs=NextJs

# simple NextJS app 

## TV information to your website or app

***Visit https://learnnextjs.com to get started with Next.js.***

**using tvmaze api : https://www.tvmaze.com/api**

## How to use

### Setup

Install:

```bash
git clone https://github.com/TawKhoury/Nextjs-simpleApp.git
npm install next react react-dom --save
```

Build and start:

build .next directory
```bash
npm run buid  
```

run app on localhost:3000
```bash
npm run start
```
##
### define the `getInitialProps` lifecycle method for stateless components: 

### Example:
`post.js`

```jsx
Post.getInitialProps = async function (context) {
    const { id } = context.query
    const res = await fetch(`https://api.tvmaze.com/shows/${id}`)
    const show = await res.json()

    console.log(`Fetched show: ${show.name}`)

    return { show }
}
```

`getInitialProps` receives a context object with the following properties:

- `pathname` - path section of URL
- `query` - query string section of URL parsed as an object
- `asPath` - the actual url path
- `req` - HTTP request object (server only)
- `res` - HTTP response object (server only)
- `jsonPageRes` - [Fetch Response](https://developer.mozilla.org/en-US/docs/Web/API/Response) object (client only)
- `err` - Error object if any error is encountered during the rendering


## change TV information to your website
##
`index.js`
```jsx
Index.getInitialProps = async function() {
    const res = await fetch('http://api.tvmaze.com/search/shows?q=batman')
    const data = await res.json()

    console.log(`Show data fetched. Count: ${data.length}`)

    return {
        shows: data
    }
}
```
-Change fetch content:
```jsx
    const res = await `fetch('http://api.tvmaze.com/search/shows?q=batman')`
```
to any api from 'http://api.tvmaze.com/search' 


### License

React is [BSD licensed](./LICENSE). We also provide an additional [patent grant](./PATENTS).

React documentation is [Creative Commons licensed](./LICENSE-docs).

Examples provided in this repository and in the documentation are in [https://learnnextjs.com]tutorial,github : https://github.com/zeit/next.js

