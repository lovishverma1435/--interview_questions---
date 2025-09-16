➤ React Basics & Advanced Concepts
1. React ka virtual DOM kya hai aur kaise kaam karta hai?

Answer:
✔ Virtual DOM ek lightweight JS object representation hota hai actual DOM ka
✔ State change hone par diffing algorithm update karta hai sirf required DOM nodes
✔ Performance optimize hoti hai

2. React Hooks kya hai aur kyu use karte hain?

Answer:
✔ Functional components me state aur lifecycle handle karne ke liye
✔ useState, useEffect, useReducer, useRef, useContext common hooks

3. useEffect vs useLayoutEffect ka difference

Answer:
✔ useEffect – async side effects after render, non-blocking
✔ useLayoutEffect – sync side effects before painting DOM, blocking

4. React context kab aur kaise use karte hain?

Answer:
✔ Global state manage karne ke liye (theme, auth)
✔ Avoid prop drilling

const ThemeContext = React.createContext();
<ThemeContext.Provider value={theme}>{children}</ThemeContext.Provider>

5. React performance optimization techniques

Answer:
✔ Memoization – React.memo for components, useMemo for expensive calculations
✔ useCallback for function references
✔ Virtualization (react-window, react-virtualized) for large lists

6. React reconciliation kaise kaam karta hai?

Answer:
✔ Virtual DOM diffing algorithm update karta hai sirf required parts of DOM
✔ Key props important for list rendering

7. useReducer vs useState kab use karte hain?

Answer:
✔ useState – simple state
✔ useReducer – complex state logic ya multiple state transitions

8. Controlled vs Uncontrolled components

Answer:
✔ Controlled – React state control karta hai input value
✔ Uncontrolled – DOM handles input value, useRef se access hota hai

9. React error boundaries kya hai?

Answer:
✔ Class component me componentDidCatch use karke errors catch karte hain
✔ UI crash prevent aur fallback render karte hain

10. React Suspense & lazy loading

Answer:
✔ Component ko lazy load karne ke liye React.lazy()
✔ Suspense fallback UI show karte hain loading ke time

const LazyComp = React.lazy(()=>import('./LazyComp'));
<Suspense fallback={<Loader />}><LazyComp /></Suspense>

11. React refs ka use

Answer:
✔ DOM access ya value persist across renders
✔ useRef hook functional components me use

12. React keys ka importance

Answer:
✔ List rendering me identity maintain karte hain
✔ Efficient DOM updates ke liye

13. Higher Order Components (HOC) kya hai?

Answer:
✔ Function jo ek component ko wrap karke enhanced component return kare
✔ Reusable logic share karne ke liye

14. Render props pattern

Answer:
✔ Component as a function prop
✔ Logic share aur flexibility

15. Custom hooks banane ke rules

Answer:
✔ Function starting with use
✔ State aur lifecycle hooks ka reuse
✔ Side effects handle

16. React batching updates kaise karta hai?

Answer:
✔ Multiple state updates ko ek single render me merge karta hai
✔ Performance improve

17. React concurrent mode aur useTransition

Answer:
✔ Concurrent mode – UI responsiveness improve
✔ useTransition – non-urgent updates defer karte hain

18. React portals kya hai aur kab use karte hain?

Answer:
✔ DOM tree ke outside render karne ke liye
✔ Modals, tooltips ke liye

ReactDOM.createPortal(<Modal />, document.getElementById('modal-root'))

19. React profiler ka use

Answer:
✔ Component render timings track
✔ Performance bottlenecks identify

20. Event delegation aur synthetic events

Answer:
✔ React synthetic events wrap native events
✔ Delegated at root for performance

➤ React + State Management Advanced
21. When to use Redux vs Context API

Answer:
✔ Redux – large app with complex state, middleware, devtools
✔ Context – simple global state, theme/auth

22. React memoization patterns

✔ React.memo, useMemo, useCallback
✔ Avoid unnecessary renders

23. React StrictMode purpose

✔ Highlight unsafe lifecycle methods, deprecated APIs
✔ Development only, double rendering helps detect issues

24. React hydration in SSR context

✔ Server-rendered HTML attach karna client React tree ke saath
✔ Prevent UI mismatch

25. Error boundaries limitations

✔ Only class components
✔ Async errors, event handler errors capture nahi karte

26. React lazy loading images or components

✔ React.lazy() aur IntersectionObserver for images

27. Optimizing large forms

✔ Controlled components optimized with useReducer
✔ Validation debounced
✔ Avoid unnecessary re-renders

28. React strict typing with TypeScript

