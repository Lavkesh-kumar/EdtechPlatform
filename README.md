# StudyNotion

StudyNotion is a full-stack EdTech platform I built to make online learning more accessible and structured. The idea was to create a space where students can find quality courses, and instructors can manage and deliver their content without any friction. It covers everything from course browsing and enrollment to payments and progress tracking.

![StudyNotion Logo](https://res.cloudinary.com/dvpulu3cc/image/upload/v1702489710/Screenshot_2023-12-13_231558_dwyhv3.png)


## 📖 About the Project

StudyNotion started as a personal project to understand how large-scale EdTech platforms work under the hood. I wanted to build something that wasn't just a CRUD app. It needed real features like payment handling, media uploads, OTP-based auth, and role-based access for students and instructors.

The platform follows a monolithic architecture where the frontend and backend live in the same codebase. The tech choices React, Node.js, Express, MongoDB, and Cloudinary were made keeping scalability and developer experience in mind.

### What it does

- Students can browse courses, enroll after payment, and track their progress
- Instructors can create and manage courses with rich media content
- The platform handles OTP verification, password resets, and email notifications out of the box
- All media (thumbnails, videos, documents) is managed through Cloudinary

## 🛠️ Tech Stack

### Frontend

- **React.js** — used for building the UI with reusable components and efficient state management
- **Redux** — handles global state across the app, especially for auth and cart
- **Tailwind CSS** — utility-first styling that made it easy to build a clean, responsive UI fast
- **Chart.js** — used in the instructor dashboard to visualize course stats and revenue
- **Figma** — the UI was designed in Figma before implementation, which helped keep things consistent

### Backend

- **Node.js** — the runtime powering the server; handles all incoming requests and business logic
- **Express.js** — lightweight framework used for routing and middleware management
- **MongoDB** — NoSQL database that stores users, courses, enrollments, and reviews in a flexible document format
- **Cloudinary** — handles all media uploads and delivery; images, videos, and documents are stored and served through Cloudinary's CDN

## 🏗️ Architecture

![Architecture Diagram](https://res.cloudinary.com/dvpulu3cc/image/upload/v1699036870/Screenshot_2023-11-04_000952_argzj8.jpg)

The project uses a monolithic architecture — both the React frontend and the Express backend are part of the same repository. The frontend communicates with the backend via REST APIs. MongoDB is used as the primary database, and Cloudinary handles all media assets.

## 🗄️ Schema Design

![Schema Design](https://res.cloudinary.com/dvpulu3cc/image/upload/v1699036870/Screenshot_2023-11-04_001024_ef0phq.jpg)

## 🔌 API Reference

### Authentication

| Endpoint         | Path                               |
|------------------|------------------------------------|
| Send OTP         | `api/v1/auth/sendotp`              |
| Signup           | `api/v1/auth/signup`               |
| Login            | `api/v1/auth/login`                |
| Reset Pass Token | `api/v1/auth/reset-password-token` |
| Reset Password   | `api/v1/auth/reset-password`       |

### Profile

| Endpoint               | Path                                |
|------------------------|-------------------------------------|
| Get User Details       | `api/v1/profile/getUserDetails`     |
| Get Enrolled Courses   | `api/v1/profile/getEnrolledCourses` |
| Instructor Dashboard   | `api/v1/profile/instructorDashboard`|

### Payments (Student)

| Endpoint                  | Path                                      |
|---------------------------|-------------------------------------------|
| Capture Payment           | `api/v1/payment/capturePayment`           |
| Verify Payment            | `api/v1/payment/verifyPayment`            |
| Payment Success Email     | `api/v1/payment/sendPaymentSuccessEmail`  |

### Courses

| Endpoint                        | Path                                        |
|---------------------------------|---------------------------------------------|
| Get All Courses                 | `api/v1/course/getAllCourses`               |
| Get Course Details              | `api/v1/course/getCourseDetails`            |
| Edit Course                     | `api/v1/course/editCourse`                  |
| Show All Categories             | `api/v1/course/showAllCategories`           |
| Create Course                   | `api/v1/course/createCourse`               |
| Add Section                     | `api/v1/course/addSection`                 |
| Add Subsection                  | `api/v1/course/addSubSection`              |
| Update Section                  | `api/v1/course/updateSection`              |
| Update Subsection               | `api/v1/course/updateSubSection`           |
| Get Instructor Courses          | `api/v1/course/getInstructorCourses`       |
| Delete Section                  | `api/v1/course/deleteSection`              |
| Delete Subsection               | `api/v1/course/deleteSubSection`           |
| Delete Course                   | `api/v1/course/deleteCourse`               |
| Get Full Course Details (Auth)  | `api/v1/course/getFullCourseDetails`       |
| Update Course Progress          | `api/v1/course/updateCourseProgress`       |
| Create Rating                   | `api/v1/course/createRating`               |

### Ratings & Reviews

| Endpoint        | Path                        |
|-----------------|-----------------------------|
| Get Reviews     | `api/v1/course/getReviews`  |

### Catalog

| Endpoint           | Path                                  |
|--------------------|---------------------------------------|
| Category Page Data | `api/v1/course/getCategoryPageDetails`|

### Contact

| Endpoint    | Path                    |
|-------------|-------------------------|
| Contact Us  | `api/v1/reach/contact`  |

### Settings

| Endpoint               | Path                                   |
|------------------------|----------------------------------------|
| Update Profile Picture | `api/v1/profile/updateDisplayPicture`  |
| Update Profile         | `api/v1/profile/updateProfile`         |
| Change Password        | `api/v1/auth/changepassword`           |
| Delete Profile         | `api/v1/profile/deleteProfile`         |

## ⚙️ Features

### Backend

- **Auth & Authorization** — email/password login with OTP verification and forgot password flow; JWT-based session management with role-based access for students and instructors
- **Course Management** — instructors can create, update, and delete courses along with sections and subsections; students can view, enroll, and leave ratings
- **Payment Integration** — Razorpay is integrated for handling course purchases; payment verification and success emails are automated
- **Media Management** — all uploads go through Cloudinary, which handles storage, optimization, and CDN delivery
- **Markdown Support** — course content is stored in Markdown, making it easy to render formatted text on the frontend

### Frontend

The UI was designed in Figma first, then built with React and Tailwind. Here's a breakdown of what each role gets:

#### Student Pages

- **Homepage** — introduces the platform and highlights featured courses
- **Course Catalog** — browse all available courses with filters, descriptions, and ratings
- **Course Details** — full breakdown of what a course covers before enrolling
- **Cart & Checkout** — add courses to cart and complete purchase via Razorpay
- **My Courses** — view all enrolled courses and continue from where you left off
- **Course Player** — watch lectures, track progress, and navigate between subsections
- **Profile & Settings** — update personal info, change password, or delete account

#### Instructor Pages

- **Dashboard** — quick overview of all published courses with earnings and ratings
- **Insights** — detailed stats per course — views, enrollments, revenue
- **Course Builder** — create or edit courses with sections, subsections, and media uploads
- **Profile** — manage account details


## 🤝 Contributing

Contributions are welcome. If you find a bug or want to add something, feel free to fork the repo, make your changes, and open a pull request. Just make sure your changes are clean and well-tested before submitting.

## 📄 License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).

## 📬 Contact

Built and maintained by **Lavkesh Kumar**

- Email: [0xlavkesh.builds@gmail.com](mailto:0xlavkesh.builds@gmail.com)
- GitHub: [github.com/Lavkesh-kumar](https://github.com/Lavkesh-kumar/EdtechPlatform)
