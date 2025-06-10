# Spotify Clone - Music Player

This project is a clone of the Spotify web player, focusing on providing a functional music playback experience.

## Features

*   **Music Playback**: Play, pause, and seek songs.
*   **Song Navigation**: Play the next or previous song in the current playlist.
*   **Volume Control**: Adjust playback volume and mute/unmute.
*   **Dynamic Song Loading**: Loads songs from local folders.
*   **Album/Playlist Display**: Fetches and displays albums/playlists from structured folders (expects `info.json` and `cover.jpg` in each album folder).
*   **Song List**: Displays songs from the selected album/playlist.
*   **Responsive Design**: Adapts to different screen sizes, including a collapsible sidebar for mobile.

## Technologies Used

*   HTML
*   CSS (including CSS variables and flexbox/grid for layout)
*   JavaScript (vanilla JS for all functionalities including DOM manipulation, audio playback, and fetching data)

## How to Use

1.  **Clone the Repository**: Download or clone this repository to your local machine.
2.  **File Structure for Songs**:
    *   Ensure you have a `songs/` directory in the `Spotify/` project root.
    *   Inside `songs/`, create subdirectories for each album or playlist (e.g., `songs/MyAlbum1/`, `songs/MyAlbum2/`).
    *   Each album directory **must** contain:
        *   Your `.mp3` song files.
        *   A `cover.jpg` file (for the album artwork).
        *   An `info.json` file with the following structure:
            ```json
            {
                "title": "Name of Your Album/Playlist",
                "description": "A brief description of the album/playlist."
            }
            ```
    *   An example `songs/.htaccess` file is included, which might be relevant for some local server configurations to allow directory listing (though the script primarily relies on fetching `info.json`). The script attempts to fetch songs from a default `/songs/ncs` folder if no specific album is loaded initially. You might need to adjust this or ensure that folder exists.

3.  **Run the Application**:
    *   The simplest way is to open the `Spotify/index.html` file directly in your web browser.
    *   For full functionality, especially regarding fetching local song files and `info.json` across different directories, you might need to run it through a local web server. Many simple HTTP server tools are available (e.g., Python's `http.server`, Node.js `serve` or `live-server` VS Code extension). This helps avoid potential CORS or file access issues that browsers might impose on `file:///` URLs.

## Project Structure

*   `index.html`: The main HTML file for the player's structure.
*   `css/`:
    *   `style.css`: Main styles for the Spotify clone.
    *   `utility.css`: Utility CSS classes used throughout the project.
*   `js/`:
    *   `script.js`: Contains all the JavaScript logic for song playback, fetching songs/albums, DOM manipulation, and event handling.
*   `img/`: Contains all static image assets and icons used in the UI (play, pause, volume, logo, etc.).
*   `songs/`: This is where your music folders (albums/playlists) should be placed. (Initially, this directory might contain example content or be empty).
    *   `songs/.htaccess`: An example htaccess file.
*   `favicon sp.ico`: The favicon for the application.

## Notes

*   The application is designed to work with locally stored MP3 files.
*   Metadata for albums (title, description, cover image) is loaded from `info.json` files within each album's directory.
*   The initial song list displayed might be from a hardcoded path (`songs/ncs`) in the script; ensure this path exists or modify the script if needed.
```
