ARC8 — HOSTING PACKAGE
======================

WHAT'S IN THIS FOLDER
  index.html            The whole game: all 40 games, the splash screen, the logo, everything. THE ONLY ESSENTIAL FILE.
  favicon.ico           Browser-tab icon.
  icon-192.png          Icon for phones / "add to home screen".
  icon-512.png          Larger version of the same.
  apple-touch-icon.png  iPhone/iPad home-screen icon.
  site.webmanifest      Lets phones show "Arc8" with the icon when saved to the home screen.
  og-image.png          The picture shown when someone shares your link (social media, chat apps).
  robots.txt            Tells search engines they may index the site.

Everything is self-contained: no external scripts, fonts, images, servers or databases. It does not
need PHP, Node or a build step. Any host that can serve plain files will work.

KEEP THESE FILES TOGETHER, in the same folder, with these exact names.


FASTEST WAY TO PUT IT ONLINE (free, ~2 minutes)
  Netlify Drop:  go to app.netlify.com/drop and drag this whole folder onto the page.
                 You get a live https:// link immediately; sign up (free) to keep it.
  Others that work the same way: GitHub Pages, Cloudflare Pages, Vercel. 


PUTTING IT ON YOUR EXISTING WEBSITE
  1. Make a folder on your site, e.g. /arcade/   (or use the site root).
  2. Upload every file in this folder into it (FTP, SFTP, or your host's File Manager).
  3. Visit  https://yoursite.com/arcade/   — done. Link to it from your menu.
  It works from a subfolder because every path is relative.

  Website builders (WordPress, Squarespace, Wix) usually can't upload a folder of files. Host it
  as above, then add a "Custom HTML"/"Embed" block with:
      <iframe src="https://yoursite.com/arcade/" style="width:100%;height:900px;border:0" allow="autoplay"></iframe>
  A direct link is more reliable than an iframe: some browsers (Safari especially) block or erase
  saved progress inside third-party iframes.


TWO THINGS TO DO BEFORE YOU GO PUBLIC
  1. Link-preview image. Open index.html in a text editor and replace  YOUR-DOMAIN.com  with your real
     address in the two lines that mention og-image.png (search for "YOUR-DOMAIN"). If the site lives in
     a subfolder, include it, e.g.  https://yoursite.com/arcade/og-image.png
  2. Admin code. The hidden "show every game / preview each day" mode is switched on by typing a secret
     word on the game-list screen. It is set in index.html on the line:   const ADMIN_CODE = 'coinslot88';
     Change 'coinslot88' to your own word. (Anyone can read the page source, so treat this as a hidden
     convenience, not security.) Type the word again to switch it off.


MOBILE
  Works on phones and tablets with no extra setup. On a touch screen the games that need a keyboard get an
  on-screen pad (and swipe on 2048, Snake, Maze Runner, Mirror Maze and Lane Hopper); Breakout and Pong
  follow your finger; wide boards shrink to fit; text boxes open the right keyboard and don't make iPhones zoom.
  Visitors can use "Add to Home Screen" to keep it like an app.


GOOD TO KNOW
  - Daily lineup: Mon-Fri each day shows 8 of the 40 games (the same 8 every Monday, etc.). Saturday opens
    the first 20 games, Sunday the second 20. The day is the visitor's own local calendar day.
  - Saved data: levels, high scores and progress are stored in each visitor's own browser. They don't
    follow a player to another device, reset if the visitor clears their browser data, and there is no
    shared leaderboard (that would need a server).
  - Updating: replace index.html on your host. Visitors may need a hard refresh (Ctrl/Cmd+Shift+R) to see
    changes right away because browsers cache files.
  - Try it locally first: open index.html by double-clicking it, or from this folder run
    "python3 -m http.server 8000" and visit http://localhost:8000
