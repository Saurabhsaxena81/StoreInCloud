# Software Requirements Specification (SRS)  

## Project Title  
**File Management System with OTP Authentication**  

---

## 1. Introduction  

### 1.1 Purpose  
The purpose of this project is to develop a secure and user-friendly file management system where users can sign up and log in using OTP authentication. This system provides each user with 2GB of personal storage space to upload, manage, and organize files of various types, ensuring a reliable and scalable solution for secure file storage.  

### 1.2 Scope  
The system includes:  
- OTP-based authentication for enhanced user security.  
- The ability to upload, manage, and organize files of any type within a 2GB storage limit per user.  
- A real-time dashboard for monitoring storage usage and file management.  
- A responsive and visually appealing interface built with **Next.js 15** and **Tailwind CSS**.  
- Backend powered by **Appwrite** for seamless authentication, file storage, and quota management.  

This system caters to individuals and small teams seeking a simple, secure, and reliable file storage platform.  

### 1.3 Definitions, Acronyms, and Abbreviations  
- **OTP**: One-Time Password  
- **GB**: Gigabyte  
- **UI**: User Interface  
- **API**: Application Programming Interface  

### 1.4 References  
- OTP authentication guidelines for secure systems.  
- Industry standards for file management and cloud storage solutions.  
- Appwrite documentation for authentication, storage, and database services.  

---

## 2. System Requirements  

### 2.1 Functional Requirements  
1. **User Registration and Authentication**:  
   - Users must provide a valid phone number or email to receive OTP during registration.  
   - OTP verification is required to complete the registration process.  
   - OTP will also be used for secure logins.  

2. **File Management**:  
   - Users can upload files of any type, such as documents, images, audio, and video.  
   - Files should be listed with metadata (e.g., name, size, type, upload date).  
   - Users can delete or replace files as needed.  

3. **Storage Quota Management**:  
   - Each user is allocated 2GB of storage.  
   - Real-time notifications and warnings will be displayed when storage usage exceeds 80%.  

4. **Dashboard**:  
   - Displays uploaded files, file metadata, and remaining storage.  
   - Provides a clean, user-friendly interface for managing files and account settings.  

5. **Error Handling**:  
   - System alerts for invalid OTPs, storage limit exceedance, or unsupported file types (if applicable).  

### 2.2 Non-Functional Requirements  
1. **Performance**:  
   - OTPs should be delivered within 5 seconds for 95% of requests.  
   - The system must support up to 500 concurrent users.  

2. **Scalability**:  
   - Designed to accommodate thousands of users and scalable using Appwrite’s cloud services.  

3. **Security**:  
   - All communications must be encrypted using HTTPS.  
   - Files and user data must comply with data protection standards such as GDPR.  

4. **Usability**:  
   - The system should work seamlessly across devices (mobile, tablet, desktop).  
   - Tailwind CSS ensures a responsive and intuitive interface.  

5. **Reliability**:  
   - The platform should guarantee 99.9% uptime using Appwrite’s backend reliability.  

---

## 3. System Design  

### 3.1 Architecture  
- **Frontend**:  
  Built with **Next.js 15** for server-side rendering and dynamic routing, paired with **Tailwind CSS** for responsive design and ease of customization.  

- **Backend**:  
  Powered by **Appwrite**, which provides secure OTP authentication, file storage, and database services.  

- **Database**:  
  Managed using **Appwrite Database** for storing user information, file metadata, and storage usage statistics.  

- **Storage**:  
  Appwrite’s scalable file storage ensures reliable and secure file uploads, with quota enforcement per user.  

### 3.2 Components  
1. **Frontend**:  
   - Responsive file upload interface with drag-and-drop and "Browse" options.  
   - Real-time dashboard showing storage usage and file list.  

2. **Backend**:  
   - OTP generation and verification via Appwrite's authentication API.  
   - File upload, retrieval, and quota management handled through Appwrite’s storage services.  

3. **Database**:  
   - Stores user credentials, file metadata, and quota details using Appwrite’s database.  

4. **File Storage**:  
   - Securely stores files in Appwrite’s storage module with user-specific restrictions.  

---

## 4. Assumptions and Constraints  

- Users must provide a valid email address or phone number to receive OTPs.  
- Maximum file size per upload is limited to 1GB.  
- The total storage limit per user is capped at 2GB.  
- The platform is dependent on Appwrite’s backend infrastructure for authentication, storage, and database services.  

---

## 5. Acceptance Criteria  

1. Users must successfully register and log in only after OTP verification.  
2. Users should be able to upload files of any type until the 2GB quota is reached.  
3. The dashboard should accurately display uploaded files and remaining storage capacity.  
4. OTPs must be delivered and verified within 10 seconds for 95% of cases.  