✔ Props, state, context types define
✔ Prevent runtime errors

29. Reconciliation with fragments

✔ <></> avoid extra DOM nodes
✔ Key props still required for lists

30. React Suspense for data fetching (experimental)

✔ Future React features for async data
✔ Integration with concurrent mode


31. React me state batching kaise kaam karta hai?

Answer:
✔ React automatically multiple state updates ko ek hi render me batch karta hai
✔ Performance improve aur unnecessary renders avoid hote hain

32. React me lazy state initialization

✔ useState(() => expensiveComputation())
✔ Initial state calculation sirf first render me hoti hai

33. React me event pooling kya hota hai?

✔ SyntheticEvent object reuse hota hai
✔ Async me event data lose ho sakta hai, event.persist() use karna padta hai

34. React me prop drilling ka solution

✔ Context API ya Redux use karke deep components ko props pass na karna

35. React me memoization aur re-render optimization

✔ React.memo component memoize karna
✔ useCallback function reference memoize
✔ useMemo expensive calculation cache

36. React me imperative handle via useImperativeHandle

✔ Parent ke liye child ke methods expose karna
✔ Mostly forwardRef ke saath use

const Child = forwardRef((props, ref) => {
  useImperativeHandle(ref, () => ({ alertMsg: () => alert('Hi') }));
});

37. React me state derived from props ka best practice

✔ Avoid copying props to state
✔ Use memoized values or effect hooks

38. React me concurrent mode aur startTransition

✔ Non-urgent updates defer karte hain
✔ UI smooth aur responsive banti hai

39. React me controlled vs uncontrolled forms

✔ Controlled – React state handle kare input
✔ Uncontrolled – DOM handle kare input, useRef se access

40. React me form validation optimization

✔ Debounce input validation
✔ useReducer for complex form state
✔ Yup + react-hook-form

41. React me server-side rendering (SSR) aur hydration

✔ SSR – initial HTML server generate
✔ Hydration – React attach DOM pe client side
✔ Prevent mismatch issues

42. React me portals ka use case

✔ Modals, tooltips, dropdowns
✔ DOM tree ke bahar render

43. React me error boundaries aur limitations

✔ Only class components
✔ Event handler errors catch nahi hote

44. React me suspense aur lazy loading images/components

✔ Lazy load components via React.lazy
✔ Suspense fallback UI dikhaye loading ke time

45. React me Profiler ka use

✔ Component render timing track
✔ Identify performance bottlenecks

46. React me useEffect cleanup

✔ Component unmount ya effect re-run hone pe cleanup
✔ Avoid memory leaks

useEffect(() => {
  const id = setInterval(doSomething, 1000);
  return () => clearInterval(id);
}, []);

47. React me forwardRef aur refs combination

✔ Parent se child DOM access
✔ Libraries like input focus, custom modals

48. React me suspense for data fetching (experimental)

✔ Async data fetch ke liye Suspense
✔ Concurrent mode ke saath integrate

49. React me state persistence across reloads

✔ LocalStorage / sessionStorage + useEffect
✔ Redux Persist for global state

50. React me dynamic imports aur code splitting

✔ React.lazy + Suspense
✔ Bundle size optimize, faster load

51. React me hydration mismatch kaise avoid kare

✔ Conditional rendering server/client
✔ Same initial state server/client

52. React me useTransition aur startTransition ka use case

✔ Large list updates ya slow operations defer karna
✔ User interaction responsive rahe

53. React me state co-location concept

✔ State sirf jaha required waha maintain
✔ Avoid global state unless needed

54. React me scroll position aur refs manage karna

✔ useRef + useEffect
✔ Custom hooks banakar reuse

55. React me SSR + CSR hybrid approach

✔ Some components server render, some client render
✔ Optimized performance aur SEO

56. React me lazy initialization of state

Answer:
✔ Expensive computation sirf first render pe run karte hain

const [value, setValue] = useState(() => expensiveComputation());

57. React me useLayoutEffect vs useEffect practical example

✔ useLayoutEffect DOM mutations aur synchronous updates ke liye
✔ useEffect async, non-blocking side effects ke liye

58. React me multiple useEffect hooks ka order

✔ Hooks top-to-bottom order me execute hote hain
✔ Cleanup functions bhi reverse order me call hote hain

59. React me state co-location concept

✔ State sirf jaha required waha maintain
✔ Avoid global state unless really needed

60. React me useReducer ka advanced use-case

✔ Complex state transitions aur nested updates
✔ Form handling, toggle operations, nested objects

61. React me event pooling aur persist()

