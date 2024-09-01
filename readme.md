# GuestSuite

## Overview

GuestSuite is a comprehensive platform designed to connect users with available apartments or messes, facilitating easy bookings, inquiries, and management. The platform includes robust features for both seekers and advertisers, along with user authentication and profile management.

## Features

### Authentication

1. **Login:** Users can log in using their email and password.
2. **Register:** New users can register with basic details.
3. **Password Reset:** Users can reset their password via email.
4. **Profile Management:** Users can add and edit details such as phone number, address, and education.
5. **Two-Factor Authentication (2FA):** Additional security for user accounts.

### Apartment

1. **Browse Apartments:** Users can view multiple apartments with detailed descriptions and images.
2. **Inquire:** Users can request more information about specific apartments.
3. **Book an Apartment:** Users can book an apartment directly through the platform.
4. **Filter Options:** Apartments can be filtered by cost, area, neighborhood, and amenities (e.g., parking, gym).
5. **Google Maps Integration:** View apartments on Google Maps for location insights.
6. **Virtual Tours:** View virtual tours of apartments if available.
7. **Availability Calendar:** Check the availability of apartments through a calendar view.

### Mess (Shared Housing)

1. **Browse Messes:** Users can view multiple messes with detailed descriptions and images.
2. **Inquire:** Users can request more information about specific messes.
3. **Book a Mess:** Users can book a mess directly through the platform.
4. **Filter Options:** Messes can be filtered by cost, area, roommate preferences, and amenities.
5. **Google Maps Integration:** View messes on Google Maps for location insights.
6. **Virtual Tours:** View virtual tours of messes if available.
7. **Availability Calendar:** Check the availability of messes through a calendar view.

### Advertiser

1. **Post Listings:** Advertisers can post new apartments or messes with detailed information and images.
2. **Manage Listings:** Advertisers can edit or delete their listings.
3. **View Inquiries:** Advertisers can view inquiries made by potential tenants.
4. **Performance Analytics:** Advertisers can see the performance of their listings (e.g., number of views, inquiries).
5. **Automated Listing Suggestions:** Receive automated suggestions for improving listing visibility and appeal based on market trends.

### Apartment or Mess Seeker

1. **Advanced Search:** Seekers can use advanced filters to find suitable apartments or messes based on cost, area, amenities, and other preferences.
2. **Google Maps Integration:** Seekers can view all listings on Google Maps.
3. **Booking Management:** Seekers can view and manage their bookings.
4. **Wishlist:** Users can save favorite apartments or messes to a wishlist for future reference.
5. **Reviews and Ratings:** Users can leave reviews and ratings for apartments or messes they have booked.
6. **Price Alerts:** Set up alerts for price changes or new listings matching criteria.
7. **Chat Feature:** Real-time chat with advertisers for quick inquiries and responses.

## Unique Apartment Features

1. **Certified Quality Ratings:**

   - **Certification Levels:** Apartments are rated based on facilities, security, and environmental quality with levels such as "Certified Premium," "Certified Standard," and "Certified Basic."
   - **Certification Criteria:**
     - **Facilities:** Quality of amenities, maintenance standards, and overall condition.
     - **Security:** Measures like CCTV coverage, secure access systems, and on-site security personnel.
     - **Environment:** Cleanliness, noise levels, green spaces, and overall living conditions.

2. **Certification Badge:**

   - **Visible Badge:** Apartments with certification are marked with a badge on listings.
   - **Detailed Report:** Users can view a detailed report of the certification criteria and results.

3. **Certification Process:**

   - **On-Site Inspections:** Regular inspections and evaluations to ensure standards are met.
   - **Resident Feedback:** Incorporates feedback from current residents for validation.

4. **Continuous Improvement:**

   - **Re-Certification:** Apartments are re-certified periodically to ensure ongoing quality.
   - **Feedback Loop:** Residents can provide feedback on certification accuracy and suggest improvements.

5. **Certification Benefits:**

   - **Enhanced Trust:** Provides verified information about apartment quality and safety.
   - **Competitive Edge:** Differentiates the platform by offering added assurance and credibility.

6. **Certification Categories:**

   - **Facility Certification:** Quality and range of amenities, maintenance, and cleanliness.
   - **Security Certification:** Security measures and protocols.
   - **Environmental Certification:** Living environment quality including noise, air quality, and green spaces.

7. **Direct Moving Assistance Connection:**
   - **Service Integration:** Directly connect with moving assistance professionals through the platform.
   - **Service Directory:** Access a directory of moving companies and professionals, complete with reviews, ratings, and contact details.
   - **Booking System:** Request quotes, schedule moving services, and manage the moving process within the platform.
   - **In-App Communication:** Facilitate seamless communication between users and moving service providers through in-app messaging.
   - **Moving Tips and Resources:** Provide users with helpful resources such as packing tips, moving checklists, and guides.

## Models

### User

- **email (unique)**
- **password**
- **first_name**
- **last_name**
- **phone_number**
- **address**
- **education**
- **profile_picture**
- **two_factor_auth_enabled (boolean)**

### Apartment

- **title**
- **description**
- **cost**
- **area**
- **neighborhood**
- **images (multiple)**
- **availability_status**
- **location (GeoJSON for Google Maps)**
- **amenities (e.g., parking, gym)**
- **virtual_tour_link**
- **availability_calendar (for checking availability)**

### Mess

- **title**
- **description**
- **cost**
- **area**
- **roommate_preferences**
- **images (multiple)**
- **availability_status**
- **location (GeoJSON for Google Maps)**
- **amenities (e.g., parking, Wi-Fi)**
- **virtual_tour_link**
- **availability_calendar (for checking availability)**

### Advertiser

- **user (ForeignKey to User)**
- **listings (ManyToMany with Apartment and Mess)**
- **contact_info**
- **performance_metrics (e.g., views, inquiries)**

### Booking

- **user (ForeignKey to User)**
- **apartment (ForeignKey to Apartment, nullable)**
- **mess (ForeignKey to Mess, nullable)**
- **booking_date**
- **status (Pending, Confirmed, Cancelled)**
- **payment_status (e.g., Paid, Unpaid)**

### Inquiry

- **user (ForeignKey to User)**
- **listing (ForeignKey to Apartment or Mess)**
- **message**
- **inquiry_date**
- **status (Pending, Responded, Closed)**

### Chat

- **user (ForeignKey to User)**
- **advertiser (ForeignKey to Advertiser)**
- **message**
- **timestamp**

### PriceAlert

- **user (ForeignKey to User)**
- **apartment (ForeignKey to Apartment, nullable)**
- **mess (ForeignKey to Mess, nullable)**
- **criteria (e.g., maximum price, area)**
- **alert_type (e.g., price drop, new listing)**

## Setup

1. **Clone the Repository:**
   ```bash
   git clone <repository_url>
   ```
