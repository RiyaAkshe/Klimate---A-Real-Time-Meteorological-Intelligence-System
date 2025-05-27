The “Klimate – A Real-Time Meteorological Intelligence System”project was conceived to develop a high-performance, single-page web application capable of retrieving, processing, and visualizing real-time weather and atmospheric data through API integrations. This system was designed to showcase seamless geolocation-based weather visualization, user-controlled forecast retrieval, and intelligent data caching within a modular React architecture.This project was developed using modern web technologies such as ReactJS (TypeScript) for the frontend, Vite for performance-optimized bundling, Tailwind CSS and Shadcn UI for UI/UX, and TanStack Query (React Query) for asynchronous state management and caching. The system consumes data from OpenWeatherMap APIs, including current weather, forecast, and reverse geocoding.

System Architecture:
The Klimate system is structured across three primary architectural layers:
1. Presentation Layer (Frontend)
•	Technologies Used: ReactJS, TypeScript, Vite, Tailwind CSS, Shadcn UI
•	UI/UX Design: The application UI was designed using Shadcn UI components and styled with utility-first Tailwind CSS. The layout is fully responsive, with adaptive design patterns for desktops, tablets, and mobile screens. The UI includes a city search module, a dynamic weather dashboard, and hourly temperature visualizations.
•	Theming Support: ThemeProvider was implemented to provide dark/light mode switching, enhancing visual accessibility and personalization.

2. Application Logic Layer (State & Behavior)
•	Frameworks: ReactJS hooks and TanStack Query
•	Custom Hooks:
o	useGeolocation – Captures and manages real-time geolocation using the browser’s geolocation API.
o	useWeatherQuery – Retrieves current weather data based on coordinates.
o	useForecastQuery – Fetches hourly forecast data for the next 24–48 hours.
o	useReverseGeocodeQuery – Resolves coordinates to human-readable city names.
•	State Handling: TanStack Query efficiently handles asynchronous data fetching, caching, and revalidation. Hooks are isolated for scalability and reuse, and query keys are used to uniquely identify data requests and minimize redundancy.
•	Mutation Management: TanStack Mutation handles updates to search history and favorites.

3. Data Layer (External API & Abstraction)
•	APIs Used:
o	api.openweathermap.org/data/2.5/weather
o	api.openweathermap.org/data/2.5/forecast
o	api.openweathermap.org/geo/1.0/reverse
•	Abstraction Model: A class named WeatherAPI was created to handle all data operations. It consists of:
o	getCurrentWeather()
o	getForecastData()
o	getReverseGeocode()
•	Private Utilities: Two internal methods—createURL() and fetchData()—handle query string generation and API calls, respectively.
•	Security: API keys are stored securely in .env files and accessed via Vite’s environment interface (import.meta.env), ensuring best practices in credential handling.

Features and Functionality
The application provides a robust set of features tailored for usability, responsiveness, and data precision.
•	Location-Based Weather Retrieval: Automatically fetches and displays real-time weather based on user location.
•	City Search Functionality: Users can search for any city and retrieve current and forecasted weather data.
•	Graphical Forecast Visualization: Displays hourly temperature data using Recharts, backed by the date-fns library for time formatting.
•	Favorites and History: Allows users to store and access frequently searched cities, powered by TanStack Query mutations and local state.
•	Theme Toggle: Supports dark and light UI themes through global theming logic.
•	Responsive UI: Fully responsive interface tested across device breakpoints using Chrome DevTools and Tailwind’s media query classes.
•	Dynamic Alerts and Skeletons: Graceful handling of loading states and error boundaries through animated skeletons and fallback messages.

Development Environment
The development process was carried out using a modern frontend stack optimized for rapid prototyping and production-grade builds.
•	Code Editor: Visual Studio Code (VS Code) with extensions such as ESLint, Prettier, and Tailwind IntelliSense.
•	Package Management: Node.js and npm for dependency management.
•	Version Control: Git and GitHub for source code management and commit history tracking.
•	Testing & Debugging:
o	React Query DevTools – for inspecting live queries and caches.
o	Browser DevTools – for network tracing, console logging, and layout debugging.
o	Manual Testing – functional testing across edge cases (e.g., invalid locations, empty search input).
•	Deployment:
o	Hosting Platform: Hostinger (with custom domain integration)