✔ SyntheticEvent object reuse hota hai
✔ Async me data lose hota hai, event.persist() se prevent

62. React me controlled forms performance optimization

✔ Debounce input changes
✔ useReducer for complex forms
✔ Avoid unnecessary re-renders

63. React me useRef for previous state

✔ Previous value store aur access

const prevValue = useRef();
useEffect(() => { prevValue.current = value; }, [value]);

64. React me component memoization for lists

✔ React.memo + key props
✔ Avoid unnecessary re-renders on parent update

65. React me context + memoization

✔ Context value change triggers re-render
✔ useMemo for context value optimize

66. React me Suspense + lazy loading images/components

✔ Lazy load components
✔ Fallback loader display

67. React me forwardRef ka advanced use-case

✔ Parent child ke methods expose
✔ Custom input focus, scroll, animation

68. React me Profiler API ka real-world use

✔ Track render times
✔ Identify performance bottlenecks
✔ Optimize heavy lists or components

69. React me useTransition ka practical use-case

✔ Large list updates ya slow state updates defer karna
✔ UI responsive rahe

70. React me hydration mismatch problem

✔ Conditional rendering server/client mismatch
✔ Initial state same rakhna

71. React me SSR + CSR hybrid rendering

✔ Kuch components server render, kuch client render
✔ Optimize SEO + performance

72. React me dynamic imports aur code splitting

✔ React.lazy() + Suspense
✔ Optimize initial bundle size

73. React me event delegation

✔ Parent level synthetic event handle karna
✔ Performance optimize

74. React me error boundaries aur limitations

✔ Only class components
✔ Event handler, async errors capture nahi karte

75. React me custom hooks advanced examples

✔ Reusable logic – data fetching, form handling, scroll tracking
✔ Hooks start with use

76. React me list virtualization

✔ react-window / react-virtualized
✔ Large lists ke liye performance optimization

77. React me useMemo vs useCallback difference

✔ useMemo – value memoize
✔ useCallback – function reference memoize
✔ Both avoid unnecessary re-renders

78. React me server-side data fetching (experimental Suspense)

✔ Async components data fetch ke liye
✔ Integrate with concurrent mode

79. React me global state management options

✔ Context API
✔ Redux / Redux Toolkit
✔ Zustand, Recoil
✔ MobX

80. React me state persistence

✔ LocalStorage / SessionStorage
✔ Redux Persist for global state

81. React me useLayoutEffect ka advanced use-case

✔ DOM mutations ke liye synchronous updates
✔ Animation, measuring DOM element size

82. React me multiple refs ka use

✔ Multiple elements ke liye useRef array ya useRef object use
✔ Forms, dynamic lists, focus management

83. React me dynamic forms handling

✔ useReducer + dynamic fields
✔ Form validation with react-hook-form or Formik
✔ Performance optimization

84. React me state hoisting kya hai?

✔ State parent me move karna taaki multiple children share kar sake
✔ Avoid duplicate state

85. React me controlled component performance issues

✔ Large forms me input onChange triggers multiple re-renders
✔ Solution: useReducer, debouncing, memoization

86. React me lazy loading ke sath Suspense fallback optimization

✔ Conditional loader / shimmer placeholder
✔ Smooth UX

87. React me error handling in async components

✔ try/catch inside useEffect or async functions
✔ Use Error Boundaries for render errors

88. React me component composition vs inheritance

✔ Prefer composition (children props) over inheritance
✔ Reusable UI patterns

89. React me render props pattern ka use-case

✔ Reusable logic share
✔ Dynamic UI rendering

90. React me key prop ka importance in dynamic lists

✔ Identity maintain
✔ Efficient diffing algorithm
✔ Avoid re-rendering of unchanged items

91. React me batching updates ka advanced example

✔ Multiple state updates in single render
✔ Performance optimization

92. React me context + useMemo ka combo

✔ Avoid unnecessary re-renders when context value changes
✔ Memoize value object

93. React me conditional rendering performance

✔ Avoid heavy computation in JSX
✔ Precompute values or memoize

94. React me large lists me virtualization

✔ react-window / react-virtualized
✔ Render only visible items for performance

95. React me hydration mismatch fix

✔ Conditional rendering server/client same initial state
✔ Avoid layout shift

96. React me forwardRef + useImperativeHandle advanced example

✔ Expose child methods to parent
✔ Scroll, focus, or custom API

97. React me SSR + lazy loading combination

✔ Code splitting + SSR considerations
✔ Avoid hydration errors

98. React me concurrent mode real-world example

✔ Large lists or transitions
✔ useTransition for non-urgent state updates

