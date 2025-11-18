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
