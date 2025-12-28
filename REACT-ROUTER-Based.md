1️⃣ What is React Router and why do we need it?

React Router enables client-side routing in React applications, allowing users to navigate between different components while staying on a single page. It improves performance and user experience by updating the UI based on the URL without reloading the entire page.

 why do we need it?

 We need it because single application load page only one time intially,so to update content dynamically we need routing without loading page

 Differnece between client side vs server side

 Feature	Client-side Routing (React Router)	Server-side Routing
Page reload	❌ No	✅ Yes
Where routing happens Browser (JavaScript) Server
Speed	Fast	Slower
User experience	Smooth	Less smooth
Used in SPA (React, Angular) Traditional websites


What is BrowserRouter?

BrowserRouter is a wrapper component that enables routing in a React application.
It uses the browser’s History API to keep the UI in sync with the URL.

What is Routes?

Routes is a container that contain  multiple route.
It ensures that only the best matching route is rendered.

What is Route?

Route is used to map a URL path to a component.
When the URL matches the path, the corresponding component is rendered.

What is useParams?
useParams is a React Router hook used to read dynamic URL parameters in  a component.

What is useNavigate?

useNavigate is a hook used to navigate programmatically between routes.

What is <Link>?
<Link> is used for navigation without page reload.

What is nested routing?
Nested routing is a routing technique where routes are defined inside other routes.
“<Outlet> is used to render child routes inside a parent route layout.”

what is route protection
Route protection is a technique used to restrict access to certain routes based on user authentication

What happens when a route does not match?
“If no route matches, React Router shows nothing unless we define a fallback * route.”
