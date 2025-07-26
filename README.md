# 🔥 North Macedonia Wildfire Tracker

A real-time wildfire monitoring and reporting system designed specifically for North Macedonia. This project helps communities stay informed about active wildfires and allows citizens to report new incidents quickly and efficiently.

---

## 🌟 What This Project Does

Imagine you're hiking in the mountains near Skopje and you spot smoke in the distance. With this tracker, you can immediately report the wildfire by simply clicking on the map, filling out a quick form, and helping emergency services respond faster. The system shows all active fires across North Macedonia in real-time, complete with severity levels, estimated sizes, and duration.

The app works seamlessly on both desktop and mobile devices, making it perfect for field reporting. Whether you're a forest ranger, local resident, or just someone who cares about fire safety, this tool puts critical information at your fingertips.

---

## 🗺️ Key Features

- **Interactive Map**: Click anywhere on the map to report a new wildfire  
- **Multiple Map Views**: Switch between street maps, topographic views, and satellite imagery  
- **Bilingual Support**: Full Macedonian and English language support  
- **Real-time Statistics**: Live tracking of active fires, severity levels, and affected areas  
- **Mobile-Optimized**: Works perfectly on smartphones for field reporting  
- **Fire History**: Browse through all previously reported fires  
- **Smart Notifications**: Automatic alerts when fire durations expire  
- **Offline Capable**: Reports are saved locally if the database is unavailable  

---

## 🛠️ Technologies Used

### Frontend

- **HTML5 & CSS3**: Modern responsive design with gradient backgrounds and glassmorphism effects  
- **Vanilla JavaScript**: No heavy frameworks - just clean, efficient code  
- **Leaflet.js**: Interactive mapping library for smooth map interactions  
- **CSS Grid & Flexbox**: Responsive layouts that work on any screen size  

### Backend & Database

- **Supabase**: PostgreSQL database with real-time capabilities  
- **Row Level Security (RLS)**: Advanced security model (more on this below)  
- **REST API**: Simple HTTP endpoints for data operations  

### Map Data Sources

- **OpenStreetMap**: Primary map tiles  
- **CartoDB**: Beautiful Voyager map style  
- **OpenTopoMap**: Detailed topographic information  
- **German OSM**: Alternative tile source for reliability  

---

## 🔒 Security: Row Level Security (RLS) Explained

Here's where things get interesting from a security perspective. Instead of building a traditional backend with authentication middleware, this project uses Supabase's **Row Level Security (RLS)** - think of it as having a security bouncer at every database table.

### How RLS Works

Traditional web apps work like this:  
`User → Frontend → Backend API → Database`  
With RLS, it's more like:  
`User → Frontend → Database (with built-in security rules)`

### Why This Matters

**The Problem with Traditional Security**: Most apps put all their security logic in the backend code. If someone finds a bug in your API or bypasses it entirely, they could potentially access or modify any data they want.

**The RLS Solution**: With RLS, security rules are baked right into the database itself. Even if someone somehow bypasses the frontend entirely and connects directly to the database, they still can't do anything the security policies don't allow.

### Real-World Example

In this wildfire tracker:

- Anyone can read fire reports (public safety information should be accessible)  
- Anyone can create new fire reports (I want to encourage reporting)  
- Only the original reporter can modify their own reports  
- Expired fires can be marked as concluded by anyone (community verification)  

These rules live in the database, not in this JavaScript code. So even if someone tries to be sneaky and send malicious requests directly to my database, PostgreSQL will just say **"nope, not allowed"** based on the RLS policies.

---

## 📱 Mobile Experience

One of the biggest challenges was making sure the interactive map works perfectly on mobile devices. Leaflet.js maps can be tricky on smartphones, especially with different screen orientations and browser quirks.

The app includes several mobile-specific optimizations:

- **Touch-friendly controls**: Larger buttons and touch targets  
- **Orientation handling**: Map resizes properly when you rotate your phone  
- **iOS Safari fixes**: Special handling for Safari's unique behaviors  
- **Offline capabilities**: Works even with poor cellular connection  

---

## 🌍 Localization

The app speaks both Macedonian and English fluently. All text, form labels, and even the map controls switch languages with a single click. This was important because wildfire reporting needs to be accessible to all citizens, regardless of their preferred language.

---

## 🤝 Contributing

This is a community safety project, so contributions are welcome! Whether you're a developer, a firefighter, or just someone who cares about fire safety, there are ways to help:

- Report bugs or suggest features  
- Translate to other languages  
- Test the mobile experience on different devices  
- Share with local emergency services or community groups  

People feel free to use this code for similar projects in your region. Wildfire safety shouldn't be limited by borders or licensing restrictions!!

---

## 🙏 Acknowledgments

- **OpenStreetMap Contributors**: For providing free, open map data  
- **Leaflet.js Team**: For making interactive maps accessible to everyone  
- **Supabase**: For democratizing real-time databases  
- **North Macedonia Fire Services**: For inspiring this project  

---

> Built with dedication for the opportunity of safer communities.  
> **Бркај работа :^) **
