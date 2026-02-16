 # 🧘‍♀️ YogaFlow: Pose Exploration & Education Platform

YogaFlow is a high-performance React application designed to help practitioners discover and learn yoga poses. It transforms raw category-based data into a seamless, paginated experience with detailed deep-dives for every pose.

🚀 **Live Link:** [https://yoga-blog-platform.vercel.app/](https://yoga-blog-platform.vercel.app/)

## 🛠️ Tech Stack

- **Frontend:** React.js (Vite)
- **Styling:** Tailwind CSS & DaisyUI
- **Data Fetching:** Axios
- **Hosting:** Vercel (CI/CD enabled)
- **Data Source:** [Alex Cumplido Yoga API](https://github.com/alexcumplido/yoga-api)

## ✨ Engineering Highlights

### 1. Data Normalization & Transformation
The source API delivers poses nested within categories. To enable a global search and global pagination, I implemented a transformation layer during the `fetch` cycle:
- **Flattening:** Used `flatMap` to merge category-specific arrays into a unified library.
- **Unique Identity:** Since IDs could overlap across categories, I injected a unique `id` based on the array index to ensure 100% accurate state tracking in the "Read View."

### 2. Custom Pagination Logic
To optimize performance and avoid "information overload," I built a custom pagination system:
- **Calculation:** Dynamically determines `totalPages` based on data length.
- **Navigation:** Implemented boundary-safe "Next" and "Previous" controls.
- **Slice Logic:** Uses `startIndx` and `endIndx` to render only 6 cards at a time, keeping the DOM light.

### 3. State-Driven View Switching
Instead of complex routing for a single-page app, I used a "Switch" pattern:
- **Listing View:** Displays the paginated grid.
- **Detail View:** Renders the `ReviewCard` component with full pose benefits and descriptions.
- **Lifting State:** Passed setter functions to children to allow the "Go Back" functionality while preserving the user's current page position.



## 📸 Preview

- **Grid View:** <img width="1451" height="871" alt="Screenshot 2026-02-16 161645" src="https://github.com/user-attachments/assets/543fe158-c2cc-411d-9a84-8955c811de5a" />
  <img width="925" height="867" alt="Screenshot 2026-02-16 161655" src="https://github.com/user-attachments/assets/d14244ce-bfbe-4b8f-a138-34b1e711978c" />


## 🚀 Installation & Setup

1. **Clone the project:**
   git clone [https://github.com/YOUR_USERNAME/yoga-blog-platform.git](https://github.com/Anshikatipathi649/yoga-blog-platform.git)
2. Install dependencies:
npm install
3. Run in development mode:
npm run dev
   
