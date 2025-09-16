1. TypeScript me React props ka type kaise define karte hain?

Answer:
✔ interface ya type use karte hain

interface ButtonProps {
  label: string;
  onClick: () => void;
}
const Button: React.FC<ButtonProps> = ({ label, onClick }) => <button onClick={onClick}>{label}</button>;

2. React state me TypeScript kaise use kare?

✔ useState generic type ke sath

const [count, setCount] = useState<number>(0);

3. TypeScript me default props handle kaise kare?

✔ Optional props + default values

interface Props { name?: string }
const Comp: React.FC<Props> = ({ name = "Ashish" }) => <div>{name}</div>;

4. TypeScript me useRef ka proper type

✔ DOM element reference

const inputRef = useRef<HTMLInputElement>(null);

5. TypeScript me React events ka type

✔ React.ChangeEvent<HTMLInputElement>
✔ React.MouseEvent<HTMLButtonElement>

6. TypeScript me component generic props

✔ Reusable generic components

interface ListProps<T> { items: T[] }
function List<T>({ items }: ListProps<T>) { return <>{items.map(i=><div>{i}</div>)}</>; }

7. TypeScript me union types aur conditional rendering

✔ Union props handle

type ButtonType = "primary" | "secondary";
interface Props { type: ButtonType }

8. TypeScript me context ka type

✔ CreateContext me generic type

interface ThemeContextType { theme: string; toggle: () => void }
const ThemeContext = React.createContext<ThemeContextType | null>(null);

9. TypeScript me HOC typing

✔ Component ko wrap karte waqt props merge

function withAuth<T>(Component: React.ComponentType<T>) {
  return (props: T) => <Component {...props} />;
}

10. TypeScript me forwardRef typing

✔ Child methods parent ko expose

interface ChildRef { focus: () => void }
const Child = React.forwardRef<ChildRef>((props, ref) => { React.useImperativeHandle(ref, () => ({ focus: () => {} })); return <input />; });

11. TypeScript me useReducer typing

✔ State & action type define

type State = { count: number }
type Action = { type: "increment" | "decrement" }
const [state, dispatch] = useReducer((state: State, action: Action) => {...}, { count: 0 });

12. TypeScript me React.memo typing

✔ Props type preserve karna

const MemoComp = React.memo<ButtonProps>(Button);

13. TypeScript me default generic props

✔ Generic component me default type

function List<T = string>({ items }: { items: T[] }) {}

14. TypeScript me event delegation aur synthetic events typing

✔ Correct event type define for performance & safety

15. TypeScript me lazy loaded components typing

✔ React.LazyExoticComponent type

const LazyComp: React.LazyExoticComponent<React.FC<Props>> = React.lazy(() => import('./Comp'));

16. TypeScript me useImperativeHandle ka use-case

✔ Parent ke liye child ke functions expose

17. TypeScript me optional chaining aur null checks in props

✔ prop?.field safe access
✔ Avoid runtime error

18. TypeScript me union + discriminated types for conditional rendering

✔ Complex props handling

type Props = { type: "A", a: string } | { type: "B", b: number }

19. TypeScript me React context + useReducer global state

✔ Strongly typed state management
✔ Avoid errors in dispatch actions

20. TypeScript me Suspense + lazy components typing

✔ Fallback handling
✔ Correct component type specify

21. TypeScript me optional props aur default values

✔ Props optional ho sakte hain aur default assign kar sakte hain

interface Props { name?: string }
const Comp: React.FC<Props> = ({ name = "Ashish" }) => <div>{name}</div>;

22. TypeScript me event handler typing for forms

✔ Input change: React.ChangeEvent<HTMLInputElement>
✔ Button click: React.MouseEvent<HTMLButtonElement>

23. TypeScript me union types for props

✔ Multiple possible values ke liye

type ButtonType = "primary" | "secondary";
interface Props { type: ButtonType }

24. TypeScript me forwardRef aur useImperativeHandle typing

✔ Parent ke liye child functions expose karte hain

