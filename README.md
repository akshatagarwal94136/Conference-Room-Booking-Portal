# Conference-Room-Booking-Portal

A web-based portal to book meeting rooms and conference halls online. It replaces manual booking with a centralized system that has a calendar view, availability filtering and role-based access, so double bookings and scheduling conflicts are avoided.

**Live demo:** https://akshatagarwal94136.github.io/Conference-Room-Booking-Portal/

---

## Problem Statement

| Current issues | Expected solution |
|---|---|
| Manual booking causes confusion | Web-based centralized portal |
| Double bookings and scheduling conflicts | Calendar view to check slots quickly |
| No centralized access across ministries | Availability filters to avoid conflicts |
| No proper tracking of past bookings | Record-keeping of bookings (localStorage) |
| No role-based login, anyone can misuse the system | Role-based access for Admin and Member |

---

## Features

- **Role-based access:** two roles, `Member` (staff, can book rooms) and `Admin` (can book and delete bookings). Login is required to book.
- **Interactive calendar:** month view; click a date to open the booking modal.
- **Room selection:** Meeting Room A (5 people), B (10), C (15), D (20), Conference Hall A (30) and Conference Hall B (40).
- **Availability filtering:** after choosing a room and date, only free time slots can be selected. Booked slots are marked and cannot be clicked, which prevents double booking.
- **Booking details:** add a meeting title and an optional description, then confirm the booking.
- **Persistent records:** bookings and the logged-in user are stored in the browser's localStorage, so data stays after a page reload.
- **Home page and extras:** W-Space landing page with solutions, amenities, locations, FAQs, footer, About page, Privacy Policy and Terms & Conditions.

### Time slots

`9:00 AM - 10:00 AM` · `10:15 AM - 11:15 AM` · `11:30 AM - 12:30 PM` · `1:30 PM - 2:30 PM` · `2:45 PM - 3:45 PM` · `4:00 PM - 5:00 PM` · `5:15 PM - 6:15 PM` · `6:30 PM - 7:30 PM` · `7:45 PM - 8:45 PM`

---

## Tech Stack

| Layer | Technology |
|---|---|
| Structure | HTML5 (semantic markup) |
| Styling | CSS3 (W-Space theme with CSS variables) |
| Logic | Vanilla JavaScript (core logic, DOM manipulation, dynamic data handling) |
| Data storage | Browser localStorage |
| Hosting | GitHub Pages |

### localStorage keys

- `weworkBookings` - array of booking objects:

```json
{
  "id": 1759234427539,
  "date": "2025-08-31",
  "timeSlot": "9:00 AM - 10:00 AM",
  "room": "Meeting Room A",
  "title": "meeting",
  "description": "meeting",
  "user": "Member User",
  "role": "Member"
}
```

- `weworkUser` - current login state, for example `{ "username": "Member User", "role": "Member" }`

---

## How It Works

1. Log in from the login button. For the demo, use `member` or `admin` as the username.
2. Click a date on the calendar.
3. Select a room. The available slots for that room and date are shown.
4. Pick a free time slot, enter a title (and optional description) and click **Confirm Booking**.
5. Admin can also delete existing bookings.

---

## Run Locally

No build step or dependencies are needed.

```bash
git clone https://github.com/sakshiagarwal8949/Conference-Room-Booking-Portal.git
cd Conference-Room-Booking-Portal
```

Open `index.html` in a browser, or serve the folder with the VS Code **Live Server** extension.

---

## Known Limitations

- Bookings are stored in localStorage, so they are per browser and per device (there is no backend or shared database yet).
- The past date/time is not yet blocked for booking.
- Only Admin can delete bookings.
- All city cards currently lead to the same booking page.

## Future Enhancements

- **Time restriction:** stop users from booking slots in the past.
- **Email notifications:** booking confirmation using a mailing service such as EmailJS.
- **Multi-location support:** make booking logic aware of the selected location (for example Whitefield, Bengaluru).
- **User settings:** let users view and cancel their own bookings.
- **Backend and database:** shared storage so bookings are visible across devices.

---

## Author

**Akshat Agarwal**

