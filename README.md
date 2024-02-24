```

█▀ █░█ █▀▀ █░░ ▀█▀ █▀▀   █▀█ █▄░█ █▀▀   █▀█ ▄▀█ █▀▀ █▀▀ █▀█
▄█ ▀▄▀ ██▄ █▄▄ ░█░ ██▄   █▄█ █░▀█ ██▄   █▀▀ █▀█ █▄█ ██▄ █▀▄

Check work @https://svelteonepager.web.app/
```

# SvelteOnePager with Firebase Hosting

## About

SvelteOnePager is an open-source, one-page website template built with Svelte, integrated with Firebase for easy deployment. It simplifies the development and deployment process, making it perfect for personal, educational, or small business websites.

![SvelteOnePager Screenshot](https://i.ibb.co/hf0pC8H/screenshot-svelteonepager.png)

## Features

- Built with Svelte for reactive web development.
- Firebase integration for easy hosting and real-time updates.
- Responsive design for a great look on any device.
- Easy to customize for your specific needs.
- SEO friendly to help your site rank well.

## Quick Start

### Clone and Setup

1. Clone the repository:

```bash
git clone https://github.com/Faktor22/SvelteOnePager.git
```

2. Navigate to the project directory and install dependencies:

```bash
cd SvelteOnePager
npm install
```

### Firebase Setup

3. Install Firebase CLI (if you haven't already):

```bash
npm install -g firebase-tools
```

4. Login to Firebase:

```bash
firebase login
```

5. Initialize your Firebase project:

```bash
firebase init
```

Follow the prompts to link your Firebase project and configure the hosting settings.

### Develop & Run

6. Start the development server:

```bash
npm run dev
```

Open http://localhost[port] in your browser to see your project live. Please note that [port] should be replaced with the actual port number your project is running on. This number can vary depending on your setup. By default, Svelte apps start on port 5000, but if this port is already in use or your setup is configured differently, the port number might be different. You can usually find the correct port number printed in the terminal where you ran the npm run dev command.

### Deploy on Firebase

7. Build your Svelte project:

```bash
npm run build
```

8. Deploy to Firebase Hosting:

```bash
firebase deploy
```

## Contributing

Contributions are welcome! Feel free to fork the repo, make your improvements, and submit a pull request.

## License

SvelteOnePager is open source and available under the MIT license. Free for both personal and commercial use.