---

## 6. Future Enhancements  

- Provide subscription options for increasing storage capacity.  
- Add file-sharing capabilities with permissions for view or edit access.  
- Enable folder organization and advanced file search/filtering features.  
- Implement two-factor authentication (2FA) using Appwrite for enhanced security.  
- Introduce activity logs to track file uploads, downloads, and deletions.  

---

# Synopsis  

## Project Title  
**Advanced File Management System with OTP Authentication**  

---

## Objective  
The goal of this project is to create a comprehensive, secure, and user-friendly file management system. Users can log in using OTP verification via email, upload files, organize them efficiently, and share them with others. The platform categorizes files based on their type for easier navigation and offers essential features like renaming, deleting, and viewing files. This project is inspired by Google Drive but emphasizes simplicity, security, and advanced categorization.  

---

## Key Features  

### 1. **User Authentication**  
- **OTP-Based Login**:  
  - Users log in securely using an email-based OTP verification system.  
  - Ensures seamless and safe authentication through **Appwrite's services**.  

### 2. **File Management**  
- **Upload Files**:  
  - Supports files of any type (e.g., images, videos, documents).  
- **Rename Files**:  
  - Rename files directly from the dashboard for better organization.  
- **Delete Files**:  
  - Permanently remove files from the system when needed.  
- **Share Files**:  
  - Share files securely with other users by entering their email addresses.  
- **View Files**:  
  - In-app file viewer supports various formats (e.g., image previews, document viewers).  

### 3. **File Categorization**  
- Files are automatically organized into specific categories:  
  - **Images**: All image files like `.jpg`, `.png`, `.gif`.  
  - **Audio and Video**: Media files such as `.mp3`, `.wav`, `.mp4`.  
  - **Documents**: Office and PDF files like `.docx`, `.xlsx`, `.pdf`.  
  - **All Files**: Unified section to view and manage all uploaded files.  

### 4. **Storage Management**  
- Each user is provided with **2GB of storage space**.  
- Real-time notifications alert users when their storage usage reaches 80% and 100%.  

### 5. **User Dashboard**  
- A visually appealing, responsive dashboard designed with **Next.js 15** and **Tailwind CSS**.  
- Displays:  
  - Uploaded files by category and metadata (e.g., file name, size, date uploaded).  
  - Remaining storage quota in an intuitive progress bar format.  
- Easy navigation between different sections for file management.  

---

## Technology Stack  

- **Frontend**:  
  - Built using **Next.js 15** for its dynamic routing, server-side rendering, and performance optimization.  
  - Styled with **Tailwind CSS** to create a modern, responsive, and user-centric interface.  

- **Backend**:  
  - Powered by **Appwrite**, offering robust authentication, file storage, and real-time data synchronization.  

---

## Scope  

The system is designed for individual users or small teams who require a lightweight, secure, and efficient platform for file storage and collaboration. The solution aims to:  
- Provide secure and fast access through OTP-based authentication.  
- Simplify file upload, categorization, and management.  
- Enable seamless file sharing for improved collaboration.  
- Serve as a scalable and customizable alternative to larger, complex platforms like Google Drive.  

---

## Unique Selling Points  

1. **Categorized File Organization**:  
   - Automatically sorts files by type into intuitive sections, making it easier for users to find what they need.  

2. **Lightweight and Fast**:  
   - Built on modern technologies to ensure a responsive and seamless user experience.  

3. **Simplified Sharing**:  
   - Sharing files is as easy as entering an email address, eliminating complicated permission management.  

4. **Privacy and Security**:  
   - OTP-based authentication and Appwrite’s backend services ensure user data and files are protected.  

5. **Cross-Platform Usability**:  
   - Fully responsive design ensures usability across desktops, tablets, and smartphones.  

---

## Future Enhancements  

- **Storage Expansion Plans**:  
  - Introduce subscription-based models for users to increase their storage quota.  

- **File Collaboration**:  
  - Add multi-user collaboration features such as shared editing and commenting.  

- **Folder Support**:  
  - Enable folder creation and hierarchy for better file organization.  

- **Advanced Search and Filters**:  
  - Implement search functionality with filters based on file type, name, or upload date.  

- **Activity Logs**:  
  - Track file actions like uploads, deletions, and shares for improved user control.  

- **Multi-Factor Authentication (MFA)**:  
  - Enhance security by incorporating MFA options such as authenticator apps or SMS codes.  

---

This project represents a modern approach to file management by combining simplicity, functionality, and security. Built with the latest technologies like **Next.js**, **Tailwind CSS**, and **Appwrite**, it provides a scalable and efficient platform tailored to meet users' everyday storage and file-sharing needs.
