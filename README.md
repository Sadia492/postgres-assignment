## ১. PostgreSQL কি?

PostgreSQL হলো একটি শক্তিশালী ওপেন সোর্স অব্জেক্ট-রিলেশনাল ডেটাবেজ সিস্টেম, যা ডেটা নিরাপদ সংরক্ষণ ও ব্যবস্থাপনা করে।

PostgreSQL এর বৈশিষ্ট্য:

- এটি ACID-compliant, অর্থাৎ ডেটা সঠিকভাবে সংরক্ষণ হয়

- এটি object-relational database হিসেবে inheritance, custom types ও functions সাপোর্ট করে

- বড় প্রজেক্ট ও সিস্টেমে ব্যবহারের জন্য খুবই স্কেলেবল ও সিকিউর|

---

## ২. PostgreSQL-এ Schema এর কাজ কী?

Schema হলো ডেটাবেজের একটি সম্পূর্ণ ডিজাইন বা পরিকল্পনা। এটিকে ডেটাবেজের ব্লুপ্রিন্টকে ও বলা হয়ে থাকে। এটিতে টেবিল, ভিউ, ফাংশন ইত্যাদি সংগঠিত করা হয়।

#### ডেটাবেজ স্কিমা-এর প্রধান উদ্দেশ্য ও সুবিধা:

১. বস্তুগুলিকে সংগঠিত করা:

- স্কিমাগুলি ডাটাবেস অবজেক্টগুলিকে সুসংগঠিতভাবে রাখতে সাহায্য করে। উদাহরণস্বরূপ,বিভিন্ন অ্যাপ্লিকেশন বা বিভিন্ন বিভাগের জন্য পৃথক স্কিমা তৈরি (যেমন sale স্কিমা, hr স্কিমা, money স্কিমা)। এটি ডাটাবেসকে আরও পরিষ্কার এবং পরিচালনা করা সহজ করে তোলে।

২. নামকরণ স্থান তৈরি করা:

- স্কিমার সবচেয়ে গুরুত্বপূর্ণ উদ্দেশ্যগুলির মধ্যে একটি হল তার জন্য নেমস্পেস তৈরি করা। এর অর্থ হল একই নামের বস্তুগুলিকে বিভিন্ন স্কিমার মধ্যে সংরক্ষণ করা যেতে পারে।

৩. নিরাপত্তা ও অনুমতি ব্যবস্থাপনা:

- স্কিমা-ভিত্তিক অনুমতি ব্যবস্থাপনা সম্ভব। নির্দিষ্ট ব্যবহারকারী বা ভূমিকাগুলিকে একটি নির্দিষ্ট স্কিমার উপর বিভিন্ন অনুমতি (যেমন: SELECT, INSERT, UPDATE, DELETE) দেওয়া যেতে পারে।

৪. তৃতীয় পক্ষের অ্যাপ্লিকেশনগুলির সাথে সংঘাত এড়ানো:

- যখন তৃতীয় পক্ষের অ্যাপ্লিকেশন ব্যবহার করা হয়, তখন তাদের নিজস্ব ডাটাবেস অবজেক্ট থাকতে পারে। নিজস্ব অবজেক্ট এবং তৃতীয় পক্ষের অবজেক্টের মধ্যে নামের দ্বন্দ্ব এড়াতে পৃথক স্কিমা ব্যবহার করা যেতে পারে।

৫. ডেটাবেজ অবজেক্টের কাঠামোবদ্ধতা:

- এটি ডেভেলপারদের ডাটাবেস কাঠামো আরও যুক্তিসঙ্গতভাবে ডিজাইন করতে সাহায্য করে। বিশেষ করে যখন একটি ডাটাবেস খুব বড় হয় এবং এতে প্রচুর সংখ্যক টেবিল, ভিউ ইত্যাদি থাকে, তখন স্কিমা ছাড়া সেগুলি পরিচালনা করা কঠিন হয়ে পড়ে।

---

## ৩. Primary Key এবং Foreign Key এর সম্পর্কে ব্যাখ্যা কর?

Primary Key: এটি প্রতিটি রো-কে ইউনিকভাবে শনাক্ত করে। একটি টেবিলে একটি মাত্র Primary Key থাকতে পারে। এটি প্রতিটি রেকর্ডকে ইউনিক এবং নাল (NOT NULL) ছাড়া হতে বাধ্য করে।

Foreign Key: এটি একটি টেবিলের কলাম যা অন্য টেবিলের Primary Key-কে রেফারেন্স করে, ফলে দুটি টেবিলের মধ্যে সম্পর্ক তৈরি হয়। এটি referential integrity বজায় রাখে।

---

## ৪. VARCHAR ও CHAR-এর মধ্যে পার্থক্য কী?

ডেটাবেজে অক্ষর বা স্ট্রিং ডেটা সংরক্ষণের জন্য VARCHAR এবং CHAR উভয়ই বহুল ব্যবহৃত ডেটা টাইপ। তবে তাদের মধ্যে কিছু মৌলিক পার্থক্য রয়েছে।

