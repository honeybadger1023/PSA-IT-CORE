# Testing Delivery Team website

A static site for GitHub Pages plus an editor each team leader uses.

## How updates stay separate
- `index.html` never changes after setup. It reads data files.
- Each leader owns ONE file: `data/team-1.json` ... `data/team-5.json` (their slot).
- The site owner owns `data/config.json` (logo, gradient, newsletter, slideshow, news, holidays, rules).
- A leader only ever uploads their own file, so nobody can overwrite anyone else.

## One-time setup (site owner)
1. Create a public GitHub repository, e.g. `delivery-team`.
2. Upload everything in this folder except `admin-tool` (keep the `data` folder).
3. Settings > Pages > Source: "Deploy from a branch", branch `main`, folder `/ (root)`. Save.
4. Your site appears at `https://<your-user>.github.io/delivery-team/` after about a minute.
5. Add the leaders as collaborators (Settings > Collaborators), or let them send their file to you.
6. When real data is in, open the editor > Site settings, set "Show sample data notice" to No, download `config.json` and upload it to `data/`.

## Set up the editor (each leader, once)
1. Open Claude, start a chat, attach `admin-tool/team-editor.html`.
2. Paste this message:
   "Publish this attached file exactly as it is as an artifact. Turn on the database and downloads capabilities. Do not change the design or code."
3. Open the artifact, enter the team name, choose your slot (Team 1 to 5), press Start.
4. Import your current `data/team-N.json` (from the repository) so you start from what is live.

## Every update (each leader)
1. Edit in the editor. It saves automatically in your own Claude database.
2. Overview > Download team-N.json.
3. GitHub > `data` folder > Add file > Upload files > drop the file > Commit.

## Notes
- Each leader's database belongs to their own Claude account, so there is no shared database to clash.
- The site shows data exactly as uploaded. A team that has not uploaded yet shows a "no data" notice.
- Photos and slideshow images are shrunk by the editor before saving to keep files small.
- Sample data (5 teams, 30 people) is included so you can see every page. Replace it with real files.
