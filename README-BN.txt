RAHAMAN ONLINE — Website + eBook Store
=====================================

এই ZIP-এ কী আছে
- আগের Rahaman Online Digital Services section
- নতুন responsive eBook Store (দুই কলামের mobile layout)
- প্রথম AI eBook-এর cover এবং PDF
- Razorpay order creation + payment signature verification + captured payment check
- 15 মিনিট মেয়াদি signed download link

গুরুত্বপূর্ণ
এই Project-এ Razorpay LIVE payment key দেওয়া নেই। নিজের Razorpay account থেকে API keys নিয়ে Netlify-তে Environment Variables সেট না করা পর্যন্ত Buy Now-তে payment কাজ করবে না। কখনো Secret Key কাউকে দেবেন না বা HTML/JavaScript-এ বসাবেন না।

Android থেকে Netlify-তে publish (GitHub পদ্ধতি — Functions-এর জন্য দরকার)
1. ZIP extract করুন।
2. GitHub app বা Chrome-এ github.com খুলে Sign in করুন।
3. New repository তৈরি করুন: rahaman-online-ebook-store (Public বা Private)।
4. এই ZIP-এর ভেতরের সব ফাইল ও folder repository-র root-এ upload করুন। ZIP ফাইলটিকে নিজে upload করবেন না; ZIP extract করে index.html, netlify.toml, package.json, assets এবং netlify folder upload করবেন।
5. netlify.com-এ Sign in করুন → Add new project → Import an existing project → GitHub → repository নির্বাচন করুন।
6. Build command ফাঁকা রাখুন; Publish directory হিসেবে . (dot) এবং Functions directory netlify/functions দিন। netlify.toml থেকেও এই settings পড়ার কথা। Deploy করুন।
7. Netlify Site configuration → Environment variables-এ এই তিনটি variable যোগ করুন:
   RAZORPAY_KEY_ID = Razorpay Dashboard-এর API Key ID
   RAZORPAY_KEY_SECRET = Razorpay Dashboard-এর API Key Secret
   DOWNLOAD_TOKEN_SECRET = নিজের তৈরি লম্বা random secret (কমপক্ষে 32 bytes)
8. Environment variables যোগ করার পর নতুন deploy trigger করুন।
9. Razorpay Dashboard-এ Website details, business details, bank/KYC এবং প্রয়োজনীয় activation সম্পূর্ণ করে Test Mode-এ পরীক্ষা করুন। Test সফল হলে Live API keys বসিয়ে আবার deploy করুন।

Razorpay setup
- Razorpay Dashboard → Account & Settings / API Keys → Test keys generate করুন। Menu নাম Dashboard-এ বদলাতে পারে।
- প্রথমে Test Mode-এ checkout, payment verification এবং PDF download পরীক্ষা করুন।
- Live keys কেবল account activation/approval-এর পরে ব্যবহার করুন।
- Payment captured না হলে server download অনুমতি দেবে না।

গুরুত্বপূর্ণ সীমাবদ্ধতা ও পরবর্তী কাজ
- এই প্রথম সংস্করণে AI eBook (₹69) কেনা চালু করার code আছে। অন্য তিনটি বই Coming Soon।
- Refund Policy, Terms, Privacy Policy, business/GST তথ্য নিজের বাস্তব ব্যবসার নিয়ম অনুযায়ী পূরণ করতে হবে।
- Digital PDF কপি হওয়া পুরোপুরি ঠেকানো যায় না; signed link কেবল অননুমোদিত public access কমায়।
- Download link 15 মিনিট পরে expire করে; customer link হারালে support-এর মাধ্যমে order যাচাই করে নতুন link দেওয়ার ব্যবস্থা পরে যোগ করা যেতে পারে।
- Netlify Function deploy না করে শুধু Netlify Drop-এ static upload করলে Razorpay server functions চলবে না। GitHub-connected Netlify deploy ব্যবহার করুন।

Local preview
index.html browser-এ খুললে design দেখা যাবে, কিন্তু payment function local server ছাড়া চলবে না। Live payment-এর আগে Netlify deploy-এ Test Mode দিয়ে পরীক্ষা করুন।

Support details in site
Phone/WhatsApp: 9907593998 / 7029076172
Email: farhatyamin012@gmail.com
Location: Khalaigram Station Para, Dhupguri, West Bengal, India
