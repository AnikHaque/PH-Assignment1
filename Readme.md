<h1> What is <code>keyof</code> in TypeScript?</h1>

<p>
  <code>keyof</code> হলো TypeScript-এর একটি ছোট কিন্তু দরকারী কীওয়ার্ড। 
  এটা কোনো অবজেক্ট টাইপের সবগুলো প্রপার্টির নাম বের করে 
  সেগুলোকে একটি ইউনিয়ন টাইপ হিসেবে রিটার্ন করে। 
  এতে কোড আরও সেফ থাকে এবং ভুল key ব্যবহার করার সুযোগ কমে যায়।
</p>

<hr />

<h2> Basic Example</h2>

<pre>
<code>
type User = {
  name: string;
  age: number;
  email: string;
};

type UserKeys = keyof User;
</code>
</pre>

<p>
  উপরের উদাহরণে <code>keyof User</code> লেখার মানে হলো User টাইপের সব প্রপার্টির নামকে 
  একসাথে টাইপ হিসেবে পাওয়া—যা হলো <code>"name" | "age" | "email"</code>.
</p>



<h1> Union & Intersection Types (TypeScript)</h1>

<p>
  TypeScript-এ আমরা মাঝে মাঝে এমন টাইপ চাই যেখানে 
  <strong>একটা ভ্যালু একাধিক টাইপের যেকোনো একটা হতে পারে</strong> — একে বলে <em>Union Type</em>।  
  আবার কখনো চাই একটা ভ্যালুতে <strong>দুই বা তার বেশি টাইপের সব প্রপার্টি একসাথে থাকা</strong> — একে বলে <em>Intersection Type</em>।  
  নিচে দুটোরই ছোট ও সহজ উদাহরণ দেওয়া হলো।
</p>

<hr />

<h2> Union Type Example</h2>

<p>
  Union টাইপ মানে: একটি ভ্যালু একাধিক টাইপের যেকোনো একটিতে হতে পারবে।
</p>

<pre>
<code>
let id: number | string;

id = 101;      // valid
id = "A102";   // valid
// id = true;  //  invalid
</code>
</pre>

<p>
  উপরের কোডে <code>id</code> কেবলমাত্র <code>number</code> অথবা <code>string</code> হতে পারবে।
</p>

<hr />

<h2> Intersection Type Example</h2>

<p>
  Intersection টাইপ মানে: দুইটা টাইপকে একসাথে যোগ করে এমন একটা টাইপ বানানো, 
  যেখানে সব প্রপার্টিই থাকতে হবে।
</p>

<pre>
<code>
type Person = {
  name: string;
};

type Employee = {
  employeeId: number;
};

type Staff = Person & Employee;

const member: Staff = {
  name: "Karim",
  employeeId: 1201
};
</code>
</pre>

<p>
  এখানে <code>Staff</code> টাইপে <strong>Person</strong> এবং <strong>Employee</strong> — 
  দুটো টাইপের সব প্রপার্টিই বাধ্যতামূলক।
</p>

<hr />
