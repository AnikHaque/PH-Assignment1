# What is the use of the keyof keyword in TypeScript? Provide an example.

= TypeScript-এ keyof ব্যবহার করা হয় কোনো অবজেক্ট টাইপের সমস্ত key-এর ইউনিয়ন বের করতে। সহজভাবে বললে—যে অবজেক্টের যেসব প্রপার্টি আছে, keyof সেগুলোর নামকে টাইপ হিসেবে রিটার্ন করে। এতে টাইপ সেফটি বাড়ে এবং ভুল key ব্যবহারের সম্ভাবনা কমে যায়।

#### Example: 

type User = {
  name: string;
  age: number;
  email: string;
};
type UserKeys = keyof User;

উপরের কোডে keyof User লিখলেই আমরা User টাইপের সব প্রপার্টির নাম পেয়ে যাই—যা অনেক জায়গায় কাজে লাগে, বিশেষ করে জেনেরিক ফাংশন বা স্ট্রং টাইপড ইউটিলিটি বানানোর সময়।