interface ChildRef { focus: () => void }
const Child = React.forwardRef<ChildRef>((props, ref) => {
  React.useImperativeHandle(ref, () => ({ focus: () => {} }));
  return <input />;
});

25. TypeScript me generic components typing

✔ Reusable components ke liye generic types

interface ListProps<T> { items: T[] }
function List<T>({ items }: ListProps<T>) { return <>{items.map(i => <div>{i}</div>)}</>; }

26. TypeScript me useReducer typing

✔ Complex state management ke liye

type State = { count: number }
type Action = { type: "increment" | "decrement" }
const [state, dispatch] = useReducer((state: State, action: Action) => {...}, { count: 0 });

27. TypeScript me context typing

✔ Strongly typed global state

interface ThemeContextType { theme: string; toggle: () => void }
const ThemeContext = React.createContext<ThemeContextType | null>(null);

28. TypeScript me React.memo typing

✔ Props ke sath memoize component

const MemoComp = React.memo<ButtonProps>(Button);

29. TypeScript me dynamic imports typing

✔ Lazy load components

const LazyComp: React.LazyExoticComponent<React.FC<Props>> = React.lazy(() => import('./Comp'));

30. TypeScript me optional chaining aur null checks

✔ Safe prop access

console.log(user?.name ?? "Guest");

31. TypeScript me discriminated union types for conditional rendering

✔ Complex conditional props handle

type Props = { type: "A", a: string } | { type: "B", b: number }

32. TypeScript me state co-location aur type safety

✔ State sirf jaha required waha maintain, type check strong

33. TypeScript me Suspense + lazy loading typing

✔ Fallback aur component type safe
✔ Optimize large bundle load

34. TypeScript me refs with generics

✔ useRef<HTMLDivElement>(null)
✔ Multiple refs ke liye object ya array use

35. TypeScript me custom hooks typing

✔ Generic reusable hooks

function useFetch<T>(url: string): { data: T | null, loading: boolean } { ... }

36. TypeScript me HOC typing

✔ Higher-order components ke liye generic props merge

function withAuth<T>(Component: React.ComponentType<T>) {
  return (props: T) => <Component {...props} />;
}

37. TypeScript me optional props + default state pattern

✔ State or props ke liye default fallback
✔ Avoid undefined errors

38. TypeScript me union + intersection types use-case

✔ Props ke liye multiple types combine

type A = { x: string }; type B = { y: number }; type C = A & B;

39. TypeScript me JSX intrinsic element typing

✔ Custom elements aur props type check
✔ JSX.IntrinsicElements['input']

40. TypeScript me functional component type options

✔ React.FC<Props> or explicit return type
✔ Props type safety

41. Next.js + TypeScript me getStaticProps ka type kaise define kare?

Answer:
✔ GetStaticProps generic use karte hain for type-safe props

import { GetStaticProps } from 'next';
interface Props { posts: string[] }
export const getStaticProps: GetStaticProps<Props> = async () => {
  const posts = await fetchPosts();
  return { props: { posts } };
};

42. Next.js + TypeScript me getServerSideProps ka type

✔ GetServerSideProps<Props>
✔ Server-side rendered pages ke liye type-safe props

43. Next.js + TypeScript me getStaticPaths typing

✔ Dynamic routes ke liye

export const getStaticPaths: GetStaticPaths = async () => {
  return { paths: [{ params: { id: '1' } }], fallback: false };
};

44. Next.js + TypeScript me API routes typing

✔ Request/Response objects ka type

import type { NextApiRequest, NextApiResponse } from 'next';
export default function handler(req: NextApiRequest, res: NextApiResponse) {
  res.status(200).json({ message: 'OK' });
}

45. Next.js + TypeScript me dynamic routing typing

✔ useRouter generic params ke sath

import { useRouter } from 'next/router';
const router = useRouter();
const { id } = router.query as { id: string };

46. Next.js + TypeScript me middleware typing

✔ Edge functions aur auth checks
✔ Request/response objects type-safe

47. Next.js + TypeScript me ISR typing

