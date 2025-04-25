# frontend-speedrun
The following plan was created with Gemini 2.5 Pro.

# Plan
**Overall Goal:** To rapidly gain foundational knowledge and practical experience in building interactive user interfaces with React for structure/logic and TailwindCSS for styling. This plan prioritizes *doing* over exhaustive theory.

**Prerequisites:** Basic HTML structure knowledge, basic CSS concepts (selectors, properties), familiarity with JavaScript fundamentals (variables, functions, objects, arrays, async/await optional but helpful), comfortable with terminal/command line, Node.js/npm installed.

---

# **Day 1: Setup, React Fundamentals & Static Styling with Tailwind**

- **Objective:** Set up a modern development environment, grasp core React concepts (JSX, Components, Props), understand Tailwind's utility-first approach, and build a static UI component.

- **Morning (Approx. 3-4 hours): Environment & Core Concepts**

    - **Topics:** Development environment setup, JSX syntax, Functional Components, Props, TailwindCSS utility-first basics.

    - **Tasks:**

        1. Initialize a new React project using Vite: `npm create vite@latest my-react-app --template react` (or `react-ts` for TypeScript).

        2. Install TailwindCSS following their official guide for Vite: [https://tailwindcss.com/docs/guides/vite](<https://tailwindcss.com/docs/guides/vite>).

        3. Run the development server (`npm run dev`) and see the default app.

        4. Read/Skim the React Quick Start guide: [https://react.dev/learn](<https://react.dev/learn>) (Focus on "Describing the UI").

        5. Understand JSX: How it mixes HTML-like syntax with JavaScript.

        6. Create your first functional component in a separate file (e.g., `src/components/MyComponent.jsx`) and import/use it in `src/App.jsx`.

        7. Pass data from `App.jsx` to `MyComponent` using props.

        8. Read Tailwind's "Core Concepts": [https://tailwindcss.com/docs/utility-first](<https://tailwindcss.com/docs/utility-first>).

        9. Experiment: Apply basic Tailwind classes directly in your components (`p-4`, `m-2`, `bg-blue-500`, `text-white`, `font-bold`, `flex`, `rounded-lg`, `shadow-md`). See changes instantly via Vite's Hot Module Replacement (HMR).

    - **Resources:** Vite Docs, Tailwind Docs (Setup, Core Concepts), React Docs (Learn Section).

    - **Focus Points:** Getting the dev environment running smoothly. Understanding that React components are JavaScript functions returning JSX. How props pass data down. Grasping the "utility class for everything" concept of Tailwind.

- **Afternoon (Approx. 4-5 hours): Project 1 - Static Profile Card**

    - **Project Focus:** Build a non-interactive component using React structure and Tailwind styling.

    - **Tasks:**

        1. Create a new component file (e.g., `src/components/ProfileCard.jsx`).

        2. Structure the card using JSX (divs, img, headings, paragraphs). Include elements like an avatar image, name, title/role, short bio, and maybe some skill tags.

        3. Apply Tailwind classes extensively for layout (`flex`, `flex-col`, `items-center`, `space-y-4`), padding/margin (`p-*`, `m-*`), sizing (`w-64`, `max-w-sm`), colors (`bg-*`, `text-*`), typography (`text-lg`, `font-semibold`), borders (`border`, `rounded-full`), shadows (`shadow-lg`).

        4. (Optional) Break the card into smaller reusable components (e.g., `Avatar.jsx`, `UserInfo.jsx`). Pass data down using props.

        5. Render multiple instances of `ProfileCard` in `App.jsx`, passing different static props to each to see reusability.

        6. Experiment with Tailwind's responsive prefixes (`md:flex-row`, `lg:text-xl`) to make the card adapt to different screen sizes.

    - **Resources:** Tailwind Docs (browse sections like Layout, Flexbox & Grid, Spacing, Sizing, Typography, Backgrounds, Borders, Effects), React Docs (Components & Props).

    - **Focus Points:** Translating a visual design concept into JSX structure. Applying Tailwind utilities logically for styling. Component composition. Responsive design basics with Tailwind.

- **Evening (Flexible): Review & Polish**

    - **Tasks:** Review the React concepts (Components, Props, JSX). Review Tailwind utility classes used. Refine the styling of the Profile Card. Try adding hover effects with Tailwind (`hover:bg-gray-100`, `hover:shadow-xl`).

    - **Resources:** Your code, React/Tailwind Docs.

    - **Focus Points:** Solidifying understanding of Day 1 concepts. Ensuring comfort with the basic workflow.

---

# **Day 2: Interactivity, State & Lists**

- **Objective:** Learn how to make React components interactive using state and event handlers, and how to render dynamic lists of data.

- **Morning (Approx. 3-4 hours): State & Events**

    - **Topics:** `useState` hook, handling events (`onClick`, `onChange`), conditional rendering, rendering lists (`.map()`).

    - **Tasks:**

        1. Read the React docs section on "Adding Interactivity": [https://react.dev/learn/adding-interactivity](<https://react.dev/learn/adding-interactivity>).

        2. Understand the `useState` hook: how it declares state variables and their setter functions.

        3. Implement a simple counter component with buttons to increment/decrement a number stored in state.

        4. Implement a controlled input field: Use `useState` to store the input's value and update it via the `onChange` event handler.

        5. Learn how state updates trigger re-renders.

        6. Practice conditional rendering: Displaying different JSX based on a state variable (e.g., show/hide element, different text content).

        7. Read about rendering lists: Using the JavaScript `.map()` method on an array in state to render multiple components. Understand the importance of the `key` prop.

    - **Resources:** React Docs (Learn Section - Adding Interactivity, Rendering Lists).

    - **Focus Points:** The `useState` syntax and flow. The concept of controlled components for forms. Immutability when updating state (especially arrays/objects - create new ones!). The purpose and necessity of the `key` prop in lists.

- **Afternoon (Approx. 4-5 hours): Project 2 - Interactive To-Do List**

    - **Project Focus:** Build a classic To-Do list application to practice state management, event handling, and list rendering.

    - **Tasks:**

        1. Create a `TodoList.jsx` component.

        2. Use `useState` to manage the list of tasks (an array of objects, e.g., `[{ id: 1, text: 'Learn React', completed: false }]`).

        3. Use `useState` to manage the value of the input field for adding new tasks.

        4. Create an input field and an "Add Task" button.

        5. Implement the `onChange` handler for the input field to update its state.

        6. Implement the `onClick` handler for the button (or form `onSubmit`):

            - Prevent default form submission if using a form.

            - Create a new task object (with unique id, text from input state, `completed: false`).

            - Update the tasks array state by creating a *new* array containing the old tasks plus the new one (`setTasks([...tasks, newTask])`).

            - Clear the input field.

        7. Render the list of tasks using `.map()` on the `tasks` state array. Each task should be rendered by a separate component (e.g., `TodoItem.jsx`) receiving task data via props. Assign a unique `key` prop (`task.id`).

        8. (Add features) In `TodoItem.jsx`, add:

            - A button/checkbox to toggle the `completed` status. This requires passing a function down from `TodoList` via props that updates the main `tasks` array state (find the task by id and update its `completed` flag, remembering immutability).

            - A button to delete the task. This also requires a function passed down via props that updates the main `tasks` array state (using `.filter()` to create a new array without the deleted task).

        9. Apply Tailwind styling to the input, button, list, list items, and add visual distinction for completed tasks (e.g., `line-through`, different text color using conditional classes like `text-gray-500 ${task.completed ? 'line-through' : ''}`).

    - **Resources:** React Docs (`useState`, events, lists), Tailwind Docs (Forms, Buttons, general utilities), JavaScript array methods (`.map`, `.filter`).

    - **Focus Points:** Managing array state immutably. Controlled form inputs. Passing functions as props to child components to update parent state. Conditional styling based on state.

- **Evening (Flexible): Refine & Review**

    - **Tasks:** Polish the To-Do list styling. Add minor features (e.g., show task count). Review `useState`, event handling, list rendering, and prop drilling (passing data/functions down).

    - **Resources:** Your code, React/Tailwind Docs.

    - **Focus Points:** Ensuring understanding of how data flows and state updates trigger UI changes.

---

# **Day 3: Side Effects, Global Context & Advanced Styling**

- **Objective:** Learn to handle asynchronous operations and external interactions using `useEffect`, share state across distant components using `useContext`, and explore more advanced Tailwind features like dark mode.

- **Morning (Approx. 3-4 hours): Handling Side Effects with `useEffect`**

    - **Topics:** The `useEffect` hook, dependency arrays, fetching data, component lifecycle interactions.

    - **Tasks:**

        1. Read the React docs on "Synchronizing with Effects": [https://react.dev/learn/synchronizing-with-effects](<https://react.dev/learn/synchronizing-with-effects>).

        2. Understand the purpose of `useEffect`: running code *after* render, interacting with outside systems (APIs, timers, DOM).

        3. Grasp the importance of the dependency array:

            - `[]`: Run effect only once after initial render (mount).

            - `[dep1, dep2]`: Run effect after initial render AND whenever `dep1` or `dep2` changes.

            - No array (avoid!): Run effect after *every* render.

        4. Implement a simple component that fetches data from a public API (e.g., `https://jsonplaceholder.typicode.com/posts/1`) inside a `useEffect` with an empty dependency array `[]`.

        5. Use `useState` to store the fetched data, a loading state, and an error state. Display appropriate UI for each state (Loading..., Error message, Fetched data).

        6. (Optional) Understand effect cleanup functions (returning a function from `useEffect`) for things like clearing timers or subscriptions.

    - **Resources:** React Docs (useEffect), Fetch API (MDN Docs), JSONPlaceholder API.

    - **Focus Points:** The "when does my effect run?" question (dependency array!). Handling async operations within `useEffect`. Managing loading and error states is crucial for real-world apps.

- **Afternoon (Approx. 4-5 hours): Global State with `useContext` & Project Work**

    - **Topics:** Prop drilling problem, `createContext`, `Context.Provider`, `useContext` hook, advanced Tailwind (dark mode).

    - **Tasks:**

        1. Read React docs on "Passing Data Deeply with Context": [https://react.dev/learn/passing-data-deeply-with-context](<https://react.dev/learn/passing-data-deeply-with-context>).

        2. Understand why prop drilling (passing props through many intermediate components) can be cumbersome.

        3. Learn the `useContext` pattern: Create context, provide value at a higher level, consume value in any descendant component.

        4. **Project Idea: Theme Switcher**

            - Create a `ThemeContext.jsx` file (`export const ThemeContext = createContext(null);`).

            - Create a `ThemeProvider` component that wraps your `App`. It uses `useState` to hold the theme (`'light'` or `'dark'`) and provides `{ theme, toggleTheme }` via `ThemeContext.Provider`.

            - Configure Tailwind's dark mode in `tailwind.config.js` (e.g., `darkMode: 'class'`).

            - In `ThemeProvider`, use `useEffect` to add/remove the `dark` class to `document.documentElement` based on the theme state.

            - In `App.jsx` or other components, use `useContext(ThemeContext)` to get the current theme.

            - Add a button somewhere that calls `toggleTheme` from the context.

            - Apply `dark:` variants in Tailwind classes throughout your app (e.g., `bg-white dark:bg-gray-900`, `text-black dark:text-white`).

        5. **Alternatively:** Refactor the data fetching component from the morning to potentially use context if you imagine the fetched data needs to be available widely.

    - **Resources:** React Docs (useContext), Tailwind Docs (Dark Mode, Configuration).

    - **Focus Points:** Recognizing prop drilling. The Provider/Consumer pattern of Context. How `useContext` makes accessing global-like state easier. Setting up and using Tailwind's `dark:` variants.

- **Evening (Flexible): Polish & Explore**

    - **Tasks:** Ensure the theme switcher or data fetching component works correctly. Refine styling using `dark:` variants. Explore other Tailwind features like `group-hover:` or basic configuration changes in `tailwind.config.js`. Review `useEffect` and `useContext`.

    - **Resources:** Your code, React/Tailwind Docs.

    - **Focus Points:** Solidifying the use cases for `useEffect` and `useContext`. Practical application of dark mode.

---

# **Day 4: State Management Patterns, Routing & Mock Authentication**

- **Objective:** Learn patterns for managing more complex state, implement client-side routing for a multi-page feel, and simulate a basic user authentication flow.

- **Morning (Approx. 3-4 hours): `useReducer`, State Libs Intro & Routing Basics**

**Topics:** `useReducer` hook, limitations of `useState`/`useContext` for complex global state, brief intro to global state libraries (concept, not deep dive), client-side routing with `react-router-dom`.

- Tasks:

1. Read React docs on1 `useReducer`: [https://react.dev/learn/extracting-state-logic-into-a-reducer](<https://react.dev/learn/extracting-state-logic-into-a-reducer>). Understand how it helps manage state transitions, especially when state logic is complex or involves multiple related pieces. Compare it to `useState`. Implement a simple counter or form using `useReducer`.

2. Discuss (with yourself/resources) *why* libraries like Redux Toolkit or Zustand exist (devtools, middleware, performance optimizations for large-scale state, standardized patterns). Look at their main websites briefly. *Goal: Awareness, not implementation today*.

3. Install React Router: `npm install react-router-dom`.

4. Read the React Router basic tutorial: [https://www.google.com/search?q=https://reactrouter.com/en/main/start/tutorial](<https://www.google.com/search?q=https://reactrouter.com/en/main/start/tutorial>).

5. Set up basic routing: Wrap your app in `<BrowserRouter>`, define routes using `<Routes>` and `<Route path="..." element={<YourComponent />}>`. Create simple page components (`HomePage`, `AboutPage`). Use `<Link to="...">` for navigation. Learn about `useNavigate`.

- **Resources:** React Docs (useReducer), Zustand/Redux Toolkit websites (overview), React Router Docs.

- **Focus Points:** When `useReducer` is beneficial. Understanding the *problem* that global state libraries solve. The core components of React Router (`BrowserRouter`, `Routes`, `Route`, `Link`).

- **Afternoon (Approx. 4-5 hours): Project - Multi-Page App with Mock Auth**

    - **Project Focus:** Combine routing and context to create a simple SPA with a protected area requiring mock login.

    - **Tasks:**

        1. Define routes for `/`, `/login`, `/dashboard` (protected).

        2. Create page components: `HomePage`, `LoginPage`, `DashboardPage`. Add a simple `Navbar` component with `&lt;Link&gt;` elements.

        3. Create an `AuthContext` using `createContext` and a corresponding `AuthProvider` component.

        4. The `AuthProvider` should use `useState` (or `useReducer`) to manage `isAuthenticated` (boolean) and maybe a `user` object. It should provide these values and `login`/`logout` functions via context.

        5. Implement the `LoginPage`: A simple form (no real password check needed). On submit, call the `login` function from `useContext(AuthContext)` (which sets `isAuthenticated = true`) and use `useNavigate` to redirect to `/dashboard`.

        6. Implement the `logout` function in the `AuthProvider` (sets `isAuthenticated = false`) and add a logout button (e.g., in the Navbar) that calls it and redirects to `/`.

        7. Create a `ProtectedRoute` component:

            - It gets the `isAuthenticated` value from `AuthContext`.

            - If true, it renders its children (or `<Outlet />` from React Router).

            - If false, it uses the `<Navigate to="/login" replace />` component from React Router to redirect.

        8. Wrap the `DashboardPage` route in `App.jsx` with `<ProtectedRoute>`.

        9. In the `Navbar`, conditionally display "Login" or "Logout" / user info based on `isAuthenticated` from context.

        10. (Optional) Use `localStorage` and `useEffect` within `AuthProvider` to persist the login state across page refreshes.

        11. Style all pages and components using Tailwind.

    - **Resources:** React Router Docs, React Context Docs, your previous Context code, `localStorage` MDN Docs.

    - **Focus Points:** Combining routing and context for practical application. Implementing protected routes. Conditional rendering based on authentication state. Basic SPA structure.

- **Evening (Flexible): Final Polish & Review**

    - **Tasks:** Test the complete auth flow (login, access dashboard, logout, try accessing dashboard when logged out). Polish styling. Review routing concepts, context usage for auth, and `useReducer` (if used). Reflect on the four days.

    - **Resources:** Your project code, previous resources.

    - **Focus Points:** Ensuring the mock auth flow works as expected. Consolidating knowledge from all four days.

---

**Project Explanations Summary:**

1. **Static Profile Card (Day 1):**

    - **Purpose:** Practice basic React component structure (JSX, props) and fundamental TailwindCSS utility classes for layout, spacing, typography, color, and appearance without worrying about state or events.

    - **Key Elements:** Image (avatar), text (name, title, bio), potentially tags/badges.

    - **Tech Focus:** React components, props, JSX syntax, Tailwind utility classes (`flex`, `p-*`, `m-*`, `bg-*`, `text-*`, `rounded-*`, `shadow-*`, responsive prefixes).

2. **Interactive To-Do List (Day 2):**

    - **Purpose:** Introduce state management (`useState`), handle user input (`onChange`) and actions (`onClick`), render dynamic lists (`.map()`), and pass functions down as props for child-to-parent communication.

    - **Key Elements:** Input field, "Add" button, list of tasks, checkbox/button per task for completion, button per task for deletion.

    - **Tech Focus:** `useState` for input value and task array, event handlers, controlled components, list rendering with `key` props, updating array state immutably (`filter`, spread operator), conditional rendering/styling.

3. **Data Fetching Component / Theme Switcher (Day 3):**

    - **Purpose:** Learn `useEffect` for side effects like API calls (Data Fetching) OR `useContext` for managing global-like state easily (Theme Switcher), and explore advanced Tailwind (like `dark:` variants).

    - **Key Elements (Data Fetching):** Loading indicator, error message display, formatted display of fetched data.

    - **Key Elements (Theme Switcher):** Toggle button, application-wide style changes based on selected theme.

    - **Tech Focus:** `useEffect` (dependency array, async/await inside), `useState` for loading/error/data states OR `useContext` (createContext, Provider, useContext), `tailwind.config.js` (dark mode setup), `dark:` utility variants.

4. **Multi-Page App with Mock Auth (Day 4):**

    - **Purpose:** Implement client-side routing for SPA navigation, manage shared authentication state using Context, and protect specific routes based on that state.

    - **Key Elements:** Multiple page components (Home, Login, Dashboard), Navigation bar (`<Link>`), Login form, Protected dashboard area, Logout button, `AuthContext` and `AuthProvider`, `ProtectedRoute` component logic.

    - **Tech Focus:** `react-router-dom` (`BrowserRouter`, `Routes`, `Route`, `Link`, `useNavigate`, `Maps`, `Outlet`), `useContext` for managing auth state globally, combining routing and context, conditional rendering for UI elements and route access.




