# Event Venue Booking System

## What's built so far
**Backend (Step 1):**
- Models: User, Venue (with embedded slots), Booking
- Auth: Signup/Login with JWT + bcrypt password hashing
- Venue APIs: list, get one, create (admin), add slots (admin), delete (admin)
- Booking APIs: book a slot, view my bookings, cancel a booking, view all bookings (admin)
- Double-booking is prevented — a slot flips to `isBooked: true` the moment it's reserved.

**Frontend (Step 2):**
- `login.html` / `signup.html` — auth pages, store JWT in localStorage
- `venues.html` — browse all venues, filter by category
- `venue-detail.html` — see venue info, pick an open slot, submit a booking
- `my-bookings.html` — view your bookings, cancel one
- `css/style.css` — shared peacock-green/blue theme (matches your portfolio)
- `js/api.js` — shared fetch wrapper + navbar + auth helpers

**Admin Panel (Step 3):**
- `admin.html` — only visible/usable to users with `role: "admin"`
- Tab 1 **Add Venue**: form to create a new venue (no more Postman needed)
- Tab 2 **Manage Venues**: see every venue's slots at a glance, add new slots with a date/time picker, delete a venue
- Tab 3 **All Bookings**: table of every booking on the platform — event, venue, user, date, price, status

## How to run it

### 1. Backend
```
cd backend
npm install
# copy .env.example to .env and fill in your MONGO_URI + JWT_SECRET
npm run dev
```
Should print `Server running on port 5000` and `MongoDB Connected ✅`.

### 2. Frontend
The frontend is plain HTML/CSS/JS — no build step needed.
- Open the `frontend` folder in VS Code
- Right-click `login.html` → **Open with Live Server** (or just double-click the file to open in a browser)
- Make sure `API_BASE` in `js/api.js` matches your backend URL (default: `http://localhost:5000/api`)

### 3. Try the flow
1. Sign up a new account on `signup.html`
2. Make that user an admin: in MongoDB Compass, open the `users` collection and change their `role` field to `"admin"`. Log out and log back in so the new role loads.
3. Click **Admin** in the navbar → **Add Venue** tab → fill in the form and submit
4. Go to **Manage Venues** tab → add a few slots to that venue with the date/time picker
5. Go to `venues.html`, click your venue, pick a slot, fill in event name, click **Confirm Booking**
6. Check `my-bookings.html` to see it — and check **Admin → All Bookings** to see it from the admin side too

## Next steps
1. **Polish (Step 4):** Loading states, better validation, maybe a booking confirmation email
2. **Deploy (Step 5):** Host backend on Render (free tier) + frontend on Netlify, connect them with real URLs

Reply "next step" when you're ready and we'll polish the UI and get it deployment-ready.


