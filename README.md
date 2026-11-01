<div align="center">

# 📊 Sorting Visualization

**৮টি Sorting Algorithm — ধাপে ধাপে, লাইন ধরে ধরে, অ্যানিমেশনসহ**

![HTML](https://img.shields.io/badge/HTML-CSS-JavaScript-orange?style=flat-square)
![No Dependencies](https://img.shields.io/badge/dependencies-none-brightgreen?style=flat-square)
![Algorithms](https://img.shields.io/badge/algorithms-8-blue?style=flat-square)

</div>

একটি **single-file** (`index.html`) visualizer। কোনো library, build tool বা internet লাগে না — browser-এ ফাইলটা খুললেই চলে।
প্রতিটি ধাপে C code-এর **ঠিক কোন লাইনটা চলছে** সেটা highlight হয়, সাথে variable-এর মান (`i`, `j`, `m`...) আর বাংলায় ব্যাখ্যা দেখা যায়।

---

## ✨ Features

| Feature | বিবরণ |
|---|---|
| 🎞️ Animated bars | Swap হলে দুইটি bar বিপরীত দিকে সরে জায়গা বদলায় |
| 🌳 **Tree view** | Merge Sort, Quick Sort-এর recursion আর Heap Sort-এর heap tree আকারে দেখা যায় |
| 💡 Status banner | প্রতিটি ধাপে সহজ ভাষায় লেখা থাকে এখন কী হচ্ছে |
| 💻 Live code highlight | প্রতি ধাপে C code-এর চলমান লাইন নীল হয় |
| 🔢 Variable chips | `i = 2`, `j = 5`, `pivot = 6` — প্রতি ধাপে বর্তমান মান |
| ⏯️ Full control | Play / Pause / আগের ধাপ / পরের ধাপ / Reset / শেষ পর্যন্ত |
| 🐢🐇 Speed slider | ধীর থেকে দ্রুত, ৫ স্তর |
| ✍️ Custom array | ২–২০টি সংখ্যা (০–৯৯৯) দিয়ে নিজের array চালাও |
| 📱 Responsive | মোবাইলেও সুন্দরভাবে চলে |

---

## 🧮 Algorithms

প্রতিটি tab-এ উপরে একটি **"এখন কী হচ্ছে"** banner থাকে — এক লাইনে algorithm-এর মূল ধারণা, আর নিচে বর্তমান ধাপ (🔍 তুলনা, 🔁 Swap, 📌 Pivot, 🎉 শেষ)।

| Algorithm | অতিরিক্ত visualization |
|---|---|
| Bubble Sort | Bar animation + banner |
| Selection Sort | Bar animation + banner (বর্তমান minimum দেখায়) |
| Insertion Sort | Bar animation + banner (key দেখায়) |
| **Merge Sort** | 🌳 Recursion tree (Divide → Merge) + bar |
| **Quick Sort** | 🌳 Recursion tree (pivot-এর বাম / ডান অংশ) + bar |
| **Heap Sort** | 🌳 Array-টা binary heap tree হিসেবে + bar |
| Counting Sort | Bar animation + banner |
| Radix Sort | Bar animation + banner |

সবুজ মানে **sorted / নিজের চূড়ান্ত জায়গায় পৌঁছেছে**।

---

## 🌳 Merge Sort — Tree Visualization

> Quick Sort-এর tree-ও একই নিয়মে চলে (node = `quickSort(lo, hi)` call, 🟣 = pivot)। Heap Sort-এ array-র index `i`-এর child থাকে `2i+1` ও `2i+2`-এ।

Merge Sort ট্যাবে bar chart-এর উপরে একটি **recursion tree** দেখানো হয়:

- প্রতিটি `mergeSort(l, r)` call = একটি **node**, যেখানে ওই অংশের সংখ্যাগুলো থাকে।
- **Status banner:** tree-র উপরে একটি লাইনে লেখা থাকে এখন কী হচ্ছে — ✂️ Divide, 🔀 Merge, 🍃 একটি element, নাকি 🎉 শেষ।
- **Curve line:** parent-child সংযোগ বাঁকানো রেখায় দেখানো হয়; চলমান পথ 🟡 হলুদ, শেষ হওয়া পথ 🟢 সবুজ।
- **Divide:** node দুই ভাগ হলে নিচে দুইটি child node আসে (🔵 বাম অংশ, 🟣 ডান অংশ)।
- **Merge:** যে node merge হচ্ছে তার চারপাশে 🟡 হলুদ border থাকে, আর যে দুই element compare হচ্ছে সেগুলো highlight হয়।
- **Swap:** merge-এর সময় যে element জায়গা বদলায়, tree-র ভেতরেই সেটা পুরনো ঘর থেকে নতুন ঘরে সরে যায় (একটি element উপর দিয়ে পার হয়, bar chart-এর মতো)।
- **Done:** merge শেষ হলে node 🟢 সবুজ হয় (sorted)। Leaf node (একটি element) শুরু থেকেই sorted।
- Tree আর bar chart **একসাথে, একই ধাপে** চলে।
- ২০টি element দিলে মোবাইলে tree আড়াআড়ি scroll করা যায়।

---

## 🚀 ব্যবহার

```bash
git clone https://github.com/sohan-parves/sorting-visualization.git
cd sorting-visualization
# index.html ফাইলটি browser-এ খোলো
```

1. উপরের tab থেকে algorithm বেছে নাও।
2. চাইলে **Array বেছে নাও** বক্সে নিজের সংখ্যা দিয়ে **Custom Array চালাও** চাপো (`7, 3, 8, 2, 6, 1`)।
3. **▶ Play** চাপো, অথবা **এক ধাপ এগোন →** দিয়ে নিজের গতিতে দেখো।

---

## 🗂️ Project Structure

```
sorting-visualization/
├── index.html   # পুরো app (HTML + CSS + JS)
└── README.md
```

## 🧠 কীভাবে কাজ করে

প্রতিটি algorithm আগে থেকেই একটি **step list** বানায়। প্রতিটি step একটি snapshot — array-এর অবস্থা, চলমান code লাইন, variable মান, highlight কোন কোন bar-এ। UI শুধু ওই snapshot দেখায়, তাই আগে-পরে যেকোনো ধাপে সহজে যাওয়া যায়। Merge Sort-এর snapshot-এ অতিরিক্ত করে প্রতিটি tree node-এর অবস্থাও (লুকানো / ভাগ হয়েছে / merge চলছে / sorted) রাখা হয়।

---

<div align="center">
শেখার জন্য বানানো ❤️ — Star দিতে ভুলো না ⭐
</div>
