# Next.js

### What is NextJS?
Next JS is React framework for building Web Applications.

### React
With React, is is not feasible to create a full-featured application ready for production. React is a library for building user interface. AS a developer, you need to make decision about other features such as routing, data fetching and more.

### NextJS
It uses React for building user interfaces. Provides additional features that enable you to build production-ready applications. These features including routing, optimized rendering, data fetching, bundling, compiling and more.

### Why learn Next.js?
It simplifies the process of building production ready web applications.

- Routing
- API routes
- Rendering 
- Data fetching
- Styling
- Optimization
- Dev and prod build system

## Day 1 : Basic Hello World App
Lets get started
```javascript
npx create-next-app@latest
```

## Day 2 : Project Files and Folders
package.json : package dependencies and scripts

.next : NextJS folder is served
node_modules : all dependencies are installed

public : all static assets
src/app : app router

**Flow of control**

when `npm run dev` is hit, the execution is transferred to layout.tsx. page.tsx is used as children in layout.tsx

## Day 3 : React Server Components (RSC)
React Server Components is a new architecture introduced by the React team version 18 which was quickly embraced by Next.js

The architecture introduces a new way of creating React components, splitting them into two types:
- Server components
- Client components

**Server Components**

- In Next.js all components are Server components by default
- They have the ability to run tasks like reading files or fetching data from a database
- However, they don't have the ability to use hooks or handle user interactions

**Client Components**

- To create a Client component, it's necessary to add "use client" at the top of the component file
- Client components can't perform tasks like reading files, but they have the ability to use hooks and manage interactions

## Day 4: Routing
Next.js has a file-system based routing mechanism

URL paths that users can access in the browser are defined by files and folders in your codebase

Every new route like for example,`localhost:3000/blog` must have a `page.tsx` file which will be the home component.

**Nested Routes**

For more routes like `localhost:3000/blog/first` and `localhost:3000/blog/second` you must have two more folders, first and second with `page.tsx` file which serves as the home page.

Note: even if I delete layout.tsx file, it automatically generates it.

**Dynamic Routes**

Avoid creating multiple folders, as this is not a good approach. Rather, use square brackets as folder name as dynamic segments to create dynamic routes.

**Nested Dynamic Routes**

Explanatory by the name itself, dynamic routing inside dynamic routing

**Catch-all Segments**

[...slug] as the folder name, with `page.tsx` file 
[...slug] to include previous root folder `page.tsx` as well

## Day 5 : 404 Not Found Page

file name : `not-found.tsx`. Edit it as per your age

**File Colocation**

Files can be safely colocated inside the route statements

**Private Folders**

A private folder indicates that it is a private implementation detail and should not be considered by the routing system

The folder and all its subfolders are excluded from routing

Prefix the folder name with an **underscore**

**Route Groups**

Allows us t logically group our routes and project files without affecting the URL path structure

Authentication Routes : inside the auth folder we have the other folders.
(auth) -> register, login, forget-password
inside () we do not need to type auth in URL

**Layouts**

A page is UI that is unique to a route.
A layout is UI that is shared between multiple pages in the app

You can define a layout by default exploring a React component from a layout,js or layout.tsx file.

That component should accept a children prop that will be populated with a child page during rendering