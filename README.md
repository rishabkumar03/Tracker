# Real-Time Location Tracker

A simple real-time location tracking application built with Node.js, Express, Socket.IO, and Leaflet.js. This application allows multiple users to share their live location on an interactive map.

## Features

- **Real-time location sharing**: Users can share their current location with others in real-time
- **Interactive map**: Built with Leaflet.js and OpenStreetMap tiles
- **Multi-user support**: Multiple users can connect and see each other's locations
- **Auto-disconnect handling**: Users are automatically removed from the map when they disconnect
- **Responsive design**: Works on both desktop and mobile devices

## Technologies Used

- **Backend**: Node.js, Express.js, Socket.IO
- **Frontend**: HTML5, CSS3, JavaScript, Leaflet.js
- **Template Engine**: EJS
- **Real-time Communication**: WebSockets via Socket.IO
- **Maps**: Leaflet.js with OpenStreetMap tiles

## Prerequisites

Before running this application, make sure you have the following installed:
- Node.js (v14 or higher)
- npm (Node Package Manager)

## Installation

1. Clone the repository or download the project files
2. Navigate to the project directory
3. Install the required dependencies:
   ```bash
   npm install
   ```

## Usage

1. Start the server:
   ```bash
   node app.js
   ```

2. Open your web browser and navigate to:
   ```
   http://localhost:3000
   ```

3. Allow location access when prompted by your browser

4. Your location will appear on the map, and you can share the URL with others to see their locations in real-time

## File Structure

```
tracker/
├── app.js              # Main server file
├── package.json        # Project dependencies and scripts
├── public/
│   ├── style.css       # CSS styles
│   └── script.js       # Client-side JavaScript
└── views/
    └── index.ejs       # Main HTML template
```

## How It Works

1. **Client Connection**: When a user visits the website, their browser requests location permission
2. **Location Tracking**: The browser continuously watches the user's position using the Geolocation API
3. **Real-time Updates**: Location data is sent to the server via Socket.IO
4. **Broadcasting**: The server broadcasts location updates to all connected clients
5. **Map Display**: Each client updates their map with markers showing all users' locations

## Configuration

### Port Configuration
The application runs on port 3000 by default. You can change this in `app.js`:
```javascript
server.listen(3000); // Change to your desired port
```

### Location Accuracy Settings
You can modify location accuracy settings in `script.js`:
```javascript
{
    enableHighAccuracy: true,  // Use GPS if available
    timeout: 5000,             // Timeout for location request
    maximumAge: 0,             // Don't use cached location
}
```

## Known Issues

1. **Location Accuracy**: The application relies on the browser's Geolocation API, which may not always be accurate, especially when using IP-based location
2. **HTTPS Requirement**: For production deployment, HTTPS is required for geolocation to work properly
3. **Battery Usage**: Continuous location tracking can drain battery on mobile devices

## Troubleshooting

### Location Not Accurate
- Ensure GPS is enabled on your device
- Grant precise location permission to your browser
- Test in an area with good GPS signal
- Disable VPN if using one

### Connection Issues
- Check if the server is running on the correct port
- Ensure firewall isn't blocking the connection
- Verify that Socket.IO is properly installed

### Map Not Loading
- Check internet connection
- Verify that Leaflet.js CDN is accessible
- Check browser console for any JavaScript errors

## Security Considerations

- **Location Privacy**: Users should be aware that their location is being shared
- **HTTPS**: Use HTTPS in production to ensure secure location data transmission
- **Rate Limiting**: Consider implementing rate limiting to prevent spam
- **Authentication**: Add user authentication for private tracking groups

## Future Enhancements

- User authentication and private rooms
- Location history tracking
- Custom markers and user avatars
- Mobile app development
- Database integration for persistent data
- Geofencing alerts
- Location sharing controls

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

This project is licensed under the ISC License.

## Support

For issues or questions, please check the troubleshooting section above or create an issue in the project repository.

---

**Note**: This application is for educational purposes. Ensure you comply with privacy laws and obtain proper consent when tracking user locations in production environments.