99. React me Suspense + data fetching libraries (React Query / SWR)

✔ Async data management with caching
✔ Error handling + suspense fallback

100. React me optimized image loading

✔ react-lazyload, IntersectionObserver
✔ WebP / srcset for responsive images

101. React me global state management advanced patterns

✔ Redux Toolkit slices, middleware, async thunk
✔ Zustand / Recoil for simple global state
✔ Context for small apps

102. React me side effect cleanup patterns

✔ useEffect cleanup for intervals, subscriptions, WebSocket
✔ Avoid memory leaks

103. React me testing advanced patterns

✔ React Testing Library
✔ Jest mock functions
✔ Async component testing, suspense testing

104. React me performance profiling

✔ React DevTools Profiler
✔ Identify heavy components and optimize with memoization

105. Next.js me SSR (Server Side Rendering) aur CSR (Client Side Rendering) ka difference

Answer:
✔ SSR – server pe render hota hai har request me, SEO friendly, slower initial render
✔ CSR – client browser me render hota hai, faster navigation but SEO dependent

106. Next.js me SSG (Static Site Generation) kab use karte hain?

Answer:
✔ Static content ke liye jo rarely change hota hai
✔ getStaticProps() ke sath pre-render pages build time pe

107. ISR (Incremental Static Regeneration) kya hai?

Answer:
✔ Static page periodically regenerate hota hai without redeploy
✔ revalidate option ke sath

export async function getStaticProps() {
  return { props: { data }, revalidate: 10 } // every 10 sec
}

108. Next.js me dynamic routing kaise implement karte hain?

✔ [param].js files in /pages
✔ getStaticPaths + getStaticProps for dynamic SSG
✔ useRouter client side access

109. Next.js me API routes kya hai aur kab use karte hain?

✔ /pages/api folder ke andar route define
✔ Backend functionality serve
✔ SSR/CSR dono ke liye useful

110. Next.js me middleware ka use-case

✔ Request/response intercept
✔ Auth check, redirects, headers injection

111. Next.js me getServerSideProps vs getStaticProps vs getInitialProps difference

✔ getServerSideProps – SSR
✔ getStaticProps – SSG
✔ getInitialProps – older method, both SSR/CSR, recommended getServerSideProps

112. Next.js me Image Optimization

✔ next/image component use
✔ Automatic lazy loading, responsive images, WebP support

113. Next.js me prefetching links

✔ next/link ke sath prefetch automatically
✔ Faster client navigation

114. Next.js me API route error handling

✔ Try/catch
✔ Status code return
✔ JSON error message

115. Next.js me authentication strategies

✔ JWT auth via cookies
✔ NextAuth.js for OAuth providers
✔ SSR protected pages

116. Next.js me environment variables

✔ .env.local, .env.production
✔ NEXT_PUBLIC_ prefix for client access
✔ Avoid sensitive info client side

117. Next.js me custom Document aur custom App

✔ _document.js – HTML structure, lang, meta tags
✔ _app.js – global CSS, context providers, layout

118. Next.js me Incremental Static Regeneration vs Client-side fetching

✔ ISR – pre-rendered + periodic update
✔ Client fetch – run-time fetch, dynamic content

119. Next.js me routing optimization

✔ Shallow routing for state update without full page reload
✔ Dynamic imports with next/dynamic for code splitting

120. Next.js me getStaticPaths fallback option

✔ fallback: true | false | blocking
✔ Determines behavior of paths not generated at build time

121. Next.js me Server Components vs Client Components (React 18)

✔ Server Components – heavy data fetch, reduce JS bundle
✔ Client Components – interactivity needed

122. Next.js me image domain whitelist

✔ External image domains allow karne ke liye next.config.js

images: { domains: ['example.com'] }

123. Next.js me API route middleware for authentication

✔ Protect API routes
✔ Token validation before route handler

124. Next.js me build performance optimization

✔ Code splitting, dynamic imports
✔ Image optimization
✔ Tree-shaking and caching

125. Next.js me Link prefetching control

✔ prefetch={false} to avoid unnecessary prefetch
✔ Improve network performance

126. Next.js me SWR library use-case

✔ Client-side data fetching
✔ Caching, revalidation, optimistic updates

127. Next.js me ISR vs on-demand revalidation

✔ ISR – periodic rebuild automatically
✔ On-demand – trigger rebuild via API call

128. Next.js me Head component ka use

✔ next/head SEO friendly meta tags, title, og tags

129. Next.js me middleware edge functions

✔ Run on edge network
✔ Low-latency auth, redirects  