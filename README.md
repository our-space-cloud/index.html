# Our Space 💕

A private, self-hosted web application for couples to share memories, notes, links, and chat - all stored securely in your GitHub repository.

![Version](https://img.shields.io/badge/version-1.0.0-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![GitHub Pages](https://img.shields.io/badge/deploy-GitHub%20Pages-orange)

## ✨ Features

- 📸 **Memories** - Save precious moments with photos and descriptions
- 📝 **Notes** - Write sweet messages to each other
- 🔗 **Links** - Bookmark special places and websites
- 💬 **Chat** - Private real-time messaging
- 👑 **Admin System** - Approval-based room joining
- 🔄 **Dual Storage** - Server or Private GitHub storage
- 🏛️ **Preserve Mode** - Freeze memories forever
- 🔐 **Secure** - Your data, your GitHub, your control

## 🚀 Quick Start

### Prerequisites
- GitHub account
- 5 minutes of your time

### Deployment Steps

1. **Fork or create this repository**
   ```bash
   # Option 1: Fork this repo
   # Click "Fork" button above
   
   # Option 2: Create new repo and upload files
   # - index.html
   # - .github/workflows/deploy.yml
   ```

2. **Generate Personal Access Token**
   - Go to [github.com/settings/tokens](https://github.com/settings/tokens)
   - Click "Generate new token (classic)"
   - Name: "Our Space Token"
   - Permissions: ✅ `repo` (Full control)
   - Copy the token immediately!

3. **Configure Repository Secrets**
   - Go to Settings → Secrets and variables → Actions
   - Add two secrets:
     - `OSW_REPO`: `your-username/your-repo-name`
     - `OSW_TOKEN`: Your Personal Access Token

4. **Enable GitHub Pages**
   - Go to Settings → Pages
   - Source: Deploy from a branch
   - Branch: `gh-pages`
   - Click Save

5. **Deploy**
   - Push to main branch (or manually trigger workflow)
   - Wait for deployment (1-2 minutes)
   - Access at: `https://your-username.github.io/your-repo-name/`

## 📖 User Guide

### Registration
1. Open the app URL
2. Click "Register"
3. Choose username (3-30 chars, lowercase, letters/numbers/./\_)
4. Set display name (how your partner sees you)
5. Create password (⚠️ **Cannot be recovered!**)

### Creating a Room
1. Login to your account
2. Click "Create New Room"
3. Get a unique 6-character room code
4. Share code with your partner
5. You become the admin

### Joining a Room
1. Login to your account
2. Click "Join Existing Room"
3. Enter room code from your partner
4. Wait for admin approval
5. Start sharing memories!

### Storage Modes

#### Server Mode (Default)
- Data stored in deployer's GitHub
- No setup required
- Free hosting
- All users start here

#### Private Mode (Admin Only)
- Data stored in your own GitHub
- Full control of your data
- Can switch back to server anytime
- Admin configures in Settings

## 🔐 Security

- **Password Security**: Passwords are base64 encoded (⚠️ **Note**: This is not cryptographically secure. For production, implement proper hashing)
- **Token Security**: Keep your Personal Access Token secret
- **Private Repository**: Recommended for privacy
- **HTTPS**: All API calls use HTTPS
- **Data Control**: You own your data completely

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────┐
│                      Your GitHub Repo                    │
├─────────────────────────────────────────────────────────┤
│                                                          │
│  Server Storage (Default):                              │
│  ├── users_data.txt       (all user accounts)           │
│  ├── master_rooms.txt     (global room registry)        │
│  ├── export.txt           (private room tracking)       │
│  └── ROOMCODE_*.txt       (room data files)             │
│                                                          │
│  Private Storage (Optional):                            │
│  └── User's GitHub → ROOMCODE_*.txt only                │
│                                                          │
└─────────────────────────────────────────────────────────┘
```

## 📁 File Structure

```
our-space/
├── index.html                 # Main application
├── config.js                  # Auto-generated (do not commit)
├── .github/
│   └── workflows/
│       └── deploy.yml         # GitHub Actions workflow
├── README.md                  # This file
└── (auto-generated files)
    ├── users_data.txt         # User accounts
    ├── master_rooms.txt       # Room registry
    ├── export.txt             # Private tracking
    └── ROOMCODE_*.txt         # Room data
```

## 🎨 Customization

### Change Colors
Edit CSS variables in `index.html`:
```css
:root {
    --primary-pink: #f8d7da;
    --secondary-lavender: #e7d3f4;
    --soft-blue: #d4f1f4;
}
```

### Change File Size Limit
Edit in `index.html`:
```javascript
maxFileSize: 50 * 1024 * 1024  // 50MB
```

## 🔧 Troubleshooting

### "Server not configured"
- Verify secrets `OSW_REPO` and `OSW_TOKEN` are set
- Check GitHub Actions workflow ran successfully
- Clear browser cache

### "Cannot access repository"
- Verify token has `repo` permission
- Check token hasn't expired
- Ensure repository is accessible

### "Room not found"
- Verify room code (case-sensitive)
- Check `master_rooms.txt` exists
- For private rooms, check `export.txt`

## 📊 Data Management

### Backup
```bash
# Clone your repository
git clone https://github.com/username/your-repo.git

# All data files are included
# Store safely
```

### Restore
1. Go to repository → File → History
2. Find desired version
3. Copy content and commit

### Export
- All data is in JSON format
- Easy to read and parse
- Can export to other formats

## 🌟 Roadmap

- [ ] End-to-end encryption
- [ ] Better password hashing
- [ ] File attachments (PDFs, videos)
- [ ] Mobile apps (iOS/Android)
- [ ] Calendar integration
- [ ] Shared todo lists
- [ ] Voice messages
- [ ] Video calls

## 🤝 Contributing

Contributions welcome! Please:
1. Fork the repository
2. Create feature branch
3. Make your changes
4. Test thoroughly
5. Submit pull request

## 📄 License

MIT License - feel free to use for personal or commercial projects.

## ⚠️ Disclaimer

- This is a self-hosted solution - you are responsible for your deployment
- Password encoding is basic - implement proper security for production
- GitHub API has rate limits - heavy usage may be restricted
- Not affiliated with GitHub

## 💡 Tips

1. **Use Private Repository** - Keep your data private
2. **Rotate Tokens** - Update tokens periodically
3. **Regular Backups** - Clone repository regularly
4. **Strong Passwords** - Use unique, strong passwords
5. **Test First** - Try in a test repo before production

## 📞 Support

- 📖 Read the [Setup Guide](SETUP_GUIDE.md)
- 🐛 Report issues on GitHub
- 💬 Check FAQs in documentation
- 🔍 Search existing issues first

## ❤️ Credits

Created with love for couples who value privacy and control over their data.

Built with: HTML, CSS, JavaScript, GitHub API, GitHub Pages

---

**Made with 💕 for preserving precious memories**

*Your data, your GitHub, your memories forever.*
