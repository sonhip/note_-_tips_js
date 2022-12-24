# Learning new Tech

##  What is grapthQL?
*  	GrapthQL is an open source data query and manipulation language for APIs and runtime for fulfilling queries with existing data. Its an alternative to a REST api, with some added benefits such as the ability to request the exact data that you want


## useCallback and useMemo
*  Both expect a function and an array of dependencies. The difference is that useCallback returns its function when the dependencies change while useMemo calls its function and returns the result.

## ReactNative 
* borderRadius on Text tag not work on IOS, so you can wrap Text inside View tag to css
* try to convert View ->  scrollView => scrollView should be inside View to avoid changes of View tag CSS
* FlatList vs scrollView => scrollView render all item even it can not be visible, flatList just only loading data when its needed. Should use FlatList with dynamic data and long list, performance 


## Reactjs Tip: 
* 	 Can useRef instead of using useState in Input in form
* 	 UseState should take an arrow func to get fresh state
* 	 React.lazy, (suspense) for  increment perform project

## NextJS
<img src="https://scontent.xx.fbcdn.net/v/t1.15752-9/320194037_3227245000873076_2033823340212475108_n.jpg?_nc_cat=104&ccb=1-7&_nc_sid=aee45a&_nc_ohc=fECk3kC8nI8AX_DS_2F&_nc_ad=z-m&_nc_cid=0&_nc_ht=scontent.xx&oh=03_AdQsYuLH1uYGGxNRSUTTnmoV9tRYD9OGII2sVbMekIA4bQ&oe=63C8103C" alt="MarineGEO circle logo" style="height: 500px; width:800px;"/>

- Define:
    - the react framework for production
    - enhances react app and adds more features
    - lots of build-in features(eg: routing) to solve common problem and clear guidance and how to use those
    - solves for almost product ready react app

- Key features: 
    - Pre render on server => for search engine => SEO
    - Blending server side and client side => fetch data on server and render finishes pages
    - File base routing
    - Can build fullstack, adding backend code along
    - Up to NextJS 13, you needed to add a nested `<a>` element in your `<Link>` if you wanted to add custom attributes (e.g., className) to the anchor element.
    - React.query.slug to get slug on URL as an array

- Pre-rendering: render some html on server
- Hydrate: process attach event listener in html already rendered
- Next.js pre-renders all pages that have no dynamic data.
- 2 ways of pre rendering: 
    - static generation: pre-render when build,
    - server side rendering: sometimes, you need to pre-render for every request OR you need access to the request object (eg: cookies). Nextjs allow run "real erver side code" by getServerSideProps func
- Incremental static genertation : pre-generate a page, but then you can also tell nextjs that a given page should be generation again for every incoming request at most every X seconds via “revalidate”
- SSG using with getStaticProps, if aagrument is prams of page’id, we need using getStaticPath follow
- in function getStaticPath, fallback property used:
	-	fallback: true: page is not pre-generated, they are only pre-generated when they are needed. Just pre-gen pages that users visit frequenly in the list `path: [{params: {pageId: "1"}]`. If you directly to page by enter URL, you actully get an error that can not read undefined of property. It just work by click via `Link`
	- 	fallback: false: default, prepare to gen all the page, even the page not necessary or rarely visited
	-  fallback: "blocking": not to check if page isnt loaded, wait to page fully be pre-gen on server, then it takes a little bit longer.

* UseRouter.query => return object has query in url
* A tag diff Link in nextjs cause a tag send http request make changes, reload page and state, link in next not do the same, link tag pre fetch data when hover
* Route.replace => cant go back this page after navigate

1. Note:
	* when we use client side data fetching? some data doesn't need to be pre-gen
		* data change with high frequency
		* highly user-specific data
		* partial data (eg: data a part of page)

## Javascript Advance
1. Closure in Js
 * Lexical scope defines how variables name are resolved in nested function
 * Nested child function have access to the scope of their parents function
 * This is often confused with closure but lexical is scope is only an import part of closure
 * w3schools: a closure is a function having access to the parent scope, even after the parent function has closed.
 * A closure is created when we define a function, not when a function is executed

## Interview Tips
* Triple equals (===) checks for strict equality, which means both the type and value must be the same. Double equals (==) on the other hand first performs type coercion so that both operands are of the same type and then applies strict comparison.
* The latest ECMAScript standard defines seven data types, six of them being primitive: Boolean, Null, Undefined, Number, String, Symbol and one non-primitive data type: Object.

	* Mention of newly added Symbol data type
	* Array, Date and function are all of type object
	* Functions in JavaScript are objects with the capability of being callable

* The virtual DOM (VDOM) is a representation of the real DOM in the form of plain JavaScript objects. These objects have properties to describe the real DOM nodes they represent: the node name, its attributes, and child nodes. The previous virtual DOM can be compared to the new virtual DOM very quickly in comparison. Once the changes between the old VDOM and new VDOM have been calculated by the diffing engine of the framework, the real DOM can be patched efficiently in the least time possible to match the new state of the application.
* Context provides a way to pass data through a tree of React components, without having to manually pass props.

* Context is designed to share data that is considered global for a tree of React components.