✔ revalidate ke sath props type-safe

48. Next.js + TypeScript me Image component typing

✔ next/image props type-safe
✔ width, height, src, alt mandatory types

49. Next.js + TypeScript me Link prefetch typing

✔ next/link ke sath href type-safe

50. Next.js + TypeScript me Auth typing

✔ JWT token payload type-safe
✔ NextAuth.js session object type-safe

51. Next.js + TypeScript me environment variables typing

✔ .env variables ke liye process.env.VARIABLE as string

52. Next.js + TypeScript me custom App & Document typing

✔ _app.tsx aur _document.tsx ke liye AppProps & DocumentProps

53. Next.js + TypeScript me dynamic imports typing

✔ next/dynamic ke sath fallback aur component type-safe

import dynamic from 'next/dynamic';
const DynamicComp = dynamic<CompProps>(() => import('./Comp'), { ssr: false });

54. Next.js + TypeScript me getInitialProps typing

✔ Legacy pages ke liye type-safe props

55. Next.js + TypeScript me error handling in API routes

✔ Try/catch + NextApiResponse type

56. Next.js + TypeScript me middleware + edge auth example

✔ JWT validation, redirect unauthorized
✔ Strongly typed request & response

57. Next.js + TypeScript me conditional SSR & CSR typing

✔ Some components server-rendered, some client-rendered
✔ Props aur state type-safe

58. Next.js + TypeScript me SWR library typing

✔ Client-side fetch ke liye generic type

const { data, error } = useSWR<User[]>('/api/users', fetcher);

59. Next.js + TypeScript me shallow routing typing

✔ State update without full page reload
✔ useRouter type-safe

60. Next.js + TypeScript me ISR on-demand revalidation typing

✔ API call trigger, rebuild page
✔ Type-safe API route

61. Next.js + TypeScript me getServerSideProps me query params ka type

✔ Type-safe access router.query ya context.params

export const getServerSideProps: GetServerSideProps<{ id: string }> = async (context) => {
  const { id } = context.params as { id: string };
  return { props: { id } };
};

62. Next.js + TypeScript me dynamic nested routes typing

✔ [category]/[id].tsx
✔ context.params as { category: string; id: string }

63. Next.js + TypeScript me API route with typed request body

✔ POST request ke liye type-safe body

interface Body { name: string; email: string }
export default function handler(req: NextApiRequest, res: NextApiResponse) {
  const body: Body = req.body;
}

64. Next.js + TypeScript me optional query params

✔ Type-safe optional params

const { page } = context.query as { page?: string };

65. Next.js + TypeScript me middleware + typed NextRequest

✔ Edge auth, redirects, headers injection

import { NextRequest, NextResponse } from 'next/server';
export function middleware(req: NextRequest) { ... }

66. Next.js + TypeScript me ISR revalidation ke sath props typing

✔ revalidate: number aur type-safe props

67. Next.js + TypeScript me API route response typing

✔ NextApiResponse<{ message: string }>

68. Next.js + TypeScript me middleware + JWT validation

✔ Token decode aur type-safe payload

interface Payload { userId: string }

69. Next.js + TypeScript me SWR fetcher generic typing

✔ Data type-safe fetch

const fetcher = async <T>(url: string): Promise<T> => { ... };
const { data } = useSWR<User[]>('/api/users', fetcher);

70. Next.js + TypeScript me conditional rendering ke liye discriminated types

✔ Props ke union types

type Props = { type: "A"; a: string } | { type: "B"; b: number };

71. Next.js + TypeScript me dynamic imports + fallback typing

✔ SSR false ke sath lazy components

const DynamicComp = dynamic<CompProps>(() => import('./Comp'), { ssr: false });

72. Next.js + TypeScript me shallow routing type-safe

✔ router.push('/page', undefined, { shallow: true })
✔ Query params type-safe

73. Next.js + TypeScript me getStaticPaths fallback: blocking

✔ Fallback paths generate aur page SSR mode me
✔ Params type-safe

74. Next.js + TypeScript me global state + context + useReducer typing

