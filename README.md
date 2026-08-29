# QuickQueue — Real-Time Multi-Business Queue Management

## Overview

QuickQueue helps clinics, restaurants, and hair salons replace unclear physical waiting lines with real-time digital queues. Customers can find a business, join its queue, and follow their ticket from any device while authorized teams manage the line as it changes.

QuickQueue သည် ဆေးခန်းများ၊ စားသောက်ဆိုင်များနှင့် ဆံပင်ညှပ်ဆိုင်များအတွက် တန်းစီစောင့်ဆိုင်းမှုကို အချိန်နှင့်တပြေးညီ ဒစ်ဂျစ်တယ်စနစ်ဖြင့် လွယ်ကူစွာ စီမံနိုင်ရန် ကူညီပေးပါသည်။

## Real-World Problem

- Customers do not know how many people are ahead of them.
- Waiting times are unclear and difficult to plan around.
- Customers often must remain physically present to keep their place.
- Small businesses commonly rely on paper-based queue management.

## Solution

Customers discover shops by category, open a shop, select a service, and join its live queue. QuickQueue issues a readable ticket and keeps its status synchronized through Cloud Firestore. Customers can see people ahead and an estimated wait, while approved owners and staff manage queue progress.

## Key Features

- English and Myanmar language support
- Customer, Staff, Owner, and Admin roles
- Customer registration and login
- Owner application with admin approval
- Staff application using shop invite codes
- Owner staff approval
- Multiple shops per owner
- Multiple staff per shop
- Clinic, restaurant, and hair salon categories
- Real-time queue tickets
- Call Next, Complete, Skip, and Cancel actions
- Live estimated waiting time
- Responsive mobile-first interface

## Role Workflow

**Admin approves Owner**  
→ **Owner creates Shop**  
→ **Staff joins with Invite Code**  
→ **Owner approves Staff**  
→ **Customer joins Queue**  
→ **Staff manages Queue**

## Adm account to check-Email: staff@quickqueue.demo Password: QuickQueue123!


## Technology Stack

- HTML5
- CSS3
- Vanilla JavaScript
- Firebase Authentication
- Cloud Firestore
- Firebase real-time listeners
- Vercel deployment

## Firestore Data Structure

```text
users/{uid}
  User profile, role, application details, staff assignment, and active ticket reference

shops/{shopId}
  Business details, owner, services, timing, category, and current invite reference

shops/{shopId}/tickets/{ticketId}
  Customer ticket, service, status, and creation time

invites/{inviteCode}
  Shop and owner association for active staff invite codes
```

## Local Setup

1. Clone the repository:

   ```bash
   git clone <repository-url>
   cd <repository-folder>
   ```

2. Start a local HTTP server:

   ```bash
   python -m http.server 8765
   ```

3. Open [http://localhost:8765](http://localhost:8765) in a browser.

Opening `index.html` directly is not recommended because Firebase browser modules require HTTP hosting.

## Security

- The Firebase web configuration is public client configuration, not a private server credential.
- Firestore Security Rules enforce data access and role boundaries.
- No service-account private keys are included.
- Applicants cannot promote their own roles.
- Owners can manage only their own shops and associated staff.
- Staff can manage only their assigned shop.

Deploy and test `firestore.rules` against the intended Firebase project before making the application public.

## Screenshots

### Authentication

![Authentication](screenshots/auth.png)

### Category Browser

![Category Browser](screenshots/categories.png)

### Owner Dashboard

![Owner Dashboard](screenshots/owner-dashboard.png)

### Staff Dashboard

![Staff Dashboard](screenshots/staff-dashboard.png)

### Queue Ticket Status

![Queue Ticket Status](screenshots/ticket-status.png)

## Live Demo

- **Live Application:** https://quickqueuee.netlify.app/
- **Hackathon Submission:** Coming soon

## Prototype Scope

QuickQueue is a working hackathon prototype intended to demonstrate the product workflow and technical approach. It is not a production-ready system.

## Future Improvements

- SMS notifications
- QR check-in
- Business analytics
- Appointment scheduling
- Shop verification
- Production App Check and monitoring

## License

Built for hackathon demonstration purposes.
