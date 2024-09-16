I have learned following from tutorial.
## Routing Conventions
All routes must reside inside the app folder. Every file corresponding to a route must be named page.js or page.tsx. Folders represent URL path segments.
## File-Based Routing
Next.js automatically creates a layout.tsx when loading the root route, which is used to define shared UI for multiple pages.
## Dynamic & Nested Routes
Dynamic routes allow us to capture URL parameters. Every page receives route parameters via props. These parameters can be destructured using the params prop.
Nested dynamic routes allow for more complex URL structures, where route parameters can be passed down to nested routes.
## Catch-All Segments
A catch-all route captures all URL segments and maps them to a single file. This is particularly useful for documentation where we want the same layout but multiple variations of the URL.
## Custom 404 Page
we can define a custom 404 page to handle invalid routes, providing a more personalized error experience.
## File Colocation
A route isn't publicly accessible until a page.js or page.tsx file is added to the respective route segment. You can colocate files such as  components inside route folders safely.
## Private Folders
Private folders, prefixed with an underscore ( _lib), are excluded from the routing system. This helps in separating UI logic from routing logic and organizing internal project files.
## Route Groups
Route groups allow us to logically group routes without affecting the URL structure. Like (auth) can be used for authentication routes like login, register, and forgot-password.
## Layouts
Layouts define shared UI across multiple pages. we can create a layout by exporting a React component from layout.js or layout.tsx, which should accept a children prop to render nested pages.
## Route Group Layouts
Route group layouts let us organize project files without affecting the URL. This allows applying certain layouts selectively to specific segments.
## Routing Metadata
Metadata is important for SEO. Next.js allows us to define page-specific metadata using the Metadata API.
## Navigation
UI Navigation is managed via the Link component.
## Templates
Templates are similar to layouts but are re-rendered every time a user navigates to a route that shares the template, means that state is not preserved, and DOM elements are recreated.
## Loading UI
Loading UI helps display a loading state when navigating between routes. Next.js allows shared layouts to remain interactive while new route segments are being fetched and loaded.
## Error Handling
Error handling in Next.js is done via error.tsx files.
Error handling in layouts is different, as errors in layouts do not get caught by child error boundaries.
## Parallel Routes
Next.js supports parallel routes via slots, which are defined using the @folder naming convention. Slots help modularize content and allow independent route handling and sub-navigation.
## Unmatched Routes
When navigating within the UI, Next.js retains the previously active state of a slot, regardless of URL changes. On page reload, Next.js searches for a default.tsx file within unmatched slots to render content.
## Advanced Routing Patterns
Parallel Routes & Intercepting Routes: These allow you to interrupt default routing behavior to show alternative views while preserving the intended route.
## Intercepting Route Conventions
(.): Match segments on the same level.
(..): Match one level above.
(…): Match from the root app directory.
## Route Handlers:
Custom request handlers for routes that respond with JSON, unlike page routes that return HTML. Useful for creating RESTful APIs or external API calls. They run server-side, ensuring sensitive data stays secure.
## Dynamic Route Handlers
Handle requests like PATCH for partial resource modifications. Support URL query parameters, redirects, and headers.
## HTTP Headers
Request Headers: Sent by the client ( 'User-Agent', 'Authorization').
Response Headers: Sent by the server ( 'Content-Type').
## Cookies in Route Handlers
Cookies handle session management, personalization, and tracking.
Route Handlers: Cached by default with the GET method. Opt out with dynamic mode, dynamic functions ( cookies())
## Middleware: 
Used for redirection, URL rewrites, authentication, headers, and cookies management. Specify paths where it applies via custom matchers.
## Rendering in React & Next.js
Client-Side Rendering (CSR): Components are rendered in the browser.
Server-Side Rendering (SSR): Components are rendered on the server.
Suspense SSR: Unlock HTML streaming and selective hydration with <Suspense>.
## React Server Components (RSC):
Server components render only on the server.
Client components handle browser-specific interactions.
## Server Rendering Strategies
Static Rendering: HTML is generated at build time along with RSC payload .
## Dynamic Rendering:
Routes are rendered at request time, switching dynamically if cookies, headers, or search params are used.
## Streaming: 
Enables progressive UI rendering from the server.
## Opting Out of Caching: 
Set cache: 'no-store' for fetch requests to prevent caching.
## Request Memoization:
 Deduplicates requests for the same data during a single render pass.