✔ Strongly typed state + dispatch
✔ Avoid runtime errors

75. Next.js + TypeScript me API route error handling advanced

✔ Status codes, typed error messages, try/catch

76. Next.js + TypeScript me auth protected page SSR

✔ JWT check in getServerSideProps
✔ Redirect unauthorized user

77. Next.js + TypeScript me optional chaining + nullish coalescing

✔ Safe props access

const username = user?.name ?? "Guest";

78. Next.js + TypeScript me Edge function typing example

✔ Low-latency auth, header injection, redirect
✔ NextRequest & NextResponse

79. Next.js + TypeScript me API route POST/PUT/DELETE typing

✔ Request body aur response type-safe

80. Next.js + TypeScript me performance optimization tips

✔ Dynamic imports, lazy loading, memoization
✔ SWR cache, ISR, on-demand revalidation

81. Next.js + TypeScript me getServerSideProps me cookies type-safe access

✔ context.req.cookies ke liye TypeScript interface

interface MyCookies { token?: string }
const cookies = context.req.cookies as MyCookies;

82. Next.js + TypeScript me API route query params typing

✔ req.query as { id: string; type?: string }
✔ POST/GET request differentiation

83. Next.js + TypeScript me optional chaining + fallback values

✔ Safe access aur default values

const name = user?.profile?.name ?? "Guest";

84. Next.js + TypeScript me typed dynamic route fallback

✔ [id].tsx ke liye getStaticPaths + getStaticProps type-safe

85. Next.js + TypeScript me incremental static regeneration + on-demand revalidation typing

✔ ISR revalidate number + optional secret key for on-demand rebuild

86. Next.js + TypeScript me API route POST body validation

✔ Type-safe request body
✔ Yup / Zod library ke sath validation aur type inference

87. Next.js + TypeScript me middleware edge function + typed headers

✔ Low-latency auth, redirect

import { NextRequest, NextResponse } from 'next/server';
const token = req.headers.get('authorization');

88. Next.js + TypeScript me dynamic import with suspense

✔ Lazy load component + fallback

const LazyComp = dynamic<CompProps>(() => import('./Comp'), { ssr: false });

89. Next.js + TypeScript me SWR use with typed fetcher

✔ Cache + type-safe data

const fetcher = async <T>(url: string): Promise<T> => { ... };
const { data } = useSWR<User[]>('/api/users', fetcher);

90. Next.js + TypeScript me shallow routing type-safe

✔ router.push('/page', undefined, { shallow: true })
✔ Query params aur state typing

91. Next.js + TypeScript me getStaticPaths fallback: true vs blocking

✔ true – fallback component render
✔ blocking – server render waits for data

92. Next.js + TypeScript me global state context + reducer typing

✔ Strongly typed state & dispatch
✔ Example: theme toggle, cart state

93. Next.js + TypeScript me API route advanced error handling

✔ Status code, error messages, type-safe response
✔ Try/catch aur custom error interface

94. Next.js + TypeScript me protected SSR page using JWT

✔ getServerSideProps me token decode
✔ Unauthorized redirect type-safe

95. Next.js + TypeScript me edge middleware for authentication

✔ JWT validation aur redirect
✔ NextRequest & NextResponse typing

96. Next.js + TypeScript me typed optional environment variables

✔ process.env.NEXT_PUBLIC_API_URL as string
✔ Client-side access ke liye NEXT_PUBLIC_ prefix

97. Next.js + TypeScript me API route PUT/DELETE typing

✔ Typed request body + typed response
✔ Strongly typed error handling

98. Next.js + TypeScript me dynamic routing + query params type-safe

✔ Optional params + fallback defaults
✔ Nested dynamic routes typing

99. Next.js + TypeScript me SSR + client side hydration mismatch handling

✔ Initial props + client state sync
✔ Conditional rendering + type-safe

100. Next.js + TypeScript me performance optimization

✔ Dynamic imports
✔ Memoization
✔ Lazy loading
✔ ISR + on-demand revalidation
✔ SWR caching