#### ১. দৈর্ঘ্য (Length)

- CHAR: এটি একটি স্থির দৈর্ঘ্যের ডেটা টাইপ। যখন CHAR(N) কলাম সংজ্ঞায়িত করা হয়, তখন এটি সর্বদা N অক্ষরের জন্য স্থান সংরক্ষণ করে। এমনকি যদি এর চেয়ে ছোট একটি স্ট্রিং সংরক্ষণ করা হয়, তবে ডেটাবেজ স্বয়ংক্রিয়ভাবে অবশিষ্ট স্থানগুলো ফাঁকা space দিয়ে পূরণ করে দেয়।

- VARCHAR: এটি একটি পরিবর্তনশীল দৈর্ঘ্যের ডেটা টাইপ। আপনি যখন VARCHAR(N) কলাম সংজ্ঞায়িত করেন, তখন N অক্ষরের সর্বোচ্চ দৈর্ঘ্য নির্দেশ করে। এটি কেবলমাত্র ব্যবহৃত অক্ষরের জন্য স্থান সংরক্ষণ করে, সাথে স্ট্রিংটির দৈর্ঘ্য তথ্য সংরক্ষণের জন্য অতিরিক্ত কিছু বাইট (সাধারণত 1 বা 2 বাইট) ব্যবহার করে।

#### ২. পারফরম্যান্স

- CHAR: যেহেতু CHAR ডেটা টাইপ স্থির দৈর্ঘ্যের, তাই ডেটাবেজ সিস্টেমে ডেটা প্রক্রিয়াকরণ কিছুটা দ্রুত হতে পারে। কারণ ডেটাবেজকে প্রতিটি স্ট্রিংয়ের দৈর্ঘ্য আলাদাভাবে পরীক্ষা করতে হয় না।

- VARCHAR: VARCHAR ডেটা টাইপ ব্যবহারের ক্ষেত্রে ডেটাবেজকে স্ট্রিংয়ের দৈর্ঘ্য ট্র্যাক করতে হয় এবং সেই অনুযায়ী স্থান বরাদ্দ করতে হয়, যা CHAR এর তুলনায় সামান্য কম দ্রুত হতে পারে। তবে, আধুনিক ডেটাবেজ সিস্টেমে এই পারফরম্যান্সের পার্থক্য সাধারণত খুব কম হয় এবং বেশিরভাগ অ্যাপ্লিকেশনের জন্য নগণ্য।

#### ৩. ব্যবহার ক্ষেত্র

- CHAR: এটি সেইসব ডেটার জন্য উপযুক্ত যেখানে স্ট্রিংগুলির দৈর্ঘ্য সবসময় একই থাকে।

  - উদাহরণ: পোস্টাল কোড, দেশের কোড (যেমন: "USA", "IND"), লিঙ্গ (Male/Female)।

- VARCHAR: এটি সেইসব ডেটার জন্য উপযুক্ত যেখানে স্ট্রিংগুলির দৈর্ঘ্য ভিন্ন হতে পারে।
  - উদাহরণ: নাম, ঠিকানা, ইমেল ঠিকানা, মন্তব্য বা বিবরণ।

---

## ৫. SELECT statement-এ WHERE clause ব্যবহার করার উদ্দেশ্য কি?

SQL SELECT স্টেটমেন্টে WHERE ক্লজ একটি অত্যন্ত গুরুত্বপূর্ণ অংশ। এর প্রধান উদ্দেশ্য হলো একটি টেবিল থেকে ডেটা পুনরুদ্ধার করার সময় নির্দিষ্ট শর্তের উপর ভিত্তি করে সারিগুলিকে ফিল্টার করা।

#### WHERE ক্লজের প্রধান উদ্দেশ্য:

১. সারি ফিল্টারিং:

- এটি SELECT ক্যোয়ারীর মাধ্যমে ডেটাবেজ থেকে ডেটা আনার সময় নির্দিষ্ট শর্তাবলী পূরণ করে এমন সারিগুলিকে বেছে নিতে ব্যবহৃত হয়।

২. শর্তাবলী প্রয়োগ করা:

- WHERE ক্লজে এক বা একাধিক শর্ত প্রয়োগ করা যায়। এই শর্তগুলি লজিক্যাল অপারেটর (যেমন AND, OR, NOT) এবং তুলনা অপারেটর (যেমন =, >, <, >=, <=, <>, !=) ব্যবহার করে তৈরি করা হয়।

৩. প্রাসঙ্গিক ডেটা পুনরুদ্ধার:

- অপ্রয়োজনীয় ডেটা লোড করা বা প্রদর্শন করা এড়ানো যায়। এটি ডেটাবেজের পারফরম্যান্স উন্নত করতেও সাহায্য করে, কারণ কম ডেটা প্রক্রিয়া করা হয়।

---

#### WHERE ক্লজের সিনট্যাক্স:

SELECT স্টেটমেন্টে WHERE ক্লজের মৌলিক সিনট্যাক্স হলো:

```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```
