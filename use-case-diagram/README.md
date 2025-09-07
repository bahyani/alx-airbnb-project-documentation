# USE CASE DIAGRAM

# Draw.io Use Case Diagram Creation Guide

## 🎯 Step-by-Step Instructions for Draw.io

### 1. Setup Draw.io Canvas
1. **Open Draw.io** (app.diagrams.net)
2. **Create new diagram** → Choose "UML" → "Use Case Diagram"
3. **Set canvas size**: Custom (1600 x 1200 pixels)
4. **Enable grid** and snap to grid for alignment

### 2. System Boundary
1. **Add rectangle** from General shapes
2. **Size**: 1200 x 900 pixels
3. **Position**: Center of canvas
4. **Style**: 
   - Border: 3px solid black
   - Fill: Light gray (#f5f5f5)
   - Corner radius: 20px
5. **Add text box** above rectangle: "Airbnb Clone Backend System"

### 3. Actors Placement

#### Primary Actors (Left Side)
**Guest User:**
- **Shape**: UML Actor (stick figure)
- **Position**: 100px left of system boundary, Y: 200
- **Label**: "Guest User"
- **Color**: Blue (#3498db)

**Host User:**
- **Position**: 100px left of system boundary, Y: 400
- **Label**: "Host User"
- **Color**: Red (#e74c3c)

**System Admin:**
- **Position**: 100px left of system boundary, Y: 600
- **Label**: "System Admin"
- **Color**: Orange (#f39c12)

#### Secondary Actors (Right Side)
**Payment System:**
- **Shape**: UML Actor
- **Position**: 100px right of system boundary, Y: 250
- **Label**: "Payment System"
- **Color**: Green (#27ae60)

**Email Service:**
- **Position**: 100px right of system boundary, Y: 450
- **Label**: "Email Service"
- **Color**: Purple (#9b59b6)

**Map Service:**
- **Position**: 100px right of system boundary, Y: 650
- **Label**: "Map Service"
- **Color**: Teal (#1abc9c)

### 4. Use Cases Organization

#### Authentication Cluster (Top)
```
Y: 100, X: 150-800 (evenly spaced)
- Register Account
- User Login
- User Logout
- Verify Identity
```

#### Profile Management (Y: 200)
```
- Manage Profile
- Upload Documents
- Update Preferences
```

#### Property Management (Y: 300-400)
```
Host-specific use cases:
- Create Property Listing
- Manage Listing Details
- Set Pricing Rules
- Manage Availability Calendar
- Upload Property Photos
- Configure Amenities
```

#### Search & Discovery (Y: 450)
```
- Search Properties
- Apply Filters
- View Property Details
- Save Favorites
- View on Map
```

#### Booking Management (Y: 550-650)
```
- Create Booking Request
- Approve/Decline Booking
- Modify Booking
- Cancel Booking
- Process Check-in
- Process Check-out
```

#### Payment Processing (Y: 700)
```
- Process Payment
- Handle Refunds
- Receive Host Payout
- Manage Payment Methods
```

#### Communication (Y: 750)
```
- Send Messages
- Receive Notifications
- Automated Email Alerts
```

#### Reviews & Ratings (Y: 850)
```
- Write Guest Review
- Write Host Review
- Respond to Reviews
- Moderate Reviews
```

#### Admin Functions (Y: 900)
```
- Manage Users
- Monitor System Health
- Generate Reports
- Handle Disputes
- Content Moderation
```

### 5. Use Case Styling
- **Shape**: Ellipse/Oval
- **Size**: 120px width x 60px height
- **Border**: 2px solid #e74c3c
- **Fill**: White (#ffffff)
- **Text**: 10pt Arial, centered
- **Shadow**: Subtle drop shadow

### 6. Association Lines

#### Guest User Connections:
```
Guest → Register Account
Guest → User Login
Guest → Search Properties
Guest → View Property Details
Guest → Create Booking Request
Guest → Process Payment
Guest → Send Messages
Guest → Write Guest Review
Guest → Manage Profile
```

#### Host User Connections:
```
Host → User Login
Host → Create Property Listing
Host → Manage Listing Details
Host → Set Pricing Rules
Host → Approve/Decline Booking
Host → Receive Host Payout
Host → Respond to Reviews
Host → Upload Property Photos
```

#### Admin Connections:
```
Admin → Manage Users
Admin → Monitor System Health
Admin → Generate Reports
Admin → Handle Disputes
Admin → Content Moderation
Admin → Moderate Reviews
```

#### External System Connections:
```
Payment System → Process Payment
Payment System → Handle Refunds
Payment System → Receive Host Payout

Email Service → Automated Email Alerts
Email Service → Receive Notifications

Map Service → View on Map
Map Service → Search Properties
```

### 7. Include/Extend Relationships

#### Include Relationships (<<include>>):
```
Create Booking Request <<include>> Verify Identity
Process Payment <<include>> Verify Identity
Create Property Listing <<include>> Upload Documents
Send Messages <<include>> User Login
```

#### Extend Relationships (<<extend>>):
```
Modify Booking <<extend>> Create Booking Request
Cancel Booking <<extend>> Create Booking Request
Handle Refunds <<extend>> Process Payment
Apply Filters <<extend>> Search Properties
```

### 8. Relationship Line Styling

#### Association Lines:
- **Line type**: Solid line
- **Width**: 1px
- **Color**: Black (#000000)
- **No arrowheads**

#### Include Lines:
- **Line type**: Dashed line
- **Arrow**: Open arrow pointing to included use case
- **Label**: "<<include>>" (green text, italic)

#### Extend Lines:
- **Line type**: Dashed line
- **Arrow**: Open arrow pointing to extended use case
- **Label**: "<<extend>>" (orange text, italic)

### 9. Legend Creation
**Position**: Bottom right corner
**Content**:
```
┌─────────────────────────┐
│         Legend          │
├─────────────────────────┤
│ 👤 Primary Actors       │
│ 🔧 Secondary Actors     │
│ ○ Use Cases            │
│ ─── Associations       │
│ ┈┈▷ <<include>>        │
│ ┈┈▷ <<extend>>         │
└─────────────────────────┘
```

### 10. Final Formatting

#### Color Scheme:
- **System boundary**: Light gray background
- **Actors**: Blue gradient
- **Use cases**: White with red border
- **Include text**: Green (#27ae60)
- **Extend text**: Orange (#f39c12)

#### Typography:
- **Title**: 18pt, bold, dark blue
- **Actor labels**: 12pt, bold
- **Use case text**: 10pt, regular
- **Relationship labels**: 8pt, italic

### 11. Export Settings
1. **File → Export as → PNG**
2. **Settings**:
   - Zoom: 100%
   - Border width: 20px
   - Transparent background: No
   - Resolution: 300 DPI
3. **Filename**: `airbnb-use-case-diagram.png`

## 📁 Directory Structure

```
alx-airbnb-project-documentation/
├── use-case-diagram/
│   ├── airbnb-use-case-diagram.png          ← Main diagram
│   ├── use-case-diagram.drawio              ← Source file
│   ├── use-case-specifications.md           ← Detailed descriptions
│   └── README.md                            ← Instructions
```

## 📋 Use Case Specifications Template

For each major use case, create detailed specifications:

### Use Case: Create Booking Request

**ID**: UC-BK-001  
**Name**: Create Booking Request  
**Actor**: Guest User  
**Description**: Guest selects dates and creates a booking request for a property  

**Preconditions**:
- User is logged in
- Property is available for selected dates
